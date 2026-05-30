# Markdown Reader

一个独立的单文件 HTML 本地 Markdown 阅读器。打开一个文件夹，在双栏界面中浏览和阅读其中的 Markdown 文件。

## 功能

- **文件夹浏览** — 打开本地任意文件夹，自动识别所有 `.md` 文件
- **代码高亮** — 支持 Python、JavaScript、TypeScript、Bash、JSON、CSS、XML、SQL、YAML
- **数学公式** — KaTeX 行内/行间公式（`$...$` / `$$...$$`）
- **图表渲染** — Mermaid 流程图、时序图等
- **深色/浅色主题** — 点击切换
- **侧边栏可调宽** — 拖拽调整文件树宽度
- **会话持久化** — 下次打开自动恢复上次浏览的文件夹（IndexedDB）
- **快速搜索** — 按文件名过滤侧边栏

## 使用

用浏览器打开 `index.html`（无需服务器），点击 **打开文件夹**（或 `Ctrl+O`），选择包含 Markdown 文件的文件夹，然后在侧边栏中点击任意文件阅读。

## 技术栈

| 库 | 版本 | 用途 |
|---------|---------|------|
| [marked](https://marked.js.org/) | 12.0.2 | Markdown → HTML |
| [highlight.js](https://highlightjs.org/) | 11.11.1 | 代码语法高亮 |
| [KaTeX](https://katex.org/) | 0.17.0 | 数学公式渲染 |
| [Mermaid](https://mermaid.js.org/) | 11.15.0 | 图表渲染 |

所有依赖从 CDN 加载，无需构建步骤。

## 自定义

只有一个 HTML 文件，用任意文本编辑器打开 `index.html` 即可修改：

| 想改什么 | 在哪儿改 |
|----------|----------|
| **颜色/主题** | `<style>` 开头的 `:root` CSS 变量，改 `--bg-primary`、`--accent` 等 |
| **字体** | `<style>` 块中的 `--font-family` |
| **代码高亮配色** | 两行 highlight.js 样式表 URL（`github-dark` / `github`），换成你喜欢的主题 |
| **CDN 版本** | 各 `<script src="...">` 的版本号 |
| **功能逻辑** | JavaScript 从 `// ── Init ──` 开始，函数如 `openFolder()`、`renderFile()` 等独立可改 |

例如想改强调色，在 `<style>` 中找到 `--accent: #6F68B7` 替换色值即可。

## License

MIT
