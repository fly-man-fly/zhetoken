# Codex CLI 快速上手

欢迎使用 Codex！本教程将帮助你快速完成配置，开始使用 AI 编程助手。

## 快速导航

- [第一步：获取 Codex API Key](#step-1)
- [第二步：选择使用方式](#step-2)
- [常见问题](#faq)

---

## 第一步：获取 Codex API Key { #step-1 }

### 1. 登录控制台

访问 Codex 控制台：[https://codex-for.me/dashboard.html](https://codex-for.me/dashboard.html)

登录后可以看到：

- 账户余额
- 卡密兑换入口
- API Key 管理

### 2. 兑换卡密（如需充值）

在控制台的「卡密兑换」面板输入卡号，额度会即时到账。

### 3. 获取 API Key

在控制台的 API Key 区域复制你的密钥，稍后配置时需要用到。

!!! warning "注意"
    请妥善保管你的 API Key，不要分享给他人或提交到公开仓库。

---

## 第二步：选择使用方式 { #step-2 }

Codex 提供两种使用方式，根据你的需求选择：

| 方式 | 适合人群 | 特点 |
|------|----------|------|
| **命令行工具**（推荐） | 开发者 | 功能完整，性能最佳，官方支持 |
| **编辑器插件** | 日常开发 | 集成在编辑器中，使用便捷 |

!!! tip "推荐"
    推荐使用命令行工具：功能更强大，响应更快，体验更好。

两种方式可以同时使用，互不影响。

### 方案 A：命令行工具（推荐）

#### 安装

```bash
npm install -g codex-cli
```

#### 配置环境变量

=== "macOS / Linux"

    在终端中执行：

    ```bash
    export CODEX_API_KEY="你的API Key"
    ```

    为了永久生效，添加到 shell 配置文件：

    ```bash
    echo 'export CODEX_API_KEY="你的API Key"' >> ~/.bashrc
    source ~/.bashrc
    ```

=== "Windows"

    在 PowerShell 中执行：

    ```powershell
    $env:CODEX_API_KEY = "你的API Key"
    ```

    为了永久生效，设置系统环境变量：

    ```powershell
    [Environment]::SetEnvironmentVariable("CODEX_API_KEY", "你的API Key", "User")
    ```

#### 验证安装

```bash
codex --version
```

看到版本号即表示安装成功。

#### 开始使用

```bash
# 在项目目录中启动
codex

# 或者直接提问
codex "帮我写一个快速排序"
```

### 方案 B：编辑器插件

#### VS Code 安装

1. 打开 VS Code
2. 进入扩展商店，搜索 **Codex**
3. 点击安装
4. 打开设置，填入你的 API Key

#### JetBrains 安装

1. 打开 IDE（IntelliJ IDEA / PyCharm 等）
2. 进入 Settings → Plugins
3. 搜索 **Codex** 并安装
4. 重启 IDE，在设置中填入 API Key

---

## 常见问题 { #faq }

### Q: 提示 "API Key 无效" 怎么办？

请检查：

1. API Key 是否完整复制（没有多余空格）
2. 账户余额是否充足
3. API Key 是否已过期

### Q: 命令行和编辑器插件可以同时使用吗？

可以。两种方式互不影响，同一个 API Key 可以在多处同时使用。

### Q: 连接超时怎么办？

1. 检查网络连接
2. 尝试切换网络环境
3. 如果使用代理，请确保代理配置正确

### Q: 如何更新到最新版本？

```bash
npm update -g codex-cli
```

---

还有其他问题？请联系客服或查看 [常见问题](faq.md) 页面。
