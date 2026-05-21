# Claude Code 配置教程

## 前言

Claude Code 是 Anthropic 官方的命令行 AI 编程工具。本文介绍 Windows / Mac / Linux 三系统的统一配置流程。

前置 Node.js 与 Git 环境的安装请参考 **Node.js 与 Git 环境配置教程**，cc-switch 配置详见 **cc-switch 配置教程**。

---

## 安装 Claude Code

### 安装方法

三系统使用同一条 npm 命令

```bash
npm install -g @anthropic-ai/claude-code
```

验证

```bash
claude -v
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

**Q：command not found: claude**

npm 全局 bin 目录未加入 PATH，执行 `npm config get prefix` 查看路径，将对应的 `/bin` 目录追加到系统 PATH

---

## 配置 API Key

### cc-switch（推荐）

图形化工具，支持多渠道一键切换、自动写入 ClaudeCode 插件，无需手动改环境变量。

详见独立文章 **cc-switch 配置教程**

### 手动配置环境变量

#### Windows

以管理员身份打开 PowerShell，运行

```powershell
setx ANTHROPIC_BASE_URL "你的API地址"
setx ANTHROPIC_AUTH_TOKEN "你的Key"
```

**关闭并重开终端**后验证

```powershell
# PowerShell
echo $env:ANTHROPIC_BASE_URL
echo $env:ANTHROPIC_AUTH_TOKEN

# cmd
echo %ANTHROPIC_BASE_URL%
echo %ANTHROPIC_AUTH_TOKEN%
```

#### Mac / Linux

编辑 shell 配置文件（zsh 用户编辑 `~/.zshrc`，bash 用户编辑 `~/.bashrc`，macOS 上的 bash 编辑 `~/.bash_profile`）

```bash
vim ~/.zshrc
```

在文件末尾追加

```bash
export ANTHROPIC_BASE_URL="你的API地址"
export ANTHROPIC_AUTH_TOKEN="你的Key"
```

保存退出后让配置生效并验证

```bash
source ~/.zshrc
echo $ANTHROPIC_BASE_URL
echo $ANTHROPIC_AUTH_TOKEN
```

---

## 开始使用

在任意项目目录打开终端（Windows 可右键 **"在终端中打开"** 或 **"Git Bash Here"**），输入 `claude` 启动

```bash
cd 你的项目目录
claude
```

首次启动会依次提示：选择主题样式、信任当前目录、登录方式（cc-switch 已开启"跳过初次安装确认"则自动跳过）

看到输入框出现 `>` 提示符后，直接用中文或英文描述需求即可，例如

```
帮我在当前目录创建一个 hello.py 输出 Hello World
```

常用快捷指令：

- `/help`：查看所有命令
- `/clear`：清空当前会话
- `/exit` 或连按两次 `Ctrl + C`：退出
