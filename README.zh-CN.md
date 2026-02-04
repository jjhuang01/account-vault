# Account Vault (账号保险箱)

[🇬🇧 English](README.md) | **🇨🇳 中文**

一个现代化的、双主题的账号管理界面，内置 TOTP 双因素认证支持，采用玻璃态设计风格。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)

## ✨ 核心特性

- 🎨 **玻璃态 V2 设计** - 现代磨砂玻璃质感，搭配动态渐变背景
- 🌓 **双主题系统** - 丝滑的明暗模式切换，自动持久化存储
- 📱 **全端响应式** - 完美适配桌面、平板和移动设备
- 🔐 **TOTP 2FA 支持** - 实时生成 6 位动态验证码 (离线计算)
- 🔍 **智能搜索** - 所有字段毫秒级即时搜索
- 📊 **分组管理** - 自定义分组展示，井井有条
- 🎯 **一键复制** - 邮箱、密码、验证码点击即复制
- ⚡ **零依赖** - 纯原生 HTML/CSS/JavaScript (仅引入 OTPAuth.js 处理算法)

## 🚀 快速开始

1. **克隆仓库**

   ```bash
   git clone https://github.com/yourusername/account-vault.git
   cd account-vault
   ```

2. **在浏览器打开**
   ```bash
   open google_accounts/index.html
   ```

就是这么简单！**无需构建，无需 npm install**，双击即用。

## 📸 截图预览

### 深色模式

![Dark Theme](docs/screenshot-dark.png)

### 浅色模式

![Light Theme](docs/screenshot-light.png)

### 移动端试图

![Mobile](docs/screenshot-mobile.png)

## 🎨 设计理念

Account Vault 遵循 **"Spatial Warmth" (空间温感)** 设计系统：

- 动态渐变光球背景
- 带有背景模糊的玻璃态卡片
- 丝滑的微交互动画
- 高级 Inter 字体族
- 精心调配的色彩 Token

## 🔧 技术栈

- **前端**: 纯 HTML5, CSS3, JavaScript (ES6+)
- **图标**: [Lucide Icons](https://lucide.dev/)
- **TOTP**: [OTPAuth.js](https://github.com/hectorm/otpauth)
- **字体**: [Inter](https://fonts.google.com/specimen/Inter)

## 📁 项目结构

```
account-vault/
├── google_accounts/
│   ├── index.html          # 主程序 (单文件架构)
│   ├── data.js             # 账号数据 (配置驱动核心)
│   └── generate_mock_data.py  # Mock 数据生成器
├── README.md               # English Doc
├── README.zh-CN.md         # 中文文档
└── LICENSE
```

## 🛠️ 配置指南 (配置驱动)

本项目是 100% **配置驱动 (Configuration-Driven)** 的。所有数据都存储在 `google_accounts/data.js` 中。

**如何替换成你自己的数据：**

1. 用编辑器打开 `google_accounts/data.js`
2. 替换 `window.ACCOUNTS_DATA` 对象为你自己的 JSON 数据

### 数据结构规范

```javascript
window.ACCOUNTS_DATA = {
  updated_at: "YYYY-MM-DD HH:mm:ss",
  groups: [
    {
      id: "group-id-1", // 唯一 ID，用于过滤
      name: "我的个人账号", // 分组显示名称
      accounts: [
        {
          email: "me@example.com",
          password: "MyStrongPassword123", // 或者写密码提示
          recovery_email: "recovery@example.com",
          two_fa_secret: "JBSWY3DPEHPK3PXP", // Base32 密钥 (用于生成 TOTP)
          note: "主要账号",
          platform: "Google", // 可选: 图标/徽章类型
          tags: ["primary", "important"], // 可选: 自定义标签
        },
      ],
    },
  ],
};
```

> **小贴士**: `two_fa_secret` 必须是有效的 Base32 字符串 (A-Z, 2-7)。空格会自动被忽略。

## 🔐 安全须知

⚠️ **这是一个带有 Mock（演示）数据的演示应用。**

生产环境使用建议：

- **不要** 明文存储密码（建议配合加密库或仅存储提示）
- 为敏感数据实施端到端加密
- 部署到受保护的静态服务器 (HTTPS)
- 不要在公共网络暴露

## 🎯 个性化定制

### 修改主题

在 `index.html` 中修改 CSS 变量即可全局生效：

```css
:root[data-theme="dark"] {
  --bg-primary: #0a0e1a;
  --accent: #64ffda;
  /* ... */
}
```

## 🤝 贡献代码

欢迎提交 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交改动 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

## 📄 许可证

本项目基于 MIT License 开源 - 详见 [LICENSE](LICENSE) 文件。

## 🙏 致谢

- 设计灵感来自现代 Glassmorphism 趋势
- TOTP 实现基于 RFC 6238 标准
- 图标由 Lucide 提供

## 📧 联系方式

项目链接: [https://github.com/yourusername/account-vault](https://github.com/yourusername/account-vault)

---

Made with ❤️ by [Your Name]
