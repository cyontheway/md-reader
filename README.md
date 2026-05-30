# Markdown Reader

A standalone, single-file HTML markdown reader. Open a folder and browse its markdown files in a clean two-panel interface.

一个独立的单文件 HTML 本地 Markdown 阅读器，双栏界面浏览 Markdown 文件。

## Features / 功能

- **Folder browsing** / 文件夹浏览 — Open any local folder, auto-detect all `.md` files / 打开本地文件夹，自动识别所有 md 文件
- **Syntax highlighting** / 代码高亮 — Python, JavaScript, TypeScript, Bash, JSON, CSS, XML, SQL, YAML
- **Math rendering** / 数学公式 — KaTeX inline and display math (`$...$` / `$$...$$`)
- **Diagrams** / 图表 — Mermaid flowcharts, sequence diagrams, etc. / 流程图、时序图等
- **Dark / light themes** / 深色/浅色主题 — toggle with one click / 一键切换
- **Resizable sidebar** / 侧边栏可调宽 — drag to resize the file tree panel / 拖拽调整宽度
- **Persistent session** / 会话持久化 — reopens your last folder on restart (IndexedDB) / 下次打开自动恢复上次浏览的文件夹
- **Fast search** / 快速搜索 — filter files by name in the sidebar / 按文件名过滤

## Usage / 使用

Open `index.html` in a browser (no server required), click **打开文件夹** (or `Ctrl+O`), select a folder containing markdown files, then click any file in the sidebar.

用浏览器打开 `index.html`（无需服务器），点击**打开文件夹**（或 `Ctrl+O`），选择 Markdown 文件夹，侧边栏点击文件阅读。

## Tech Stack / 技术栈

| Library / 库 | Version / 版本 | Use / 用途 |
|---------|---------|------|
| [marked](https://marked.js.org/) | 12.0.2 | Markdown → HTML |
| [highlight.js](https://highlightjs.org/) | 11.11.1 | Code highlighting / 代码高亮 |
| [KaTeX](https://katex.org/) | 0.17.0 | Math rendering / 公式渲染 |
| [Mermaid](https://mermaid.js.org/) | 11.15.0 | Diagrams / 图表 |

All dependencies loaded from CDN. No build step required.

所有依赖从 CDN 加载，无需构建。

## Customization / 自定义

Open `index.html` in any text editor — everything is in that single file.

只有一个 HTML 文件，用任意文本编辑器打开 `index.html` 即可修改：

| What / 改什么 | Where / 在哪儿 |
|----------|----------|
| **Colors & theme** / 颜色和主题 | `:root` CSS variables at the top of `<style>`. Change `--bg-primary`, `--accent`, etc. / `<style>` 开头的 CSS 变量 |
| **Fonts** / 字体 | `--font-family` in `<style>` |
| **Syntax theme** / 代码高亮配色 | Swap the CDN URL for highlight.js stylesheets (`github-dark` / `github`). / 替换 highlight.js 样式表 URL |
| **CDN versions** / 依赖版本 | The `<script src="...">` version numbers / 各 CDN URL 中的版本号 |
| **Features** / 功能逻辑 | JavaScript starts at `// ── Init ──`. Functions like `openFolder()`, `renderFile()`, etc. / JS 从 `// ── Init ──` 开始，函数独立可改 |

For example, to change the accent color, find `--accent: #6F68B7` in `<style>` and replace the hex value.

例如改强调色，在 `<style>` 中找到 `--accent: #6F68B7` 替换色值即可。

## License / 许可证

MIT
