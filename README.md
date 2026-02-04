# Account Vault

[English](README.md) | [中文](README.zh-CN.md)

A privacy-focused, offline-first account management interface with built-in TOTP support. Designed with a modern glassmorphism aesthetic and a dual-theme system.

![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Introduction

Account Vault provides a secure, single-file solution for managing accounts and 2FA codes. It is built entirely with vanilla HTML, CSS, and JavaScript, ensuring zero dependencies and no build process. The application is configuration-driven, allowing for easy data management via a single JavaScript file.

## Features

- **Offline Architecture:** Zero external dependencies (except local OTP library). No data is sent to any server.
- **TOTP Support:** Integrated RFC 6238 compliant 2FA code generation.
- **Glassmorphism UI:** Modern interface with dark/light mode persistence.
- **Configuration Driven:** All data is managed in a separate configuration file for easy backup and portability.
- **Responsive Design:** Optimized for desktop and mobile viewports.
- **Instant Search:** Client-side filtering across all account fields.

## Quick Start

### Installation

Clone the repository:

```bash
git clone https://github.com/jjhuang01/account-vault.git
cd account-vault
```

### Usage

Simply open `index.html` in any modern web browser.

```bash
# MacOS
open google_accounts/index.html

# Windows
start google_accounts/index.html
```

## Configuration

Account data is stored in `google_accounts/data.js`. To orchestrate your own accounts, modify the `window.ACCOUNTS_DATA` object.

### Data Structure

```javascript
window.ACCOUNTS_DATA = {
  updated_at: "YYYY-MM-DD",
  groups: [
    {
      id: "personal",
      name: "Personal Accounts",
      accounts: [
        {
          email: "user@example.com",
          two_fa_secret: "JBSWY3DPEHPK3PXP", // Base32 string
          note: "Primary email",
          tags: ["important"],
        },
      ],
    },
  ],
};
```

**Note:** The `two_fa_secret` must be a valid Base32 string to generate correct TOTP codes.

## Security

This application runs entirely on the client side.

- No data is transmitted over the network.
- Passwords and secrets are stored in `data.js` (plain text).
- **Recommendation:** Use this tool in a secure, encrypted storage environment or for non-critical accounts.

## License

This project is open-sourced software licensed under the [MIT license](LICENSE).
