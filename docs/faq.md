# 常见问题

## 通用问题

### API Key 在哪里获取？

访问 [控制台](https://codex-for.me/dashboard.html)，登录后在 API Key 管理区域复制。

### API Key 通用吗？

是的，同一个 API Key 可以在所有工具（Codex CLI、Cline、Claude Code 等）中使用。

### 如何充值？

在控制台的「卡密兑换」面板输入卡号，额度即时到账。

### 账户余额不足会怎样？

API 调用会返回错误，提示余额不足。充值后即可恢复使用。

---

## 连接问题

### 连接超时

1. 检查网络连接是否正常
2. 确认中转站地址是否正确
3. 尝试更换网络环境
4. 如果使用 VPN/代理，尝试关闭或切换节点

### 提示 "SSL Error"

1. 检查系统时间是否正确
2. 尝试更新系统证书
3. 联系客服获取帮助

### 响应速度慢

1. 尝试切换到其他模型
2. 减少单次请求的上下文长度
3. 检查网络延迟

---

## 工具特定问题

### Codex CLI

**Q: `npm install` 报错怎么办？**

确保 Node.js 版本 >= 18：

```bash
node --version
```

如果版本过低，请先升级 Node.js。

**Q: 如何更新 Codex CLI？**

```bash
npm update -g codex-cli
```

### Cline

**Q: VS Code 中找不到 Cline 插件？**

确保 VS Code 版本 >= 1.80。可以在 `帮助 → 关于` 中查看版本。

**Q: Cline 设置中没有 "OpenAI Compatible" 选项？**

更新 Cline 插件到最新版本。

### Claude Code

**Q: `claude` 命令找不到？**

检查 npm 全局安装路径是否在 PATH 中：

```bash
npm config get prefix
```

确保该路径下的 `bin` 目录在系统 PATH 中。

---

还有其他问题？请联系客服获取帮助。
