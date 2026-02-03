# 🦞 OpenClaw WeCom — 企业级 AI 助手

<p align="center">
    <picture>
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/openclaw/openclaw/main/docs/assets/openclaw-logo-text-dark.png">
        <img src="https://raw.githubusercontent.com/openclaw/openclaw/main/docs/assets/openclaw-logo-text.png" alt="OpenClaw" width="500">
    </picture>
</p>

<p align="center">
  <strong>企业微信集成版</strong>
</p>

**OpenClaw WeCom** 是您私有部署的 *个人 AI 助手*，专为集成企业微信而优化。
除了支持原有的 WhatsApp, Telegram, Slack, Discord 等渠道外，本项目特别增强了对**企业微信 (WeCom)** 的支持。

[网站](https://openclaw.ai) · [文档](https://docs.openclaw.ai) · [DeepWiki](https://deepwiki.com/openclaw/openclaw)

## 进交流群群内测体验
<p align="center">
  <img src="https://github.com/user-attachments/assets/ddda8c5e-ec31-48c9-9514-9a95634a0d7b" alt="OpenClaw WeCom" style="max-width: 100%; height: auto; width: 350px; height: 499px; object-fit: cover;" />
</p>

## 快速开始

运行环境: **Node ≥22**.

### 安装

```bash
npm install -g openclaw-wecom
# 或者: pnpm add -g openclaw-wecom

openclaw onboard --install-daemon
```

### 启动网关

```bash
openclaw gateway --port 18789 --verbose
```

### 发送消息

```bash
# 发送消息
openclaw message send --to +1234567890 --message "来自 OpenClaw WeCom 的问候"

# 与助手对话
openclaw agent --message "项目进度检查" --thinking high
```

## 企业微信集成 (WeCom)

本项目集成了 Python 版本的企业微信 Bot (`openclawqiyeweixinbot-suaiwis`) 作为 OpenClaw 的一个通讯渠道。

### 功能亮点

*   **双向通信**: 支持 OpenClaw 发送消息到企业微信，以及接收企业微信的消息。
*   **多模态支持**: 支持文本、图片、文件等多种消息类型。
*   **桥接架构**: 利用原有 Python 项目的 DLL 处理能力，通过 HTTP 桥接实现无缝集成。

### 配置

在 `src/wecom/` 目录下配置您的企业微信 Bot API 地址和 Webhook 回调。

```json5
{
  channels: {
    wecom: {
      apiUrl: "http://localhost:8002",
      webhookPath: "/api/v1/channels/wecom/webhook"
    }
  }
}
```

## 功能特性

*   **[本地优先网关](https://docs.openclaw.ai/gateway)** — 统一控制平面，管理会话、渠道、工具和事件。
*   **[多渠道聚合](https://docs.openclaw.ai/channels)** — 统一管理 WhatsApp, Telegram, Slack, 企业微信等多个渠道。
*   **[智能代理路由](https://docs.openclaw.ai/gateway/configuration)** — 将不同的消息路由到独立的 Agent 进行处理。
*   **[实时 Canvas](https://docs.openclaw.ai/platforms/mac/canvas)** — 交互式可视化工作区。

## 社区与贡献

欢迎提交 PR 或 Issue！

请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解更多贡献指南。

---
*OpenClaw 原项目由 Peter Steinberger 和社区构建。*
