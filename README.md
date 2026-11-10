# TUI Widgets: Live Panels for the Hermes Dock

> Author live widget apps for a terminal dashboard: real-time data, custom layouts, and the lifecycle hooks that keep a panel updating without leaking processes.

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg) ![Claude Code](https://img.shields.io/badge/Claude_Code-skill-blueviolet.svg)

## What it does

Author live widget apps for the Hermes TUI dock.

Author widget apps for the Hermes TUI (`hermes --tui`): glanceable ambient
panels docked above the status bar, or modal overlays that own the keyboard.
Widgets are plain ESM files the TUI loads at startup — no build step, no
repo changes. This skill does not cover desktop-app or web-dashboard
widgets.

## The failure it prevents

The cases that cost time are specific, and they are written down:

- No JSX and no bare imports in `.mjs` — everything comes from the `sdk`
- Don't ship a modal without a close path (`Esc`/`q` returning `null`).
- Ambient widgets must stay small (≤ ~6 rows) — the dock sits between the
- A thrown `register()` is logged and skipped; check

## When to use it

- The user asks for a live panel in the TUI (ticker, clock, countdown,
- The user wants a custom modal tool (picker, calculator, viewer) bound to

## What's inside

```
plugins/
└── tui-widgets/
    ├── .claude-plugin/plugin.json
    └── skills/tui-widgets/
        ├── SKILL.md
        ├── templates/              (1 files)
```

## Install

Add this repo as a Claude Code marketplace, then install the skill:

```bash
claude plugin marketplace add Verstige/tui-widgets
claude plugin install tui-widgets@tui-widgets
```

Or copy the skill straight into your skills directory:

```bash
git clone https://github.com/Verstige/tui-widgets.git
cp -R tui-widgets/plugins/tui-widgets/skills/tui-widgets ~/.claude/skills/
```

## Usage

The skill activates on the work it describes. Ask for the outcome, and it
supplies the method:

```
> "Use the tui-widgets skill for this task."
```

## License

MIT. See [LICENSE](LICENSE).

Part of the [Verstige](https://github.com/Verstige) skills portfolio. More at [github.com/Verstige](https://github.com/Verstige).
