# AI API 网关错误排查

适用于客户端、反向代理、New API 和上游模型服务之间的 502、503、504 排查。

## 先收集证据

记录发生时间、请求 ID、目标模型、请求路径、状态码、首 token 延迟、总耗时，以及错误来自哪一层。脱敏后再分享日志。

## 502 Bad Gateway

通常表示代理收到上游的无效响应或连接被中断。检查 DNS、TLS、endpoint 路径、上游响应头、协议类型和代理日志。确认代理能从服务器直接访问上游，而不是只在本地浏览器可访问。

## 503 Service Unavailable

通常表示服务暂不可用、过载、健康检查失败或渠道被限流。检查实例健康、并发、配额、熔断状态和上游公告。重试应使用指数退避，并设置上限。

## 504 Gateway Timeout

通常表示代理等待上游超过超时。分别测量连接时间、TLS 时间、首 token 时间和总响应时间；流式接口要确认代理没有缓冲响应。不要只把超时无限调大，否则会堆积连接。

## 最小化测试

```powershell
$headers = @{ Authorization = "Bearer $env:AI_API_KEY" }
$body = @{ model = "模型名"; messages = @(@{ role = "user"; content = "ping" }) } | ConvertTo-Json -Depth 5
Invoke-WebRequest -Method Post -Uri "https://api.example.com/v1/chat/completions" -Headers $headers -ContentType "application/json" -Body $body -TimeoutSec 30
```

测试时使用低风险内容，确认响应后立即清理命令历史中的密钥。

## 排查顺序

客户端配置 → New API 路由 → 反向代理日志 → DNS/TLS → 下游健康与限流 → 模型和请求体兼容性。

## 相关阅读

- [AI CLI 国内接入指南](../ai-cli-cn-guide/README.md)
- [New API 接入 Moe API](../new-api-moe-api/README.md)
