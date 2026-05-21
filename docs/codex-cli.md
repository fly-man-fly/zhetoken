# Codex CLI 配置教程

## 前言

Codex CLI 是 OpenAI 官方的命令行 AI 编程工具。本文介绍 Windows / Mac / Linux 三系统的统一配置流程。

前置 Node.js 与 Git 环境的安装请参考 **Node.js 与 Git 环境配置教程**，cc-switch 配置详见 **cc-switch 配置教程**。

---

## 安装 Codex CLI

### 安装方法

三系统使用同一条 npm 命令

```bash
npm install -g @openai/codex
```

验证

```bash
codex --version
```

输出版本号即为安装成功

### 常见问题

**Q：permission denied / EACCES 错误（Mac / Linux）**

不要使用 `sudo`，把 npm 全局目录改到用户目录

```bash
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.bashrc   # zsh 用户改为 ~/.zshrc
source ~/.bashrc
```

**Q：permission denied 错误（Windows）**

以管理员身份运行 PowerShell

```bash
npm config set prefix "$env:APPDATA\npm"
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

**Q：command not found: codex**

npm 全局 bin 目录未加入 PATH，执行 `npm config get prefix` 查看路径，将对应的 `/bin` 目录追加到系统 PATH

---

## 配置 API

### cc-switch（推荐）

cc-switch 同时支持 Claude Code 和 Codex，无需手动编辑配置文件，可在多渠道间一键切换。

详细安装与使用见 **cc-switch 配置教程**

!!! warning "注意"
    Codex 的 Base URL 必须带 `/v1` 后缀（与 Claude Code 不同）

### 手动编辑配置文件

Codex 不使用环境变量，而是读取两个配置文件：

| 系统 | config.toml | auth.json |
|------|-------------|-----------|
| Windows | `C:\Users\<用户名>\.codex\config.toml` | `C:\Users\<用户名>\.codex\auth.json` |
| Mac / Linux | `~/.codex/config.toml` | `~/.codex/auth.json` |

#### 编辑 config.toml

若文件不存在，先创建 `.codex` 目录再新建文件。Windows 在 `%USERPROFILE%`，Mac/Linux 直接 `mkdir -p ~/.codex`

```toml
model_provider = "custom"
model = "gpt-5.4"
model_reasoning_effort = "high"
disable_response_storage = true

[model_providers.custom]
name = "custom"
base_url = "https://你的请求地址/v1"
wire_api = "responses"
requires_openai_auth = true
model_context_window = 1000000
model_auto_compact_token_limit = 900000
```

#### 编辑 auth.json

```json
{
  "OPENAI_API_KEY": "sk-xxx"
}
```

保存后重启终端，`codex` 启动时会自动读取上述配置

#### 配置参数速查

| 参数 | 说明 | 可选值 |
|------|------|--------|
| `model_provider` | 模型提供商标识，需与下方 `[model_providers.xxx]` 一致 | 自定义名称 |
| `model` | 使用的模型 | 见模型列表 |
| `model_reasoning_effort` | 推理深度 | `low` / `medium` / `high` |
| `disable_response_storage` | 禁用服务端响应存储 | 推荐 `true` |
| `wire_api` | API 协议 | `responses` |
| `model_context_window` | 上下文窗口（1M 长上下文场景填 `1000000`） | 整数 |
| `model_auto_compact_token_limit` | 接近上限前自动压缩对话 | 整数（一般 `900000`） |

---

## 开始使用

在任意项目目录打开终端，输入 `codex` 启动

```bash
cd 你的项目目录
codex
```

看到输入框出现提示符后，直接用中文或英文描述需求即可，例如

```
帮我用 Python 实现一个二叉搜索树，包含插入、删除、查找方法
```
