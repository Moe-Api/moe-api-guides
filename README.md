# AI API 中转与模型接入指南 | GPT、Claude、Gemini、Codex、New API

面向国内开发者的 AI API 中转、第三方 API 接入、模型配置与网关排障资料。覆盖 OpenAI GPT、Claude、Gemini、Codex、Claude Code、Gemini CLI、Codex CLI，以及 New API 下游接入。

## Moe API 快速访问

需要稳定的 AI API 中转服务，可直接访问 **[Moe API](https://moeapi.com)**，查看可用模型、接口文档与接入方式。

> 请以 Moe API 网站当前公布的模型、价格、限流和服务条款为准。不要在 GitHub issue、日志或截图中公开 API Key。

## 你可以在这里找到什么

- **AI API 中转**：GPT、Claude、Gemini 等模型的第三方 API 接入思路
- **Claude Code 国内接入**：环境变量、兼容接口与常见错误定位
- **Codex CLI 配置**：CLI 版本、Responses API 与第三方 endpoint 检查清单
- **Gemini CLI 接入**：协议、模型名称、流式响应与兼容性验证
- **New API 下游配置**：渠道、模型映射、超时、重试和限流设置
- **GPT / Claude / Gemini 排障**：502、503、504、401、403、429 错误定位

## 推荐阅读

- [AI CLI 国内接入指南](./ai-cli-cn-guide/README.md)：Claude Code、Codex CLI、Gemini CLI 的第三方 API 配置思路。
- [New API 接入 Moe API](./new-api-moe-api/README.md)：从渠道配置到兼容性验证的检查清单。
- [AI API 网关错误排查](./ai-api-troubleshooting/README.md)：502、503、504 的定位路径与可复制诊断命令。

## 关键词

`AI API` · `API 中转` · `GPT API` · `Claude API` · `Gemini API` · `Codex` · `Claude Code` · `Gemini CLI` · `Codex CLI` · `New API` · `OpenAI 兼容接口` · `Anthropic Messages` · `Responses API`

## 为什么单独维护这些内容

不同客户端对 API 协议、环境变量和模型名称的要求不同；网关问题也常常发生在客户端、代理、上游服务三个边界之间。本项目把可验证的配置步骤和排障证据放在一起，方便提交修订和持续更新。

## 贡献

欢迎提交准确性修订。涉及价格、模型名称、限流和服务可用性的内容，请附上日期、地区和测试条件，避免把短期结果当成长期承诺。

## 免责声明

文档仅用于技术学习与配置参考。第三方服务的条款、价格、可用区域和模型能力可能变化，请以服务商当前公告为准。不要在仓库、日志或截图中提交 API Key。
