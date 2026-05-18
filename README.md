# yeelds-daily-recap

A Claude Code skill for composing the **Yeelds daily/weekly DeFi recap** — a scan-friendly numbered list of the most noteworthy things happening in DeFi on EVM chains, formatted for direct distribution on Telegram and X.

## What it does

Given either:
- a **list of items/links** (data-fed mode), or
- a request like *"write today's recap"* with no items supplied (self-fetch mode),

the skill researches across newsletters, protocol blogs, governance forums, X accounts, and crypto newsrooms, then writes a punchy newsletter-style post:

```
Yeelds — Daily Recap — DD Month

1. [Subject-first newsletter headline with concrete detail]
Link to discussion: [specific verified URL]

2. ...
```

Coverage is **EVM-only** (Ethereum, Arbitrum, Base, Optimism, Berachain, HyperEVM, Sonic, Unichain, Linea, Scroll, etc.). Solana, Sui, Aptos, TON, Cosmos, and BTC L2s are explicitly out of scope.

## Install

Drop the directory into your Claude Code skills folder:

```bash
git clone https://github.com/afk1997/yeelds-skill ~/.claude/skills/yeelds-daily-recap
```

Then invoke it by asking Claude things like:

- *"write today's Yeelds recap"*
- *"make the daily DeFi digest"*
- *"summarize the feed"* (with items pasted)
- *"weekly recap for 11–17 May"*

## Repo layout

```
.
├── SKILL.md                       # main skill — rules, format, workflow, effort floor
└── references/
    ├── source-priorities.md       # ranked source list (P0/P1/P2) for self-fetch
    └── example-recaps.md          # worked examples in the headline style
```

## Design notes

- **The Iron Rule:** every URL, number, name, date, and dollar amount must come from a tool result. No fabrication.
- **Publication date governs freshness** — a fresh article today about an older event counts as today's news.
- **Minimum 5 items, target 5–7** — no "quiet day" 2-item exits. If the first sweep is thin, run a second sweep targeting different angles.
- **Headline style:** subject-first, active verb, concrete detail. No "News and commentary on…" / "Reporting on…" / "Discussion on…" openers.
- **Effort floor:** a comprehensive parallel sweep across newsletters, protocol blogs, governance forums, X accounts, security feeds, and newsroom homepages — 30+ tool calls before declaring a quiet day.
