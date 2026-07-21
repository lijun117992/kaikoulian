# 📱 「开口练」— GitHub + Cloudflare Pages 自动同步部署指南

本项目已初始化并提交至 GitHub 仓库：
👉 **[https://github.com/lijun117992/kaikoulian](https://github.com/lijun117992/kaikoulian)**

通过绑定 Cloudflare Pages 与 GitHub，以后每次我们在本地修改或更新代码，只需要一句 `git push`，Cloudflare 就会在 10 秒内**自动编译并更新线上应用**！

---

## ⚡ 1 分钟绑定 Cloudflare 与 GitHub

1. 打开 [Cloudflare 控制台](https://dash.cloudflare.com/) ➔ 点击 **Workers 和 Pages**。
2. 点击 **创建应用 (Create application)** ➔ 选择 **Pages** 选项卡。
3. 选择 **连接至 Git (Connect to Git)**。
4. 选择你的 GitHub 账号 `lijun117992`，在仓库列表中找到并选择 **`kaikoulian`** 仓库。
5. 点击 **开始配置 (Begin setup)**：
   - **项目名称**：`kaikoulian`
   - **生产分支**：`main`
   - **构建设置**：留空（框架预设选择 `None` 即可，本程序为纯静态 PWA，无需打包构建步骤）
   - **构建输出目录**：留空（默认根目录 `/`）
6. 点击 **保存并部署 (Save and Deploy)**！

---

## 🎉 部署完成效果

- 10 秒后，Cloudflare 会生成专属域名（如：`https://kaikoulian.pages.dev`）。
- **自动化同步**：以后任何修改只需运行 `git add .` -> `git commit -m "更新"` -> `git push`，Cloudflare 就会自动刷新线上全量应用，手机端会自动收到新版本！
