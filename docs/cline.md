# cc-switch 配置教程

## 前言

开源工具，可方便地管理 API key、MCP、Skills，无需手动配置环境变量，并支持多渠道一键切换。

下载地址：[https://github.com/farion1231/cc-switch/releases](https://github.com/farion1231/cc-switch/releases)

---

## 下载与安装

在 Release 页根据系统选择对应的安装包

### Windows

下载 `.exe` 安装包，双击运行，按向导完成安装

### Mac

下载 `CC-Switch-vX.X.X-macOS.dmg`（universal 通用包，Apple Silicon 和 Intel 均可使用），双击挂载后将图标拖入 Applications

如需免安装版可下载 `macOS.tar.gz`，解压后即可运行

!!! warning "注意"
    首次打开若提示"无法验证开发者"，前往 **系统设置 → 隐私与安全性**，点击"仍要打开"

### Linux

Linux 提供三种格式，每种都有 `arm64` 和 `x86_64` 两个架构（按你的 CPU 选择对应版本）

- `.AppImage`：通用免安装，所有发行版均可使用
- `.deb`：Ubuntu / Debian / Deepin 等
- `.rpm`：CentOS / RHEL / Fedora / openSUSE 等

#### AppImage（通用，免安装）

```bash
chmod +x CC-Switch-*-Linux-*.AppImage
./CC-Switch-*-Linux-*.AppImage
```

#### deb 包（Ubuntu / Debian）

```bash
sudo dpkg -i CC-Switch-*-Linux-*.deb
sudo apt install -f
```

#### rpm 包（CentOS / RHEL / Fedora）

```bash
sudo rpm -i CC-Switch-*-Linux-*.rpm
```

或使用 dnf / yum：

```bash
sudo dnf install ./CC-Switch-*-Linux-*.rpm
```

---

## 添加渠道

先从官网获取 API Key 与请求地址，记录备用

### Claude 为例

1. 顶部选择 Claude 图标后点击加号
2. 选择 **自定义渠道**
3. 仅需填写 **供应商名称、API Key、请求地址**，点击 **添加/保存** 即可自动启用

### Codex 为例

1. 顶部选择 Codex 图标后点击加号
2. 选择 **自定义渠道**
3. 仅需填写 **供应商名称、API Key、请求地址（Codex 需要以 /v1 结尾）**，点击 **添加/保存** 即可自动启用

### Gemini 为例

设置与上述相同，换汤不换药

---

## 附加设置

建议开启以下两项：

- **应用到 ClaudeCode 插件**：让 VSCode/JetBrains 等 IDE 内的 Claude Code 插件自动读取当前渠道
- **跳过 Claude Code 初次安装确认**：第一次启动 `claude` 时不再弹出登录/授权确认

---

## 切换 / 管理渠道

在主界面点击任意渠道即可切换为当前生效渠道，无需重启 Claude Code（下次启动 `claude` 命令时即生效）

渠道支持 编辑 / 删除 / 排序，便于在 Anthropic 官方、第三方代理、本地代理之间快速切换
