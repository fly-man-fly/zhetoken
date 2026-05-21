# Cline 编辑器插件配置

Cline 是一个 VS Code 插件，让你在编辑器中直接使用 AI 编程助手。

## 快速导航

- [第一步：获取 API Key](#step-1)
- [第二步：安装 Cline 插件](#step-2)
- [第三步：配置中转站](#step-3)
- [常见问题](#faq)

---

## 第一步：获取 API Key { #step-1 }

访问控制台：[https://codex-for.me/dashboard.html](https://codex-for.me/dashboard.html)

在 API Key 管理区域复制你的密钥。

---

## 第二步：安装 Cline 插件 { #step-2 }

1. 打开 VS Code
2. 按 `Ctrl+Shift+X`（macOS 为 `Cmd+Shift+X`）打开扩展商店
3. 搜索 **Cline**
4. 点击 **Install** 安装

安装完成后，左侧活动栏会出现 Cline 图标。

---

## 第三步：配置中转站 { #step-3 }

### 打开 Cline 设置

1. 点击左侧的 Cline 图标
2. 点击右上角的齿轮图标进入设置

### 填写配置

在设置页面中：

| 配置项 | 填写内容 |
|--------|----------|
| **API Provider** | 选择 `OpenAI Compatible` |
| **Base URL** | 填入中转站地址 |
| **API Key** | 填入你的 API Key |
| **Model** | 选择你想使用的模型 |

!!! tip "推荐模型"
    - `claude-sonnet-4-20250514` — 性价比最高，日常开发推荐
    - `claude-opus-4-20250514` — 最强能力，复杂任务推荐
    - `gpt-4o` — 通用能力优秀

### 验证配置

在 Cline 的对话框中输入任意问题，如果正常回复则表示配置成功。

---

## 常见问题 { #faq }

### Q: 提示 "Connection refused" 怎么办？

1. 检查 Base URL 是否填写正确
2. 确认网络可以访问中转站地址
3. 尝试在浏览器中打开 Base URL 看是否能访问

### Q: 响应速度很慢怎么办？

1. 尝试切换到更快的模型
2. 检查网络延迟
3. 减少单次对话的上下文长度

### Q: 如何切换模型？

在 Cline 设置页面的 Model 选项中直接切换即可，无需重启。

---

还有其他问题？请查看 [常见问题](faq.md) 页面。
