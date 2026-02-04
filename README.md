# Account Vault

**🇬🇧 English** | [🇨🇳 中文](README.zh-CN.md)

A modern, dual-themed account management interface with TOTP 2FA support and glassmorphism design.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)

## ✨ Features

- 🎨 **Glassmorphism V2 Design** - Modern frosted glass aesthetics with dynamic gradient backgrounds
- 🌓 **Dual Theme System** - Seamless Dark/Light mode toggle with localStorage persistence
- 📱 **Fully Responsive** - Optimized for desktop, tablet, and mobile devices
- 🔐 **TOTP 2FA Support** - Real-time 6-digit verification code generation
- 🔍 **Smart Search & Filtering** - Instant search across all account fields
- 📊 **Group Management** - Organize accounts into customizable groups
- 🎯 **Click-to-Copy** - One-click copy for emails, passwords, and TOTP codes
- ⚡ **Zero Dependencies** - Pure HTML/CSS/JavaScript (except OTPAuth.js for TOTP)

## 🚀 Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/account-vault.git
   cd account-vault
   ```

2. **Open in browser**
   ```bash
   open google_accounts/index.html
   ```

That's it! No build process required.

## 📸 Screenshots

### Dark Theme

![Dark Theme](docs/screenshot-dark.png)

### Light Theme

![Light Theme](docs/screenshot-light.png)

### Mobile View

![Mobile](docs/screenshot-mobile.png)

## 🎨 Design Philosophy

Account Vault follows the **"Spatial Warmth"** design system:

- Dynamic gradient orb backgrounds
- Glassmorphic cards with backdrop blur
- Smooth micro-interactions
- Premium Inter font family
- Carefully crafted color tokens

## 🔧 Tech Stack

- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Icons**: [Lucide Icons](https://lucide.dev/)
- **TOTP**: [OTPAuth.js](https://github.com/hectorm/otpauth)
- **Fonts**: [Inter](https://fonts.google.com/specimen/Inter)

## 📁 Project Structure

```
account-vault/
├── google_accounts/
│   ├── index.html          # Main application
│   ├── data.js             # Account data (mock data for demo)
│   └── generate_mock_data.py  # Mock data generator
├── README.md
└── LICENSE
```

## 🔐 Security Notes

⚠️ **This is a demo application with mock data.**

For production use:

- Never store passwords in plain text
- Use proper encryption for sensitive data
- Implement backend authentication
- Store TOTP secrets securely
- Use HTTPS only

## 🎯 Customization

### Adding Accounts

Edit `google_accounts/data.js`:

```javascript
{
  "email": "user@example.com",
  "password": "YourPassword123",
  "recovery_email": "recovery@example.com",
  "two_fa_secret": "JBSWY3DPEHPK3PXP",  // Base32 encoded
  "note": "Manager Account",
  "platform": "Google Workspace",
  "tags": ["manager", "verified"]
}
```

### Theme Customization

Modify CSS variables in `index.html`:

```css
:root[data-theme="dark"] {
  --bg-primary: #0a0e1a;
  --accent: #64ffda;
  /* ... */
}
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Design inspired by modern glassmorphism trends
- TOTP implementation based on RFC 6238
- Icons provided by Lucide

## 📧 Contact

Project Link: [https://github.com/yourusername/account-vault](https://github.com/yourusername/account-vault)

---

Made with ❤️ by [Your Name]
