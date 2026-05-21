# Claude Code 配置教程

Claude Code 是 Anthropic 官方的命令行 AI 编程助手，功能强大，适合开发者使用。

## 快速导航

- [第一步：获取 API Key](#step-1)
- [第二步：安装 Claude Code](#step-2)
- [第三步：配置中转站](#step-3)
- [开始使用](#usage)
- [常见问题](#faq)

---

## 第一步：获取 API Key { #step-1 }

访问控制台：[https://codex-for.me/dashboard.html](https://codex-for.me/dashboard.html)

在 API Key 管理区域复制你的密钥。

---

## 第二步：安装 Claude Code { #step-2 }

### 前置要求

- Node.js 18 或更高版本

### 安装命令

```bash
npm install -g @anthropic-ai/claude-code
```

### 验证安装

```bash
claude --version
```

---

## 第三步：配置中转站 { #step-3 }

### 设置环境变量

=== "macOS / Linux"

    ```bash
    export ANTHROPIC_BASE_URL="你的中转站地址"
    export ANTHROPIC_API_KEY="你的API Key"
    ```

    永久生效：

    ```bash
    echo 'export ANTHROPIC_BASE_URL="你的中转站地址"' >> ~/.bashrc
    echo 'export ANTHROPIC_API_KEY="你的API Key"' >> ~/.bashrc
    source ~/.bashrc
    ```

=== "Windows (PowerShell)"

    ```powershell
    $env:ANTHROPIC_BASE_URL = "你的中转站地址"
    $env:ANTHROPIC_API_KEY = "你的API Key"
    ```

    永久生效：

    ```powershell
    [Environment]::SetEnvironmentVariable("ANTHROPIC_BASE_URL", "你的中转站地址", "User")
    [Environment]::SetEnvironmentVariable("ANTHROPIC_API_KEY", "你的API Key", "User")
    ```

---

## 开始使用 { #usage }

```bash
# 在项目目录中启动
claude

# 直接提问
claude "帮我优化这段代码"

# 带上下文提问
claude "解释 src/main.py 的功能"
```

### 常用命令

| 命令 | 说明 |
|------|------|
| `/help` | 查看帮助 |
| `/clear` | 清空对话上下文 |
| `/compact` | 压缩对话历史 |
| `Ctrl+C` | 中断当前操作 |
| `Ctrl+D` | 退出 |

---

## 常见问题 { #faq }

### Q: 提示 "Authentication failed" 怎么办？

1. 检查 API Key 是否正确
2. 确认 `ANTHROPIC_BASE_URL` 填写正确（不要加 `/v1` 后缀）
3. 检查账户余额是否充足

### Q: 如何查看当前配置？

```bash
claude config list
```

### Q: 可以使用哪些模型？

在对话中输入 `/model` 可以查看和切换可用模型。

---

还有其他问题？请查看 [常见问题](faq.md) 页面。
