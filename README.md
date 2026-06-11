# 📚 CET-4 智能学习助手 / CET-4 Smart Learning Assistant

<p align="center">
  <img src="static/icons/icon-192.png" alt="CET-4 Logo" width="120" />
</p>

<p align="center">
  <strong>大学英语四级 (CET-4 / CET-6) 全功能智能备考平台</strong>
</p>

<p align="center">
  <a href="https://github.com/miholimm/CET4-App/releases"><img src="https://img.shields.io/badge/Windows-桌面版-blue?logo=windows" alt="Windows"></a>
  <a href="https://github.com/miholimm/CET4-App/releases"><img src="https://img.shields.io/badge/Android-APK-green?logo=android" alt="Android"></a>
  <a href="#"><img src="https://img.shields.io/badge/PWA-可安装-orange?logo=pwa" alt="PWA"></a>
  <img src="https://img.shields.io/badge/Python-3.11+-blue?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Flask-2.2+-green?logo=flask" alt="Flask">
  <img src="https://img.shields.io/badge/词汇量-1218-orange" alt="词汇量">
  <img src="https://img.shields.io/badge/license-MIT-brightgreen" alt="License">
</p>

---

## ✨ 功能特性 / Features

| 功能 | 说明 |
|------|------|
| 📝 **单词闪卡** | CET-4/CET-6 核心词汇闪卡式记背，支持词频排序、英汉互译 |
| 🎲 **随机测验** | 智能出题引擎，支持英汉选择/拼写/匹配多种题型 |
| 🎧 **听力训练** | 内置短对话、长对话、短文听力资源 |
| ✍️ **写作评估** | AI 辅助写作评估与反馈，内置多题材写作题库 |
| ⭐ **作文金句** | 6大分类55条金句，开头/过渡/结尾/论证/替换/模板 |
| 🚨 **考前抱佛脚** | 紧急模式，高频核心词+快速复习+模拟冲刺 |
| 📊 **学习统计** | 可视化学习进度、掌握率、每日打卡数据 |
| 🔄 **综合复习** | 错题回顾、薄弱点强化、智能推荐 |
| 📱 **多平台** | Web / PWA / Windows 桌面版 / Android APK |

---

## 🚀 快速开始 / Quick Start

### 🌐 在线使用（推荐）

直接访问云端服务器：

```
http://218.11.5.75
```

注册账号即可使用全部功能，数据云端存储，多设备同步。

### 🖥️ Windows 桌面版

