# AI CLI 国内接入指南

本指南说明如何为 Claude Code、Codex CLI、Gemini CLI 配置兼容的第三方 API。示例只展示变量名和占位地址，不包含任何真实密钥。

## 安全原则

- API Key 使用环境变量或系统密钥链保存，不写入 shell 配置截图、仓库和 issue。
- 先用最小权限、低额度账号验证，再扩大权限。
- 对第三方中转服务核对隐私政策、日志保留、模型映射和限流规则。
- 不要把官方客户端的账号登录凭据交给不受信任的代理。

## Claude Code

不同版本对变量名和兼容协议支持可能不同。先查当前版本文档，再设置服务商要求的 endpoint 和 key。例如：

```powershell
$env:ANTHROPIC_BASE_URL = "https://api.example.com"
$env:ANTHROPIC_API_KEY = "替换为你的密钥"
```

启动后先发送短消息，确认返回模型、状态码和请求 ID。遇到 401/403 时检查 key 权限、请求头和 endpoint；遇到 404 时检查模型名与协议路径。

## Codex CLI

Codex CLI 的认证方式、配置文件和模型支持会随版本变化。使用前固定 CLI 版本，阅读该版本的官方配置说明，并确认服务商支持 Responses API 或 CLI 所需的协议。不要把一个客户端的变量名直接套到另一个客户端。

## Gemini CLI

确认代理是否支持 Gemini CLI 使用的 API 形态、模型名和流式响应。若服务商只提供 OpenAI 兼容接口，通常需要使用其明确支持的 OpenAI 兼容客户端，而不是假设 Gemini CLI 可以直接替换 endpoint。

## 验证清单

1. 查看客户端版本和生效配置来源。
2. 发送一个最小请求，不上传敏感数据。
3. 记录 HTTP 状态码、响应协议、模型名和请求 ID。
4. 验证流式输出、超时、重试和上下文长度。
5. 清除测试 key，并确认 shell 历史没有保存密钥。

## 相关阅读

- [New API 接入 Moe API](../new-api-moe-api/README.md)
- [AI API 网关错误排查](../ai-api-troubleshooting/README.md)
