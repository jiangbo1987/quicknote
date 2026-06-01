# QuickNote - 桌面悬浮快捷笔记

[![Version](https://img.shields.io/badge/version-1.2.0-blue.svg)](https://github.com/lilaoban/quicknote)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-lightgrey.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

轻量级的桌面悬浮笔记工具，让记录灵感像呼吸一样自然。

---

## 📸 截图

<img width="1342" height="934" alt="2" src="https://github.com/user-attachments/assets/bd1d0b8b-e691-4cc0-b952-82c007c86e9b" />
<img width="672" height="962" alt="1" src="https://github.com/user-attachments/assets/614f4f56-7d7a-40d5-8184-ffa8d5285765" />



---

## ✨ 核心特性

- **🎯 零干扰** - 悬浮图标常驻桌面，不遮挡工作区域
- **⚡ 零延迟** - 全局快捷键 1 秒内唤出笔记表单
- **💾 草稿保护** - 输入过程中自动保存草稿，关闭窗口不丢失
- **🖱️ 自由拖动** - 窗口可拖动到任意位置，面板切换时位置保持
- **📅 日历视图** - 按日期浏览历史笔记，快速定位
- **🔐 离线授权** - HMAC-SHA256 签名验证，无需联网
- **🌍 跨平台** - 支持 macOS (Intel/ARM64) 和 Windows (x64)

---

## 🚀 快速开始

### macOS

1. 下载 `.dmg` 安装包
2. 双击打开 DMG 文件
3. 将 QuickNote 拖入 `Applications` 文件夹
4. 启动应用

> **首次启动**：右键点击应用图标 →「打开」→ 在弹窗中再次点击「打开」

### Windows

**安装版（推荐）**：
1. 下载 `QuickNote Setup 1.2.0.exe`
2. 双击运行，按向导完成安装
3. 桌面快捷方式启动

**便携版**：
1. 下载 `QuickNote-1.2.0-Portable.exe`
2. 放到任意目录直接运行

> **SmartScreen 警告**：点击「更多信息」→「仍要运行」

---

## 📖 使用指南

### 记录第一条笔记

1. **单击** 悬浮图标（屏幕右下角蓝色圆形图标）
2. 输入标题（可选）和内容
3. 点击「保存」按钮

### 查看笔记

- **今日笔记**：右键托盘图标 →「📋 查看今日笔记」
- **历史笔记**：**双击**悬浮图标 或 右键托盘 →「📅 查看历史笔记」

### 编辑与删除

在笔记列表中，每条笔记都有操作按钮：
- ✏️ **编辑** - 修改标题或内容后保存
- 🗑️ **删除** - 删除笔记（不可恢复，请谨慎操作）

### 拖动窗口

- 按住窗口顶部的**标题栏**拖动即可移动窗口
- 切换不同面板（今日笔记 ↔ 历史笔记 ↔ 设置）时，窗口位置**不会重置**
- 使用全局快捷键唤起时，窗口会重新定位到光标附近

> **注意**：只有标题栏区域可拖动，输入框、按钮等区域保持正常交互。

---

## ⌨️ 快捷键

| 快捷键 | 平台 | 功能 |
|--------|------|------|
| `Cmd + Shift + N` | macOS | 在光标位置弹出笔记表单 |
| `Ctrl + Shift + N` | Windows | 在光标位置弹出笔记表单 |

### 自定义快捷键

1. 右键托盘图标 →「⚙️ 设置」
2. 找到「快捷键」设置项
3. 点击**录制按钮**
4. 按下你想设置的快捷键组合
5. 保存设置

---

## 🔑 授权说明

| 版本 | 授权码前缀 | 价格 | 笔记上限 |
|------|-----------|------|---------|
| 免费版 | — | 免费 | 1000 条 |
| 年费版 | `QNPRA-` | ¥9.9/年 | 无限 |
| 终身版 | `QNPRO-` | ¥49（一次性） | 无限 |

### 激活步骤

1. 右键托盘图标 →「⚙️ 设置」
2. 进入「授权信息」页面
3. 输入授权码
4. 点击「激活」按钮

> 免费版无需激活，安装即可使用。

---

## 📂 配置文件位置

| 平台 | 配置文件路径 |
|------|-------------|
| macOS | `~/Library/Application Support/QuickNote/` |
| Windows | `%APPDATA%\QuickNote\` |

**重要文件**：
- `license.json` - 授权信息（含 HMAC 签名）
- `settings.json` - 用户设置（快捷键、保存目录等）
- `notes/` - 笔记文件目录（按日期组织）

---

## 🛠️ 开发者指南

### 环境要求

- Node.js >= 18.0.0
- npm >= 9.0.0
- Python 3 (用于生成授权码)

### 安装依赖

```bash
cd /Users/lilaoban/workspace/quicknote
npm install
```

### 开发模式

```bash
npm start
```

### 打包

```bash
# macOS (Intel + ARM64)
npm run build-mac
npm run build-mac-arm

# Windows (x64)
npm run build-win

# 全部平台
npm run build-all
```

构建产物位于 `dist/` 目录。

---

## 🐛 常见问题

### macOS 提示「无法验证开发者」

**解决方法**：
1. 右键点击 QuickNote 图标
2. 选择「打开」
3. 在弹窗中点击「打开」

### Windows 弹出 SmartScreen 警告

**解决方法**：
1. 点击「更多信息」
2. 点击「仍要运行」

### 快捷键没有反应

**可能原因**：
1. 快捷键被其他应用占用 → 在设置中更换快捷键
2. macOS 未授予辅助功能权限 → 系统设置 → 隐私与安全性 → 辅助功能，添加 QuickNote
3. Windows 未以管理员身份运行 → 右键图标 →「以管理员身份运行」

### 如何备份笔记？

笔记以 JSON 文件形式存储在本地：
- macOS: `~/Library/Application Support/QuickNote/notes/`
- Windows: `%APPDATA%\QuickNote\notes\`

直接复制整个 `notes/` 目录即可备份。

---

## 📄 相关文档

- **产品需求文档 (PRD)**: [PRD_QuickNote.md](PRD_QuickNote.md)
- **使用手册**: [使用手册.md](使用手册.md)
- **授权码管理运维**: [管理运维_授权码.md](管理运维_授权码.md)

---

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

---

## 📝 更新日志

### v1.2.0 (2026-06-01)

**新增功能**：
- ✅ 窗口拖动位置保持（面板切换不重置）
- ✅ Windows 无边框窗口拖动支持
- ✅ 授权状态条实时显示
- ✅ license.json HMAC 签名防篡改
- ✅ 生成授权码支持 `--days` 自定义有效期

**修复**：
- 修复授权验证卡在"验证中"的 Bug
- 修复面板切换时窗口位置被重置
- 修复草稿保存失败问题

### v1.1.0 (2026-05-22)

**新增功能**：
- 笔记编辑和删除
- 设置面板
- 公众号二维码

### v1.0.0 (2026-05-20)

**首次发布**：
- 基础 CRUD 功能
- 悬浮图标交互
- 全局快捷键
- 日历视图
- 授权系统

---

**让灵感不再溜走** 💡
