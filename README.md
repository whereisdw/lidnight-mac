<p align="center"><img src="icon.png" width="96" alt="Lidnight icon"></p>

<h1 align="center">Lidnight</h1>
<p align="center"><b>Keep your MacBook awake with the lid closed while AI agents work — then let it sleep.</b><br>
Claude Code · Codex · Gemini CLI · Ollama · LM Studio and 40+ more · Apple Silicon · macOS 13+</p>

<p align="center">
<a href="https://lidnight.app/en/"><b>Website</b></a> ·
<a href="https://lidnight.app/download/Lidnight.dmg">Download (free)</a> ·
<a href="https://lidnight.app/en/security/">Security</a> ·
<a href="https://lidnight.app/en/guides/">Guides</a> ·
<a href="https://github.com/whereisdw/lidnight-mac/issues">Issues</a>
</p>

<p align="center"><a href="https://lidnight.app/en/"><img src="demo.jpg" width="720" alt="30-second demo: close the lid, Claude Code keeps working, approve from your phone, the Mac sleeps when it's done"></a></p>

```bash
brew install whereisdw/tap/lidnight
```

## Why

Close a MacBook with no external display and macOS sleeps — and your Claude Code / Codex run stalls a few minutes in. `caffeinate` only blocks *idle* sleep, and `sudo pmset -a disablesleep 1` works but stays on until you remember to undo it (heat, drained battery, a hot bag).

Lidnight turns lid-closed sleep prevention **on while agents are actually working, and off when they're done**.

## What it does

- **Lid closed, even on battery** — through a small helper that only runs a fixed list of power commands. A watchdog restores sleep settings if the app quits; after a power loss they're restored at the next boot.
- **Knows when the work is done** — Claude Code and Codex precisely via their hooks; 40+ other tools (Gemini CLI, Aider, Kiro CLI, Ollama, LM Studio…) from process and GPU activity. Sleeps 10 minutes after everything goes quiet.
- **Usage-limit waits** — when Claude Code hits its 5-hour limit it waits and continues on its own after the reset, but not if the Mac slept through it. Lidnight keeps the Mac awake until the reset.
- **Approve from anywhere** — answer Claude Code permission prompts from a Mac notification, the menu bar, a bunny next to the notch, or your phone (end-to-end encrypted; `rm -rf` / `git push` / `sudo` stay Mac-only).
- **Safety** — alert at 42 °C, sleep at 45 °C or at a battery floor you set.
- **Limits & usage** — Claude/Codex 5-hour and weekly limits, tokens and estimated cost, a bunny per agent in the menu bar.

<p align="center"><img src="menubar-approval.png" width="380" alt="Menu bar window with a Claude Code approval request"></p>

## Pricing

Free: AI Auto mode, battery & heat protection, approvals on the Mac.
Pro (one-time, no subscription): $9.99 for 1 Mac · $14.99 for 3 — **50% off through Oct 31, 2026**. Every download includes a 7-day Pro trial, no payment details needed. 14-day refund.

## Privacy

No account, no analytics. Your code and conversations never leave the Mac. Phone status is encrypted on the Mac (AES-GCM) and commands are one-time HMAC signatures — the relay can't read them. Details: https://lidnight.app/en/security/

## Support

Bug reports and feature requests: [open an issue](https://github.com/whereisdw/lidnight-mac/issues) or email support@dawonlabs.com.
This repository hosts the README and issue tracker; Lidnight itself is a closed-source, notarized app from Dawon Labs.
