# 📋 「开口练」项目完整交接文档 (Project Handover Document)

> **生成时间**：2026-07-22  
> **项目名称**：开口练 (OpenKouLian) — 表达力与逻辑系统训练 App  
> **适用对象**：接手开发团队 / 运营团队 / 维护人员  

---

## 1. 📌 项目基本情况与定位

- **项目简介**：基于“无错、无漏、无废”核心表达理论打造的系统化口才与逻辑表达训练 PWA Web 应用。
- **设计风格**：默认“暖白纸质手帐风”（焦糖棕 `#c8956c` + 纸感背景 `#faf8f5` + Noto Serif SC 衬线体），支持一键切换“墨色手札模式 (Editorial Dark)”。
- **技术栈**：纯原生 HTML5 / CSS3 / JavaScript (ES6+)，零第三方框架包依赖，单页 PWA 架构。
- **部署环境**：Cloudflare Pages / Cloudflare Workers。

---

## 2. 🔗 在线资源与发布地址

| 资源名称 | 链接地址 / 路径 | 说明 |
| :--- | :--- | :--- |
| **线上生产站 (Pages)** | [https://kaikoulian.pages.dev](https://kaikoulian.pages.dev) | **推荐国内主访问地址** |
| **Workers 节点** | [https://kaikoulian.lijun051218.workers.dev](https://kaikoulian.lijun051218.workers.dev) | 边缘服务节点 |
| **GitHub 仓库** | [https://github.com/lijun117992/kaikoulian](https://github.com/lijun117992/kaikoulian) | 代码仓库 |
| **本地源码路径** | `C:\Users\机械革命\Documents\AI-Projects\网页\表达力训练工具\` | 开发根目录 |

---

## 3. 📂 项目目录结构

```text
表达力训练工具/
├── index.html                    # 核心单页应用主文件 (包含全部 UI/逻辑/样式)
├── manifest.json                 # PWA 应用配置文件 (支持添加到手机桌面)
├── sw.js                         # Service Worker 离线缓存服务
├── wrangler.json                 # Cloudflare 部署配置文件
├── README.md                     # 项目常规说明
├── HANDOVER.md                   # 项目完整交接文档 (本文件)
└── assets/                       # 静态资源目录
    ├── icon-192.svg              # 192x192 PWA 图标
    └── icon-512.svg              # 512x512 PWA 图标
```

---

## 4. ⚙️ 核心技术模块与实现原理

1. **语音识别与录音回放**
   - **语音转文字**：调用浏览器原生 `SpeechRecognition / webkitSpeechRecognition`。
   - **真录音回放**：调用原生 `MediaRecorder` API，录音结束后生成 Blob URL 渲染原生 `<audio>` 播放控件，供用户回听对比。
2. **文本相似度算法与雷达图**
   - **算法诊断**：内嵌 `Levenshtein Distance` (编辑距离算法)，实时对比参考文本与用户转述文本，精确计算匹配度。
   - **五维雷达图**：采用 HTML5 Canvas API 手绘五维雷达图（准确度、完整度、简洁度、流畅度、节奏感）。
3. **典籍名句库 (105 条真数据)**
   - 内置道德经、论语、孟子、庄子、孙子兵法、鬼谷子等 17 部经典典籍。
   - 每条含：文言文原文 + 白话翻译 + 场景化表达用例 + 150-300字历史典故。
4. **视频跟读组件**
   - 采用 Bilibili iframe 响应式嵌入，零存储占用，支持下拉选集。
5. **打卡热力图与成就系统**
   - Canvas 绘制 GitHub 风格真实打卡热力日历。
   - 8 大可解锁徽章墙，内置发光特效与 Confetti 粒子撒花庆祝。

---

## 5. ⚠️ 接手团队需注意事项与待改进建议 (Known Issues & Roadmap)

1. **📹 视频素材筛选与替换（高优先度）**
   - **当前状态**：跟读模块目前内置了 10 个 Bilibili 演讲/朗读视频链接。
   - **用户反馈**：部分视频素材与具体断句/跟读训练场景的贴合度有待进一步精细化遴选。
   - **替换方式**：修改 `index.html` 中的 `TRAINING_VIDEOS` 数组，将 `bvid` 替换为运营团队精选出的更优质、带字幕的专业口才训练视频 BV 号，或替换为 CDN 上的 `.mp4` 直链。
2. **🎤 语音 API 扩展**
   - 当前采用 Web Speech API，受浏览器兼容性影响（Chrome/Edge 体验最佳）。如未来需要商用精准识别，建议在服务端对接 Whisper 或讯飞语音识别 API。
3. **💾 数据备份**
   - 用户数据存储在浏览器 `localStorage` (`kaikoulian_app_state`)，支持设置页 JSON 导入导出。

---

## 6. 🚀 运维与部署命令指南

### 本地修改与测试
直接双击 `index.html` 或在本地起 HTTP 服务运行测试。

### 部署到 Cloudflare Pages
```bash
cmd /c "set XDG_CONFIG_HOME=C:\Users\机械革命\AppData\Roaming & npx wrangler pages deploy . --project-name kaikoulian --commit-dirty=true"
```

### Git 推送
```bash
git add .
git commit -m "update: handover documentation"
git push origin main
```
