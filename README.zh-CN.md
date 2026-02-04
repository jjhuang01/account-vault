# Account Vault (账号保险箱)

[English](README.md) | [中文](README.zh-CN.md)

一个注重隐私、离线优先的账号管理工具，内置 TOTP 双因素认证支持。采用现代化的玻璃态设计风格与双主题系统。

![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 简介

Account Vault 提供了一个安全、单文件的账号与 2FA 验证码管理方案。它完全由原生 HTML、CSS 和 JavaScript 构建，零依赖且无需构建流程。应用采用配置驱动（Configuration-driven）架构，通过单个 JavaScript 文件即可轻松管理数据。

## 功能特性

- **离线架构**：零外部依赖，所有逻辑在本地执行，不向服务器发送任何数据。
- **TOTP 支持**：集成符合 RFC 6238 标准的 2FA 验证码生成。
- **现代化 UI**：支持持久化存储的深色/浅色主题切换。
- **配置驱动**：所有数据存储在独立的配置文件中，便于备份与迁移。
- **响应式设计**：完美适配桌面端与移动端设备。
- **即时搜索**：支持全字段的客户端实时过滤。

## 快速开始

### 安装

克隆仓库：

```bash
git clone https://github.com/jjhuang01/account-vault.git
cd account-vault
```

### 使用

直接在任何现代浏览器中打开 `index.html`。

```bash
# MacOS
open google_accounts/index.html

# Windows
start google_accounts/index.html
```

## 配置说明

账号数据存储在 `google_accounts/data.js` 文件中。如需管理您自己的账号，请修改 `window.ACCOUNTS_DATA` 对象。

### 数据结构

```javascript
window.ACCOUNTS_DATA = {
  updated_at: "YYYY-MM-DD",
  groups: [
    {
      id: "personal",
      name: "个人账号",
      accounts: [
        {
          email: "user@example.com",
          two_fa_secret: "JBSWY3DPEHPK3PXP", // Base32 字符串
          note: "主邮箱",
          tags: ["重要"],
        },
      ],
    },
  ],
};
```

**注意**：`two_fa_secret` 必须是有效的 Base32 字符串以确保正确生成 TOTP 验证码。

## 安全须知

本应用完全在客户端运行。

- 不会通过网络传输任何数据。
- 密码和密钥存储在 `data.js` 中（明文）。
- **建议**：请在安全、加密的存储环境中使用本工具，或避免存储极高敏感度的凭据。

## 许可证

本项目基于 [MIT 许可证](LICENSE) 开源。
