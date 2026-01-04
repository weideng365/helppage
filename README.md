# lkmio 信令服务器帮助文档

这是 lkmio 信令服务器的静态帮助文档和 API 文档站点。本项目旨在为 lkmio 信令服务器提供清晰、易用的文档支持，帮助开发者快速接入和使用。

## 核心模块介绍

lkmio 信令服务器基于 Go 语言开发，具备高性能、高并发特性，全面支持 GB28181 协议，并独创性地实现了 JT1078 到 GB28181 的无缝转换。

### 1. 高性能 Go 实现
利用 Go 语言优秀的并发处理能力（Goroutines），确保服务器在处理大规模设备接入和信令交互时依然保持稳定可靠。

### 2. GB28181 标准支持
全面覆盖国标 GB/T 28181 协议的核心功能，包括但不限于：
- **设备注册与注销**：支持设备的主动注册和心跳保活。
- **目录查询**：支持查询设备目录、通道信息。
- **视频预览**：支持实时视频流的推流与拉流。
- **录像回放**：支持设备端历史录像的查询与回放。

### 3. JT1078 互通
这是本项目的特色功能。支持将部标 JT/T 1078 协议的视频流转换为国标 GB28181 协议，打通了车联网视频监控与公共安全视频监控平台之间的壁垒，实现跨协议的视频互通。

### 4. API 友好
提供设计清晰、遵循 RESTful 规范的 API 接口，完美适配 LiveGBS 等前端展示系统，极大降低了二次开发和集成的难度。详细接口定义请参考 [API 文档](api_docs.html)。

## 目录结构

- `index.html`: 首页，项目概览与特性介绍。
- `api_docs.html`: API 文档页面，详细列出了设备管理、通道管理、推流控制等接口。
- `style.css`: 样式文件，定义了页面的视觉风格。
- `wrangler.toml`: Cloudflare Pages 配置文件。
- `_headers`: Cloudflare Pages 响应头配置。

## 部署到 Cloudflare Pages

本项目已配置为可直接部署到 Cloudflare Pages。

### 步骤 1: 准备代码
将此项目推送到您的 GitHub 或 GitLab 仓库。

### 步骤 2: 创建 Pages 项目
1. 登录 Cloudflare Dashboard。
2. 点击 **Create application**。
3. **关键步骤**：点击 **Pages** 标签页 (不要留在 Workers 标签页)，然后点击 **Connect to Git**。
4. 选择您的仓库 `lkmio/helppage` (假设)。

### 步骤 3: 配置构建设置
在 **Build settings** 中：
- **Framework preset**: None
- **Build command**: (留空) - **注意：绝对不要填 `npx wrangler deploy`**
- **Build output directory**: `.` (即当前目录)

### 步骤 4: 部署
点击 **Save and Deploy**。部署完成后，Cloudflare 会自动分配一个 `*.pages.dev` 的域名。

## 更多资源

- **GitHub 仓库**: [https://github.com/lkmio](https://github.com/lkmio)
- **API 文档**: [在线查看](api_docs.html)
