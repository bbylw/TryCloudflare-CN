# TryCloudflare 中文教程

基于 [Cloudflare 官方文档 — Quick Tunnels](https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/do-more-with-tunnels/trycloudflare/) 翻译与整理的中文教程网站，介绍如何使用 **TryCloudflare** 快速将本地服务安全暴露到公网。

## ✨ 特性

- **纯静态站点** — 单页 HTML + 编译后的 Tailwind CSS，无需后端
- **Tailwind CSS v4** — CSS-first 配置（`@theme`），自定义品牌色与字体
- **真实 Cloudflare 标识** — 内联 SVG 云标 + favicon
- **精致视觉** — 渐变光晕、网格、噪点氛围层；滚动渐显动效
- **响应式** — 桌面双栏（含 sticky 目录轨道），移动端自动折叠
- **可访问性** — 尊重 `prefers-reduced-motion`

## 📦 技术栈

- HTML5
- Tailwind CSS v4（`@tailwindcss/cli`）
- 字体：Space Grotesk / JetBrains Mono / Noto Sans SC（Google Fonts）

## 🚀 本地开发

```bash
# 安装依赖
npm install

# 编译 CSS（生成 styles.css）
npm run build

# 或监听模式，改动后自动重新编译
npm run watch
```

编译完成后，直接用浏览器打开 `index.html` 即可预览。

## 📁 项目结构

```
.
├── index.html        # 站点主页面（Tailwind 工具类）
├── styles.css         # 编译后的样式（由 src/input.css 生成）
├── src/
│   └── input.css      # Tailwind 入口：@theme 主题与自定义工具类
├── package.json       # 构建脚本与依赖
└── .gitignore
```

## 📝 内容概要

| 章节 | 内容 |
| --- | --- |
| 什么是快速隧道 | Quick Tunnels 原理与适用场景 |
| 三步上手 | 安装 cloudflared → 启动本地服务 → 运行命令 |
| 终端实战 | 完整命令行演示 |
| 能力与限制 | 200 并发上限、不支持 SSE |
| 常见问题 | 使用场景、免费原因、429、config.yaml |
| 法律声明 | 许可协议、服务条款、隐私政策 |

## ⚠️ 说明

快速隧道仅用于**测试与开发**，不保证 SLA 或在线率，请勿用于生产部署。生产环境请创建远程托管的 Cloudflare Tunnel。

## 📄 许可

本教程内容整理自 Cloudflare 官方文档，仅供学习参考。
