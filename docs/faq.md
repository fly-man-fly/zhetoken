# 常见问题

## 通用问题

### API Key 在哪里获取？

访问 [官网](https://code.b886.top)，登录后在左侧 **令牌管理** 中添加令牌并复制密钥。

### API Key 通用吗？

是的，同一个 API Key 可以在所有工具（Codex CLI、Claude Code 等）中使用。

### 如何充值？

在官网首页，输入自定义充值数量（1元起），或选择预设充值额度，选择支付方式即可。

### 账户余额不足会怎样？

API 调用会返回错误，提示余额不足。充值后即可恢复使用。

---

## 连接问题

### 连接超时

1. 检查网络连接是否正常
2. 确认 API/URL 地址是否正确（Codex 需要加 `/v1` 后缀）
3. 尝试更换网络环境

### 提示 "Authentication failed" / "Unauthorized"

1. 检查 API Key 是否完整复制（没有多余空格）
2. 确认令牌已选择正确的分组
3. 检查账户余额是否充足

### 响应速度慢

1. 尝试切换到其他模型
2. 减少单次请求的上下文长度
3. 检查网络延迟

---

## 工具特定问题

### Codex CLI

**Q：`codex` 命令找不到怎么办？**

npm 全局 bin 目录未加入 PATH，执行 `npm config get prefix` 查看路径，将对应的 `/bin` 目录追加到系统 PATH。

**Q：Base URL 应该填什么？**

Codex 的 Base URL 必须带 `/v1` 后缀（与 Claude Code 不同）。

### Claude Code

**Q：`claude` 命令找不到怎么办？**

npm 全局 bin 目录未加入 PATH，执行 `npm config get prefix` 查看路径，将对应的 `/bin` 目录追加到系统 PATH。

**Q：permission denied 错误（Mac / Linux）**

不要使用 `sudo`，把 npm 全局目录改到用户目录：

```bash
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```

### cc-switch

**Q：切换渠道后不生效？**

下次启动 `claude` 或 `codex` 命令时即生效，无需重启终端。

**Q：如何让 VSCode 插件也使用当前渠道？**

在 cc-switch 设置中开启 **应用到 ClaudeCode 插件** 即可。

---

还有其他问题？联系站长解决即可。
