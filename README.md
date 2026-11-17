# 📄 Doc2PDF

> 极简电子书与文档转 PDF 工具 —— 你的本地排版工作室

**Doc2PDF** 是一款开箱即用的电子书 / 文档转换工具。拖入 EPUB、Markdown 或 TXT 文件，调整排版，一键导出排版精美的 PDF 电子书。所有解析与转换均在**本地浏览器内核中完成**，文件不出你的电脑。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Web-lightgrey.svg)](#-下载与安装)
[![Size](https://img.shields.io/badge/Package-Portable%20EXE%20·%2074MB-8A2BE2)](#-下载与安装)

---

## ✨ 特性

- **📚 多格式支持** — EPUB、Markdown (`.md` / `.markdown`)、TXT 一网打尽，自动解析章节结构与 EPUB 封面
- **🖱️ 拖拽即用** — 文件拖入窗口即可开始，无需任何配置
- **📐 专业排版控制** — 页面尺寸（A4 / A5）、正文字号、行间距、页边距自由调节，实时预览
- **🖨️ 双导出模式** —
  - **矢量打印导出（推荐）**：调用原生打印管线，文字为高清矢量，缩放不失真
  - **一键直接下载**：html2pdf.js 快速生成，适合简单场景
- **🔒 隐私优先** — 纯本地处理，零上传，离线打包版不依赖任何服务器存储
- **🌗 深浅双主题** — 精心设计的浅色 / 深色界面，长时间使用不疲劳
- **📦 单文件便携版** — Windows 免安装 EXE，双击即用，U 盘随身携带

## 📦 下载与安装

### Windows 便携版（推荐）

前往 [Releases 页面](../../releases) 下载 `Doc2PDF.exe`（约 74 MB），双击即可运行，无需安装。

> 首次启动有数秒自解压等待，属正常现象。

### 网页版

仓库中的 `index.html` 是完整的单页应用，可直接用浏览器打开使用（需联网加载 CDN 资源）。

## 🚀 使用方法

1. 将 `.epub` / `.md` / `.txt` 文件拖入窗口（或点击选择）
2. 按需调整排版参数：页面尺寸、字号、行距、页边距
3. 展开预览确认效果
4. 点击 **「导出高清矢量 PDF」**，选择「另存为 PDF」即可

## ⚙️ 排版选项一览

| 选项 | 可选值 | 默认 |
| --- | --- | --- |
| 页面尺寸 | A4（标准文档）/ A5（电子书阅读） | A4 |
| 正文字号 | 13 / 15 / 17 / 19 px | 15 px |
| 行间距 | 紧凑 1.5 / 舒适 1.75 / 宽松 2.0 | 1.75 |
| 页边距 | 窄 12mm / 标准 18mm / 宽 25mm | 18mm |

## 🛠️ 从源码构建

环境要求：Node.js ≥ 18

```bash
# 克隆仓库
git clone https://github.com/Leon-Ning-san/doc2pdf.git
cd doc2pdf

# 安装依赖
npm install

# 开发模式运行
npm start

# 打包 Windows 便携版 EXE（输出至 dist/）
npm run build
```

国内网络环境建议设置镜像加速：

```bash
ELECTRON_MIRROR=https://npmmirror.com/mirrors/electron/ \
ELECTRON_BUILDER_BINARIES_MIRROR=https://npmmirror.com/mirrors/electron-builder-binaries/ \
npm run build
```

## 🧱 技术栈

| 层 | 技术 |
| --- | --- |
| 界面 | Tailwind CSS · 原生 HTML / JS |
| Markdown 解析 | marked.js |
| EPUB 解压 | JSZip |
| PDF 生成 | html2pdf.js + 原生打印管线 |
| 桌面封装 | Electron 33 + electron-builder（portable target） |

## ⚠️ 已知限制

- 网页版与 EXE 的界面依赖（Tailwind / JSZip 等）通过 CDN 加载，**完全离线时不可用**
- `.mobi` 格式目前仅在文件选择器中列出，解析支持有限
- 矢量导出走系统打印管线，输出质量与所装打印机驱动相关，推荐选择「Microsoft Print to PDF」

## 🤝 贡献

欢迎提交 Issue 与 Pull Request —— 无论是新格式支持、排版增强还是界面优化。

## 📄 许可证

[MIT](LICENSE)
