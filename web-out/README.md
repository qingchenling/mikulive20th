# MIKU 20TH 活动网站

纯静态网站，不需要 Node.js、npm 或构建步骤。

## 本地预览

在本文件所在目录运行：

```bash
python3 -m http.server 8080
```

浏览器访问 `http://localhost:8080`。

## 发布到 GitHub Pages

### 网站文件作为仓库根目录

1. 将 `web-out` 内的文件（包括 `.nojekyll`）放到 GitHub 仓库的根目录。
2. 在仓库的 **Settings → Pages → Build and deployment** 中选择 **Deploy from a branch**。
3. 选择存放文件的分支（通常是 `main`），目录选择 **/ (root)**，保存。
4. 等待 GitHub Pages 部署完成，通过 Pages 设置中显示的网址访问。

### 保留 web-out 子目录

如果整个项目作为仓库、保留 `web-out/` 子目录：

1. 把本目录下的 `.github/workflows/pages.yml` 复制到仓库根目录的 `.github/workflows/pages.yml`。
2. 在 **Settings → Pages** 中将 Source 选为 **GitHub Actions**。
3. 工作流默认由 `main` 分支的推送触发；如果使用其他分支，修改工作流的 `branches`。
4. 推送提交，或在 Actions 中手动运行工作流。

工作流会自动选择根目录或 `web-out/` 作为网站文件目录。所有页面、样式、脚本和图片均使用相对路径，兼容 `https://用户名.github.io/仓库名/` 和自定义域名。无需修改资源路径，请保留文件名的大小写。

## 内容更新

- `index.html`：主页面和活动介绍。
- `soon.html`：GOODS、TICKETS、SPECIAL 共用的建设中页面。
- `style.css`：颜色、排版、移动端适配和动画；支持系统的“减少动态效果”设置。
- `script.js`：进入视口时播放一次的轻量动画，不影响关闭 JavaScript 后浏览内容。
- `background.jpg`、`favicon.png`：现有主视觉背景与网站图标。

更新内容后提交到配置的发布分支即可。
