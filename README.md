# Moe API 开源指南

面向国内开发者的 AI API 接入、配置与排障资料，覆盖 Claude Code、Codex CLI、Gemini CLI、New API 下游配置以及常见网关错误。

## 推荐阅读

- [AI CLI 国内接入指南](./ai-cli-cn-guide/README.md)：Claude Code、Codex CLI、Gemini CLI 的第三方 API 配置思路。
- [New API 接入 Moe API](./new-api-moe-api/README.md)：从渠道配置到兼容性验证的检查清单。
- [AI API 网关错误排查](./ai-api-troubleshooting/README.md)：502、503、504 的定位路径与可复制诊断命令。

## 为什么单独维护这些内容

不同客户端对 API 协议、环境变量和模型名称的要求不同；网关问题也常常发生在客户端、代理、上游服务三个边界之间。本项目把可验证的配置步骤和排障证据放在一起，方便提交修订和持续更新。

## 贡献

欢迎提交准确性修订。涉及价格、模型名称、限流和服务可用性的内容，请附上日期、地区和测试条件，避免把短期结果当成长期承诺。

## 免责声明

文档仅用于技术学习与配置参考。第三方服务的条款、价格、可用区域和模型能力可能变化，请以服务商当前公告为准。不要在仓库、日志或截图中提交 API Key。
