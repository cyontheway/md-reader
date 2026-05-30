# Markdown Reader

A standalone, single-file HTML markdown reader for browsing markdown files locally. Open a folder and navigate its markdown files in a clean, two-panel interface.

## Features

- **Folder-based browsing** — open any local folder, render all `.md` files
- **Syntax highlighting** — Python, JavaScript, TypeScript, Bash, JSON, CSS, XML, SQL, YAML
- **Math rendering** — KaTeX inline and display math (`$...$` / `$$...$$`)
- **Diagrams** — Mermaid flowcharts, sequence diagrams, and more
- **Dark / light theme** — toggle with the theme button
- **Responsive sidebar** — resizable file tree panel
- **Persistent session** — reopens your last folder on restart (IndexedDB)
- **Fast search** — filter files by name in the sidebar

## Usage

Open `index.html` in a browser (no server required), click **打开文件夹** (or `Ctrl+O`), select a folder containing markdown files, then click any file in the sidebar to read it.

## Tech Stack

| Library | Version | Use |
|---------|---------|-----|
| [marked](https://marked.js.org/) | 12.0.2 | Markdown → HTML |
| [highlight.js](https://highlightjs.org/) | 11.11.1 | Code syntax highlighting |
| [KaTeX](https://katex.org/) | 0.17.0 | Math typesetting |
| [Mermaid](https://mermaid.js.org/) | 11.15.0 | Diagrams and flowcharts |

All dependencies loaded from CDN. No build step required.

## Customization

Everything is in a single HTML file — open `index.html` in any text editor to tweak:

| What | Where to look |
|------|---------------|
| **Colors / theme** | `:root` CSS variables at the top of `<style>`. Change `--bg-primary`, `--accent`, etc. |
| **Fonts** | `--font-family` in the `<style>` block. Default uses system UI fonts. |
| **Syntax theme** | The two highlight.js stylesheets (`github-dark` / `github`). Swap the CDN URL for your preferred highlight.js theme. |
| **CDN version** | The `<script src="...">` URLs. Pin any version you like. |
| **Features** | JavaScript starts at `// ── Init ──`. Functions like `openFolder()`, `renderFile()`, etc. are self-contained and easy to modify. |

To change the accent color, for example, just find `--accent: #6F68B7` in the `<style>` block and replace the hex value.

## License

MIT
