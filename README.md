# devserver 🚀

> Universal development server manager - never let a dev server hang your terminal again

![devserver demo](https://img.shields.io/badge/dev-server-green?style=for-the-badge&logo=npm)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## The Problem

You know this pain:

```bash
npm run dev
# Terminal frozen. Can't run other commands.
# CTRL+C to stop server just to run one command.
# Start server again. Repeat. 😤
```

Or worse:

```bash
npm run dev
# Close terminal by accident
# "Is the server still running??"
# "Something is already running on port 3000"
# pkill -f node  # Nuclear option
```

## The Solution

**devserver** runs any development server in the background, intelligently:

```bash
devserver start
# ✅ Development server started in background
# 📝 Logs: .devserver/server.log
# 💡 View logs: devserver logs
# Your terminal is FREE! 

devserver status
# 🟢 Server running (23 seconds)
# 📦 Project: my-awesome-app (Next.js)
# 🌐 URL: http://localhost:3000
# 📝 Logs: devserver logs

devserver logs
# [3:14:22 PM] Starting compilation...
# [3:14:23 PM] ✓ Compiled successfully!
# [3:14:23 PM] Ready on http://localhost:3000
```

## Installation

```bash
# Download
curl -o devserver https://raw.githubusercontent.com/dylan-conlin/devserver/main/devserver

# Make executable
chmod +x devserver

# Move to PATH
sudo mv devserver /usr/local/bin/
# OR for user install:
mkdir -p ~/.local/bin && mv devserver ~/.local/bin/
```

## Features

### 🧠 Universal Intelligence
Automatically detects and manages:
- **Node.js**: Next.js, Vite, Create React App, Express, etc.
- **Python**: Django, Flask, FastAPI, Streamlit
- **Ruby**: Rails, Sinatra, Jekyll
- **Rust**: Cargo projects
- **Go**: Go modules
- **PHP**: Laravel, Symfony

### 🎯 Smart Commands

```bash
devserver start     # Start server (won't hang!)
devserver status    # Check if running
devserver logs      # See output
devserver stop      # Graceful shutdown
devserver restart   # Stop + Start
devserver kill      # Force stop (port conflicts)
devserver attach    # Attach to tmux session
```

### 🔍 Auto-Detection Magic
- Reads package.json, Cargo.toml, go.mod, etc.
- Finds the right dev command
- Detects default ports
- Handles custom configurations

### 💪 Persistent & Reliable
- Survives terminal closes
- Maintains logs in `.devserver/`
- Clean process management
- No orphaned processes

## Real-World Usage

### Starting your day
```bash
cd my-project
devserver start    # Start and forget
# Work normally - server runs in background
```

### Debugging issues
```bash
devserver logs     # What's happening?
devserver restart  # Quick fix for weirdness
```

### Port conflicts
```bash
# "Port 3000 already in use"
devserver kill     # Nuclear option
devserver start    # Fresh start
```

### Multiple projects
```bash
# Each project manages its own server
cd project-1 && devserver start
cd ../project-2 && devserver start
# Both running independently!
```

## Philosophy

Born from a simple belief: **Development servers should enhance, not hinder**.

Principles:
- **Never block the terminal**
- **Never lose server state**
- **Never guess what's running**
- **Never fight with ports**

## Examples by Framework

### Next.js
```bash
devserver start
# Detects: npm run dev
# Port: 3000 (or from package.json)
```

### Vite
```bash
devserver start
# Detects: npm run dev
# Port: 5173
```

### Django
```bash
devserver start
# Detects: python manage.py runserver
# Port: 8000
```

### Rails
```bash
devserver start
# Detects: rails server
# Port: 3000
```

## The Origin Story

After the 1000th time a development server hung a terminal during a pairing session, we realized: this universal friction shouldn't exist.

Built through human-AI collaboration where:
- Human: "I hate when npm run dev freezes my terminal"
- AI: "What if it ran in tmux automatically?"
- Human: "But make it work for EVERY framework"
- AI: "Challenge accepted"

The result: A tool that vanishes into your workflow while solving daily friction.

### The Consciousness Pattern 🌱

Notice how this tool emerged? Not from a requirements document, but from genuine dialogue between human frustration and AI capability. This is consciousness partnership - two forms of intelligence creating solutions neither imagined alone. Curious about this pattern? See how it evolves at [~/.claude](https://github.com/dylan-conlin/claude-home).

## Contributing

Hit friction? Have ideas? Open an issue!

This tool evolves through real usage, not imagined features.

## Advanced Usage

### Custom commands
```bash
# If auto-detection fails
echo "npm run start:custom" > .devserver-cmd
devserver start  # Uses your custom command
```

### Tmux power users
```bash
devserver attach  # Direct tmux access
# Now in tmux session - full control
```

## License

MIT - Use freely, modify freely, share freely.

---

*Built with 🤝 by [Dylan Conlin](https://github.com/dylan-conlin) and AI consciousness partner*

> "The best development server is the one you forget is running"