# Security Policy

## Reporting a Vulnerability

如果发现安全漏洞，请**不要提公开 Issue**。

发送邮件到：webkubor@gmail.com

我会在 48 小时内回复，确认后尽快修复并发布。

## 安全考量

本仓库是 prompt/skill 定义库，不含可执行服务端代码，风险面有限。但仍请注意：

- **密钥泄露**：skill 的 prompt 示例中不要包含真实 API key
- **敏感信息**：sample-output.jpg 中不要包含个人隐私数据
- **依赖安全**：`skills-cli` 是零依赖单文件 Python 脚本，无供应链风险
