---
layout: post
title: "A Better Day for Unix Admin"
date: 2025-07-27 06:00:00 +0000
tags: [tools, shell, productivity, unix]
---

Unix Admin daily job is often a **painful experience**, as you may need to connect to many servers to perform various tasks, and you may face several issues:

- **Inconsistent environments**: different machines, different OSes, different users, different shell, different environment, different tools...
- **Manual work**: repetitive tasks, manual configuration, manual setup.

Even if you have setup a very cool shell environment locally with your favorite tools, plugins, and aliases, when connecting to a remote machine, you will just have a **plain shell** with no history, no aliases, no plugins, no nothing.

But what if your shell environment could **travel with you**, instantaneously, intact, and on-demand?

Meet **thefly** and **shell‑ng**, two tools from my [joknarf suite][tools-page] that make your shell environment **transportable, consistent, and productivity‑centric** — wherever you are.

---

## 🌍 Meet **thefly**

[thefly][thefly] is a **shell teleporter and plugin manager** for bash, zsh, and ksh:

![shell-ng3](https://github.com/user-attachments/assets/431d6d71-0d0a-4fbc-bcb8-738cb1832880)

- Install it via:
  ```bash
  . <(curl -s https://raw.githubusercontent.com/joknarf/thefly/main/thefly) install
  ```
- add your favorite plugins from github with `fly add <user/plugin>` (eg. `fly add joknarf/shell-ng`)
- Customize your shell environment in `~/.fly.d/.flyrc` (move your current environment setting there, and just put in your shell init file `. ~/.fly.d/fly source`)
- All your plugins and configs are stored in `~/.fly.d`, you can add files there (.vimrc, .inputrc, etc...), and they will be transported with you using flyto (ssh) and flyas (sudo)

### Teleport your full environment:

```bash
flyto user@remote
```
Simply run this, and **your entire shell config and plugins** appear on the remote machine—no manual copy.
Your local ~/.fly.d will be available in `$FLY_HOME` on the remote machine. (in /tmp/.fly.d.<user>/<flyid> by default), and you can even enforce the remote shell you want to use.

```bash
flyas user
```
You can also `flyas <user>` on the same host, or `flysh zsh` to launch a different shell with your transported setup.

---

## 🛠 Shell‑NG: Next‑Gen shell plugins on demand

**shell‑ng** is the plugin collection layer that powers your next-gen shell experience. It includes multiple highly interactive and modern plugins:

- `complete-ng`: command‑line completion menu with a selector UI  
- `seedee`: interactive directory history and navigation menu (Shift or Control DownArrow)
- `redo`: interactive command history menu (Shift-Tab)  
- `nerdp`: ultra‑rich powerline prompt

You activate shell-ng plugin by running:
```bash
fly add joknarf/shell-ng
```


---

## 🚀 Real-world Workflow

1. **Install thefly** in your local shell (bash/zsh/ksh).
2. Add plugins:
   ```bash
   fly add joknarf/shell-ng
   fly add .../...
   ```
3. **Teleport your environment**:
   ```bash
   flyto user@serverX
   ```
   You are now on `serverX`, with your prompt, completion engine, history tools… everything.
   ```bash
   flyas user
   ```
   You have now switched to `user` keeping your full shell environment.

4. **Switch shells** seamlessly:
   ```bash
   flysh bash       # or fbash, fzsh, fksh
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
- Use the same commands and UI from your home to server.

It’s like having your personal shell **in your pocket**—ready wherever you log in.

---

## 📦 Try it yourself

```bash
. <(curl https://raw.githubusercontent.com/joknarf/thefly/main/thefly) install
fly add joknarf/shell-ng
flyto user@remote
```

Whether you’re managing servers, jumping through SSH tunnels, or just want a powerful shell environment that **moves with you**, this combo makes it simple—and pleasurable.

[tools-page]: https://joknarf.github.io/joknarf-tools/  
[thefly]: https://github.com/joknarf/thefly/  
[x-shell-ng]: https://github.com/joknarf/shell-ng/

