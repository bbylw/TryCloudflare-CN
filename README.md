# TryCloudflare（快速隧道 / Quick Tunnels）是什么

**TryCloudflare** 是 Cloudflare Tunnel 提供的一项免费、零配置的能力：无需拥有域名、无需修改 DNS，一行命令即可把本地运行的 Web 服务通过 Cloudflare 全球网络暴露到公网。

> 官方文档：<https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/do-more-with-tunnels/trycloudflare/>

## 🚀 快速开始

### 1. 安装 cloudflared

按[官方安装说明](https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/downloads/)安装命令行工具，版本需 ≥ `2020.5.1`。

```bash
# macOS
brew install cloudflare/cloudflare/cloudflared
```

### 2. 启动本地服务

在 `localhost` 上运行一个可被 `cloudflared` 连接的服务，例如监听 `http://localhost:8080`。

### 3. 开启隧道

```bash
cloudflared tunnel --url http://localhost:8080
```

终端会打印一个随机生成的 `*.trycloudflare.com` 子域名，把它分享给任何人即可从公网访问你的本地服务。

> ⚠️ 若 `.cloudflared` 目录中存在 `config.yaml`，快速隧道暂不支持，请临时重命名该文件。

## 💡 典型使用场景

- 把笔记本上的项目临时分享给他人，对方无需和你处于同一网络
- 创建免费隧道，在不同浏览器中测试新站点的兼容性
- 用 Pingdom / WebPageTest 等工具连到随机子域名，从不同地区做速度测试

## ⚠️ 限制（仅适用于快速隧道）

| 限制 | 说明 |
| --- | --- |
| 并发请求上限 | 同时代理的在途请求硬上限为 **200**，触顶时返回 `429` |
| 不支持 SSE | 不支持 Server-Sent Events |

如需突破限制，请[注册 Cloudflare 账户](https://dash.cloudflare.com/sign-up)并[创建托管的 Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/get-started/)用于生产环境。

## ❓ 为什么 Cloudflare 免费提供？

- 希望更多用户体验 Cloudflare Tunnel 的速度与安全，试用后用于生产站点
- 降低试用门槛：以往需拥有域名并配置 DNS，现在无需这些负担
- 不保证 SLA / 在线率，Cloudflare 会在此通道上试验新功能，为生产发布前提供测试连接组

## 📄 法律声明

安装 `cloudflared` 即表示你接受 [Cloudflare 许可协议](https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/downloads/license/)、[服务条款](https://www.cloudflare.com/terms/)与[隐私政策](https://www.cloudflare.com/privacypolicy/)。

---

> 本仓库为上述内容的中文教程网站源码（基于 Tailwind CSS v4 构建）。详见 [`index.html`](./index.html)。
