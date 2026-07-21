# 📱 「开口练」— Cloudflare Pages 一键部署指南

只需 **1 分钟**，即可将「开口练」App 部署到 Cloudflare，获得公网 HTTPS 专属网址，并在 iPhone / 安卓手机上作为独立 App 使用！

---

## 第一步：准备部署文件

确保文件夹 `C:\Users\机械革命\Documents\AI-Projects\网页\表达力训练工具\` 下包含以下文件：
- `index.html` （主程序应用）
- `manifest.json` （App 手机配置文件）
- `sw.js` （PWA 离线脚本）

---

## 第二步：在 Cloudflare Pages 上发布网站

1. 登录你的 [Cloudflare 控制台](https://dash.cloudflare.com/)。
2. 在左侧菜单点击 **Workers 和 Pages** ➔ 点击 **创建应用**。
3. 选择 **Pages** 选项卡 ➔ 点击 **上传资产 (Upload assets)**。
4. 在“项目名称”填入 `kaikoulian`（或你喜欢的名字）。
5. 将 `表达力训练工具` 文件夹里的所有文件直接**拖拽打包**上传。
6. 点击 **部署站点 (Deploy site)**！

成功后，Cloudflare 会为你生成一个专属网址：
👉 `https://kaikoulian.pages.dev`（带有免费安全的 HTTPS 证书）。

---

## 第三步：在手机上“安装”为原生 App

使用手机打开你的 Cloudflare 网址（如 `https://kaikoulian.pages.dev`）：

### 🍎 iPhone / iPad (Safari)
1. 用 **Safari** 浏览器打开网址。
2. 点击屏幕底部中间的 **分享图标** ⬆️。
3. 向下滑动，点击 **添加到主屏幕 (Add to Home Screen)**。
4. 命名为 **开口练**，点击右上角 **添加**。

### 🤖 安卓手机 (Chrome / Edge / 品牌浏览器)
1. 用 **Chrome** 或 **Edge** 浏览器打开网址。
2. 点击右上角的 **三点菜单** ⋮。
3. 点击 **安装应用** 或 **添加到主屏幕**。

---

🎉 此时你的手机桌面就会出现一个 **「开口练」App 图标**！点击即可全屏运行，自带独立 App 体验，且离线可用。
