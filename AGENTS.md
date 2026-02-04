# AGENTS.md

> Configuration for AI coding assistants (Claude Code, Gemini, Cursor, etc.)

## 📁 Project Structure

```
google_accounts/
├── index.html    # Main app (HTML + CSS + JS in single file)
└── data.js       # All account data (Configuration-Driven)
```

## 🔧 Data Format

All data lives in `google_accounts/data.js`. Structure:

```javascript
window.ACCOUNTS_DATA = {
  updated_at: "YYYY-MM-DD HH:mm:ss",
  groups: [
    {
      id: "unique-group-id",
      name: "Display Name",
      accounts: [
        {
          email: "user@example.com",
          password: "SecretPassword",
          recovery_email: "backup@example.com",
          two_fa_secret: "BASE32SECRET", // Must be valid Base32
          note: "Optional note",
          platform: "Google",
          tags: ["manager", "verified"],
        },
      ],
    },
  ],
};
```

### Field Rules

| Field           | Required | Format            |
| :-------------- | :------: | :---------------- |
| `email`         |    ✅    | Valid email       |
| `password`      |    ❌    | String or `-`     |
| `two_fa_secret` |    ❌    | Base32 (A-Z, 2-7) |
| `tags`          |    ❌    | Array of strings  |

## 🎨 Styling Rules

- **DO** use CSS variables (defined in `:root`)
- **DO NOT** hardcode colors
- **Maintain** Glassmorphism aesthetic (blur, transparency)
- **Preserve** Inter font family

### Key CSS Variables

```css
--bg-primary      /* Page background */
--card-bg         /* Card backgrounds */
--accent          /* Primary accent color */
--text-primary    /* Main text color */
--radius-lg       /* Card border radius (28px) */
```

## 🚫 Prohibited

- No plaintext secrets in code comments
- No external API calls (offline-first)
- No build steps (pure HTML/CSS/JS)
