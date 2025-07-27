---
layout: post
title: "A Better Day for Unix Admin"
date: 2025-07-27 06:00:00 +0000
tags: [tools, shell, productivity, unix]
---

Managing shell environments across multiple hosts and sessions is often a hassle: copying configs, syncing plugins, handling differences between machines…

But what if your shell environment could **travel with you**, instantaneously, intact, and on-demand?

Meet **thefly** and **shell‑ng**, two tools from my [joknarf suite][tools-page] that make your shell environment **transportable, consistent, and productivity‑centric** — wherever you are.

---

## 🌍 Meet **thefly**

[thefly][thefly] is a **shell teleporter and plugin manager** for bash, zsh, and ksh:

- Install it via:
  ```bash
  . <(curl -s https://raw.githubusercontent.com/joknarf/thefly/main/thefly) install
  ```
- Manages your shell environment in `~/.fly.d`, loads plugins (.plugin.bash/.zsh/.ksh), and sources them upon login.

### Teleport your full environment:
```bash
flyto user@remote
```
Simply run this, and **your entire shell config and plugins** appear on the remote machine—no manual copy.

You can also `fly as <user>` on the same host, or `flysh zsh` to launch a new shell with your transported setup.

---

## 🛠 Shell‑NG: Next‑Gen shell plugins on demand

**shell‑ng** is the plugin collection layer that powers your next-gen shell experience. It includes multiple highly interactive and modern plugins:

- `complete-ng`: command‑line completion menu with a selector UI  
- `seedee`: directory history navigation via Ctrl/Shift arrows  
- `redo`: interactive command history menu (Shift-Tab)  
- `pgtree`: process search, hierarchy, and management from your shell prompt  
- `nerdps1`: ultra‑rich powerline prompt, transportable via thefly

You activate shell-ng plugins by running:
```bash
fly add joknarf/shell-ng
```
or by installing them individually.

---

## 🚀 Real-world Workflow

1. **Install thefly** in your local shell (bash/zsh/ksh).
2. Add plugins:
   ```bash
   fly add joknarf/seedee
   fly add joknarf/complete-ng
   fly add joknarf/nerdps1
   ```
3. **Teleport your environment**:
   ```bash
   flyto user@serverX
   ```
   You are now on `serverX`, with your prompt, completion engine, history tools… everything.

4. **Switch shells** seamlessly:
   ```bash
   flysh bash       # or fzsh, fksh
   ```

5. **Remote or local commands still use your setup**—consistent experience everywhere.

---

## 🔍 Why It Works

| Feature            | Benefit |
|--------------------|---------|
| Portable config    | `~/.fly.d` holds your shell & plugins in a unified layout |
| Teleportable       | `flyto` copies your full setup via SSH to remote hosts |
| Plugin-driven      | You pick only what you need (seedee, redo, complete-ng…) |
| Shell‑agnostic     | Works on bash, zsh, and ksh reliably |
| Standalone-ready   | No installation needed on remote hosts, only SSH access |

---

## ✍️ Summary

With **thefly** and **shell‑ng**, a Unix admin can:

- Maintain one environment that travels.
- Have a polished shell experience with modern tools.
- Stay lightweight: no dotfiles scattered across hosts.
- Use the same commands and UI from laptop to server.

It’s like having your personal shell **in your pocket**—ready wherever you log in.

---

## 📦 Try it yourself

```bash
curl -s https://joknarf.github.io/joknarf-tools/thefly | bash
fly add joknarf/shell-ng
flyto user@remote
```

Whether you’re managing servers, jumping through SSH tunnels, or just want a powerful shell environment that **moves with you**, this combo makes it simple—and pleasurable.

[tools-page]: https://joknarf.github.io/joknarf-tools/  
[thefly]: https://github.com/joknarf/thefly/  
[x-shell-ng]: https://github.com/joknarf/shell-ng/

