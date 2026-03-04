# 🌟 CTRLIX PROXY

**CTRLIX** (Control Intelligence X) is a professional, standalone, and ultra-lightweight CLI tool designed to proxy OpenAI's unofficial Codex Desktop App backend into a standard OpenAI-compatible API.

This allows you to use your **ChatGPT Plus / GPT-4o / GPT-5** capabilities for free (via your existing desktop session) with developer tools like **Continue.dev**, **Claude Code**, **Cline**, and other AI agents.

---

## 🚀 Installation

You can install CTRLIX globally to use the command anywhere in your terminal:

```bash
# From the project directory
npm install -g .
```

After installation, simply run:
```bash
ctrlix
```

## 🎮 Interactive CLI Features

Once you launch `ctrlix`, you enter an interactive shell with professional formatting and slash commands:

- **`/add`**: Log in to a new ChatGPT account. It opens your browser and automatically saves the account using your email as the identifier.
- **`/start`**: Starts the internal proxy server (Default port: `8888`).
- **`/stop`**: Stops the running proxy server.
- **`/port`**: Change the default port (e.g., to `9000`). This setting is saved persistently.
- **`/accounts`**: View all logged-in accounts.
- **`/switch`**: Fast-switch between multiple ChatGPT accounts.
- **`/remove`**: Safely delete a saved account.
- **`/help`**: Display the command guide.
- **`/exit`**: Leave the CTRLIX controller.

## 🛠 Integration with IDEs

To use CTRLIX with your favorite tools, set the base URL to your local proxy:

### Continue.dev (config.json)
```json
{
  "models": [
    {
      "title": "Codex Proxy",
      "model": "gpt-4o",
      "apiBase": "http://localhost:8888/v1",
      "provider": "openai",
      "apiKey": "any-string"
    }
  ]
}
```

### Manual Test (curl)
```bash
curl http://localhost:8888/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4o",
    "messages": [{"role": "user", "content": "Hello!"}],
    "stream": true
  }'
```

## ✨ Why CTRLIX?

1. **Zero Configuration**: Just `/add` and `/start`. No manual token hunting.
2. **Model Mapping**: Automatically maps `gpt-5` or `gpt-4o` to backend-compatible slugs to avoid "model not supported" errors.
3. **Multi-Account**: Manage work and personal accounts seamlessly in one CLI.
4. **Professional UI**: A beautifully centered and colored terminal interface.
5. **Ultra-Lightweight**: Written in pure Node.js with zero external dependencies in the core logic.

---

## ⚖️ Requirements

- **MacOS** (Intel/Silicon) or **Windows** (x64)
- **Node.js v18+**

> [!NOTE]
> The login engine binaries are bundled in the pre-built `.tgz` release. If you are cloning from GitHub, you may need to download the appropriate `codex` binary for your platform from the [official OpenAI Codex repository](https://github.com/openai/codex/releases) and place it in `bin/engine/`.

---
*Created with 🌟 for advanced AI engineering.*