从 [Releases](https://github.com/miholimm/CET4-App/releases) 下载 `CET4-Setup.exe`，双击运行即可。

- 单文件 16MB，无需安装
- 自动连接云服务器或启动本地服务
- 支持 Windows 10 / 11 (x64)

### 📱 Android

从 [Releases](https://github.com/miholimm/CET4-App/releases) 下载 APK 安装包。

> 也可通过 PWA 方式安装：Chrome 浏览器打开网站 → 自动弹出安装横幅

### 🐍 本地部署 / Local Deploy

```bash
# 克隆仓库
git clone https://github.com/miholimm/CET4-App.git
cd CET4-App

# 安装依赖
pip install -r requirements.txt

# 启动服务
python app.py

# 浏览器打开 http://127.0.0.1:5000
```

### 🐳 Docker 部署

```bash
# 构建镜像
docker build -t cet4-app .

# 运行容器
docker run -d -p 80:80 --name cet4-app cet4-app
```

---

## 🏗️ 技术栈 / Tech Stack

| 层级 | 技术 | 说明 |
|------|------|------|
| **后端** | Python 3.11 + Flask | RESTful API + Jinja2 模板引擎 |
| **数据库** | SQLite | 用户账户、学习记录、词库数据 |
| **前端** | HTML5 + CSS3 + Vanilla JS | 响应式设计 + Chart.js 图表 |
| **桌面版** | PyInstaller | 单文件 Windows .exe 打包 |
| **Android** | WebView + Gradle | 原生 Android 应用 |
| **部署** | Flask / Gunicorn / Nginx | Linux 服务器生产部署 |
| **PWA** | Service Worker + Manifest | 离线缓存 + 可安装 |

---

## 📂 项目结构 / Project Structure

```
CET4-App/
├── app.py                  # Flask 主应用 (路由/API/业务逻辑)
├── config.py               # 应用配置
├── models.py               # SQLite 数据模型
├── vocab_loader.py         # 词库加载器（支持 CET-4/CET-6）
├── quiz_generator.py       # 智能测验出题引擎
├── writing_evaluator.py    # 写作评估引擎
├── launcher.py             # 桌面启动器（云端优先 + 本地回退）
├── run.py                  # 服务器启动脚本
├── requirements.txt        # Python 依赖
│
├── templates/              # Jinja2 HTML 模板 (15个页面)
│   ├── base.html           #   基础布局（导航/PWA支持）
│   ├── index.html          #   首页/仪表盘
│   ├── vocab.html          #   单词闪卡
│   ├── quiz.html           #   随机测验
│   ├── listening.html      #   听力训练
│   ├── writing.html        #   写作练习
│   ├── golden.html         #   作文金句
│   ├── emergency.html      #   考前抱佛脚
│   ├── stats.html          #   学习统计
│   ├── review.html         #   综合复习
│   ├── login.html          #   登录
│   ├── register.html       #   注册
│   └── ...
│
├── static/                 # 静态资源
│   ├── css/style.css       #   全局样式
│   ├── js/                 #   JavaScript 脚本
│   ├── icons/              #   应用图标 (11个尺寸)
│   ├── manifest.json       #   PWA 清单
│   └── sw.js               #   Service Worker
│
├── golden_sentences.json   # 作文金句库 (55条)
├── writing_prompts.json    # 写作题库
├── listening_resources.json# 听力资源
└── emergency_vocab.json    # 抱佛脚高频词库
```

---

## 📖 功能详解 / Feature Details

### 单词闪卡
- CET-4 核心词汇 (1218词) + CET-6 进阶词汇
- 按词频排序，优先学习高频词
- 英汉双向闪卡，支持键盘快捷键
- 标记「已掌握/再复习」，智能复习计划

### 随机测验
- 智能出题：根据用户掌握情况动态调整难度
- 多题型：英译中选择、中译英选择、拼写、匹配
- 即时反馈 + 详细解析
- 错题自动加入复习队列

### 作文金句
- 🚀 开头句型 — 万能开头、现象引入
- 🔗 过渡句型 — 递进、对比、转折
- 🎯 结尾句型 — 总结、呼吁、倒装
- 💡 论证句型 — 举例、数据、引用
- ⭐ 高级替换 — important→crucial 等10对
- 📋 万能模板 — 直接套用的段落框架
- 点击一键复制到剪贴板

### 考前抱佛脚
- 筛选中高频核心词汇（考试出现概率 > 60%）
- 30分钟极速复习模式
- 模拟冲刺测试

---

## 🔧 构建指南 / Build Guide

### Windows 桌面版 (.exe)

```bash
pip install pyinstaller
cd CET4-App
pyinstaller --onefile --name "CET4学习助手" \
  --add-data "templates;templates" \
  --add-data "static;static" \
  --add-data "*.json;." \
  --hidden-import flask \
  launcher.py
# 产出: dist/CET4学习助手.exe
```

### Android APK

```bash
# 需要 JDK 17 + Android SDK
cd CET4-Android
./gradlew assembleRelease
# 产出: app/build/outputs/apk/release/app-release.apk
```

---

## 🌍 服务器部署 / Server Deploy

```bash
# SSH 登录服务器
ssh root@your-server

# 上传项目文件
scp -r CET4-App root@your-server:/opt/cet4-app/

# 安装依赖
apt-get install python3-flask

# 启动（端口 80 需 root）
cd /opt/cet4-app
nohup python3 run.py > /tmp/cet4.log 2>&1 &
```

---

## 📄 License

MIT License © 2026 [miholimm](https://github.com/miholimm)

---

## 🤝 贡献 / Contributing

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建 Feature 分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

---

<p align="center">
  <strong>⭐ 如果这个项目对你有帮助，请给一个 Star！</strong>
</p>
