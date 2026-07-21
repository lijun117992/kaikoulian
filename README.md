# 📱 「开口练」— 表达力与逻辑系统训练 App 项目说明

基于“无错、无漏、无废”核心理论打造的个人表达力与口才系统化训练 Web App / PWA 应用。

---

## 🔗 在线体验

- **Cloudflare Pages（推荐国内直接访问）**：[https://kaikoulian.pages.dev](https://kaikoulian.pages.dev)
- **Cloudflare Workers 节点**：[https://kaikoulian.lijun051218.workers.dev](https://kaikoulian.lijun051218.workers.dev)

---

## ⭐ 核心亮点与功能

1. **暖白纸质手帐美学 (Bright Paper Style)**
   - 焦糖棕 + 米白纸感配色，搭配 Noto Serif SC 衬线体，兼具精致质感与练习仪式感。
2. **每日三字功主线 (跟 · 背 · 诵)**
   - 早跟读（配合 Bilibili 嵌入视频与平滑高亮歌词）、白天背金句、睡前诵名篇。
3. **6 大深度训练大厅**
   - 涵盖复述跟读、4D精准描述（带高清 SVG 图表）、脱稿转述、30秒电梯演讲、手绘透视与综合实战。
4. **国学典籍与表达金句宝典 (105 条真实数据)**
   - 精选道德经、论语、孟子、庄子、孙子兵法、鬼谷子等 17 部国学经典。
   - 每条均含：**原文 + 白话释义 + 表达化用场景 + 150-300字历史典故**。
5. **真实算法评分与打卡热力图**
   - 原生 Web Speech 语音识别 + 语速/用时/关键词匹配真算法诊断评分。
   - GitHub 风格 Canvas 真实打卡热力日历。

---

## 🛠️ 本地运行与维护

主应用为单个单页文件 `index.html`，直接用浏览器打开 `index.html` 即可运行。

如需通过 Wrangler 手动部署：
```bash
npx wrangler pages deploy . --project-name kaikoulian
```
