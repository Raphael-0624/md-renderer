# MD Renderer

面向 Markdown 长文阅读、排版预览与内容导出的浏览器端工具。粘贴 Markdown 后即可实时查看效果，并在 112 套主题中切换阅读样式，最后导出为长图、PDF 或 HTML。

[在线使用](https://rafa.love/md) · [GitHub Pages 镜像](https://raphael-0624.github.io/md-renderer/) · [问题反馈](https://github.com/Raphael-0624/md-renderer/issues)

[![Live Demo](https://img.shields.io/badge/Live-Demo-6c63ff?style=flat-square)](https://rafa.love/md)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Online-24292f?style=flat-square)](https://raphael-0624.github.io/md-renderer/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)

## 功能

- Markdown 实时预览，覆盖标题、列表、任务列表、引用、代码块、表格和分割线等常用语法。
- 112 套阅读主题，包含经典、暗黑、极简、复古、创意和学术等风格。
- 可调字号、行高、正文宽度、中英文字体和代码高亮主题。
- 全屏阅读模式，以及字数、字符数和预计阅读时长统计。
- 导出 1920 像素宽长图、PDF 或独立 HTML。
- 单文件运行，无需安装依赖或执行构建命令。

## 在线地址

- 主站：<https://rafa.love/md>
- GitHub Pages：<https://raphael-0624.github.io/md-renderer/>

主站与 GitHub Pages 使用同一份单文件实现。GitHub Pages 版本会跟随 `main` 分支自动部署。

## 本地运行

下载仓库后，在项目目录启动任意静态文件服务器：

```bash
python3 -m http.server 8080
```

打开 <http://localhost:8080>。

项目没有构建步骤。也可以直接打开 `index.html`，但建议通过 HTTP 访问，以确保字体加载、剪贴板等浏览器能力处于正常的安全上下文。

## 使用方式

1. 在左侧输入框粘贴或编写 Markdown。
2. 在右侧查看实时渲染结果。
3. 打开主题面板，选择阅读主题和代码高亮样式。
4. 按需调整字号、行高、正文宽度和中英文字体。
5. 使用顶部工具栏导出长图、PDF 或 HTML。

页面内置示例内容，可点击「示例」快速查看各项排版效果。

## 技术实现

| 模块 | 实现 |
| --- | --- |
| 页面与交互 | 原生 HTML、CSS、JavaScript |
| Markdown 渲染 | marked |
| 代码高亮 | highlight.js 11.9.0 |
| 长图导出 | html2canvas 1.4.1 |
| PDF 导出 | jsPDF 2.5.1 |
| 字体 | Google Fonts |

项目刻意保持为单文件应用，目的是降低部署和维护成本。运行时依赖通过 CDN 加载，因此首次打开需要网络连接。

## 隐私

Markdown 渲染、主题切换和文件导出都在当前浏览器标签页中完成，项目没有后端服务，也不会上传或保存输入的文档内容。

页面会从 Google Fonts 和 jsDelivr 加载字体、脚本与样式资源。浏览器与这些 CDN 服务之间的网络请求受对应服务商的隐私政策约束。

## 浏览器支持

建议使用较新的 Chrome、Edge、Firefox 或 Safari。长图、PDF 导出和剪贴板功能依赖现代浏览器 API，旧版浏览器可能无法使用全部功能。

## 项目结构

```text
.
├── .github/workflows/pages.yml  # GitHub Pages 自动部署
├── index.html                   # 应用入口与完整实现
├── LICENSE
└── README.md
```

## 部署

推送提交到 `main` 分支后，GitHub Actions 会自动发布静态页面。首次部署时，需要在仓库的 Pages 设置中将发布来源设为 GitHub Actions。

## 参与贡献

欢迎通过 Issue 反馈问题或提出改进建议。提交 Pull Request 时，请优先保持当前的单文件、零构建体验，并说明改动对导出功能或浏览器兼容性的影响。

## 许可证

本项目基于 [MIT License](LICENSE) 开源。

Copyright © 2026 Raphael
