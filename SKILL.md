---
name: yeelds-daily-recap
description: Use when composing a daily or weekly DeFi recap post — a numbered list of noteworthy EVM yield, governance, protocol, security, and incentive events for distribution on Telegram or X. Triggers on "daily recap", "weekly recap", "DeFi digest", "DeFi roundup", "summarize the feed", "today's post", "make the daily", or when handed a list of items/links to package as a recap.
allowed-tools: WebSearch, WebFetch, Read
---

# Yeelds Daily Recap

Compose the Yeelds daily/weekly recap: a scan-friendly numbered list of the most noteworthy things happening in DeFi on EVM chains. Output is plain text, posted directly to Telegram and X. It should read like a curated newsletter snippet, not like a chat response.

**Audience:** DeFi-native readers who already know what PT/YT, gauges, LRTs, restaking, and SSR mean. Don't translate jargon.

**Voice:** factual and informative with enough specificity to make a reader want to click. Punchy newsletter headlines — not press-release language, not chat-bot summaries, not editorialised hype.

## Scope: EVM-only

Cover EVM chains only — Ethereum, Arbitrum, Base, Optimism, Polygon, BNB Chain, Berachain, Sonic, HyperEVM, Unichain, Linea, Scroll, and similar. Drop any item whose primary subject is Solana, Sui, Aptos, TON, Cosmos chains, or Bitcoin L2s. If an item touches both EVM and non-EVM, include it only when the EVM angle is the lede.

## Two modes

| Mode | Trigger | What you do |
|---|---|---|
| **Data-fed** | User supplies items/links | Filter, rank, write. Trust user-supplied URLs but still freshness-check and EVM-check. |
| **Self-fetch** | User asks for "today's recap" with no items | Run the comprehensive sweep in `references/source-priorities.md`, then filter, rank, write. |

If ambiguous, treat as self-fetch and supplement with the supplied items.

## The Iron Rule: never fabricate

Every URL, number, name, date, and dollar amount in the output must come from a tool result in this conversation (a `WebSearch` result, a `WebFetch`, or a user message). If you didn't literally see it, you don't have it.

**Resist these temptations:**
- Guessing a slug because "the site uses this URL pattern"
- Rounding "roughly $4 billion" to "$4.2B" because it sounds more specific
- Inferring a publish date from search-result ordering
- Filling in details the snippet didn't show
- Quoting someone you didn't see speak

One fake URL destroys trust in the entire post. The Iron Rule is non-negotiable.

## Freshness — publication date governs

If a major outlet (DL News, CoinDesk, The Block, The Defiant, Bankless, Blockworks) publishes fresh coverage today on something — even something that originally happened weeks ago — that **is** today's news for recap purposes. Include it. Don't be pedantic about "the underlying event was three weeks ago" — readers care about what's being discussed *right now*, not just what's happening for the first time *right now*.

**Rule:** Use the **publication date** of the source (article, tweet, forum post, protocol blog) as the freshness anchor.

- **Daily recap:** include sources published in the past ~3 days (today + 2). Tight window, but not so tight that fresh analysis gets dropped.
- **Weekly recap:** include sources published in the past 7 days.

Anchor "now" to **today's date in UTC** unless the user specifies otherwise.

The one exception: if the **same** event has been recapped in a prior Yeelds post, don't recycle it just because someone re-shared the article. Fresh analysis = include; stale re-shares = drop.

**How to verify a publication date:**
- **Article:** `<time>` element, visible "Published" line, or date in URL slug (e.g. `/2026/05/16/…`). If unclear, `WebFetch` the page.
- **X / Twitter:** explicit date on the tweet. If you only have "3h" or "2d", `WebFetch` the tweet URL or read the homepage timestamp.
- **Forum:** post header has an absolute timestamp.
- **Protocol blog:** date on the post page.

If you cannot verify the publication date, drop the item.

## Link integrity

Every `Link to discussion:` URL must point to the **specific** article, forum thread, tweet, or post — never a homepage, category page, search-result page, or aggregator summary. If still unavailable after a follow-up search, drop the item.

## Output format

Output goes inside a fenced code block so the user can copy it cleanly:

```
Yeelds — Daily Recap — DD Month

1. [Punchy newsletter headline]
Link to discussion: [URL]

2. [Punchy newsletter headline]
Link to discussion: [URL]
```

- **Title line:** `Yeelds — Daily Recap — DD Month` (e.g. `18 May`). For weekly: `Yeelds — Weekly Recap — DD–DD Month` (e.g. `11–17 May`). Title dashes are em-dashes (U+2014 `—`). Date-range dash is an en-dash (U+2013 `–`).
- **Numbered list:** `1. `, `2. `, … No bullets, no sub-bullets.
- **Item line:** one punchy headline — see "Writing the headline" below.
- **Link line:** literally `Link to discussion: ` followed by the URL, on its own line directly under the item.
- **Blank line between items.**
- **Plain text only.** No emojis, hashtags, @mentions, images, intro sentence, or sign-off. The title is the first line; the last item's link line is the last.
- **Item count:** **minimum 5, target 5–7, cap at 8** per recap. If you can't surface 5 verified items, you haven't searched enough — run another sweep. See **Effort floor**.

After the code block you may add 1–2 short bullets noting what you dropped and why.

## Writing the headline

Each item is one **newsletter-style headline**, not a description-of-an-item.

**The reader should want to click.** Give them enough information density to be informative, with one concrete specific detail that creates intrigue.

### Format

- **Subject-first.** Lead with the protocol, person, or entity doing the thing — not with a meta-frame ("News on…", "Reporting on…", "Discussion of…").
- **Active verb.** What is the subject doing? Verbs: launches, raises, drops, faces, proposes, opens, ships, lands, migrates, tightens, exits, files, freezes, scrutinises, recovers.
- **Specific detail.** A number, a name, a percentage, a chain, an opposing party. Concrete > vague.
- **Length:** 8–18 words per headline. Hard cap 22.
- **No editorialising.** No "huge", "massive", "exciting", "shocking", "controversial". Specificity creates interest; adjectives don't.

### Good vs. bad

| Style | Example |
|---|---|
| ❌ Boring meta-frame | `News and commentary on CME and ICE pushing the CFTC to scrutinize Hyperliquid` |
| ✅ Subject + verb + detail | `Hyperliquid faces CFTC scrutiny as CME and ICE lobby for federal oversight` |
| ❌ Vague | `Some discussion about Aave today` |
| ✅ Specific | `Aave's ACI proposes onboarding sUSDe as collateral with a 25% LTV cap` |
| ❌ Hype | `🚀 HUGE Aave news! sUSDe might be coming!!` |
| ✅ Factual | `Aave votes underway to add PT-sUSDe August 2026 expiry to V3 Core and V4` |
| ❌ Press-release | `Launch of a new Pendle PT market for Ethena's sUSDe expiring December 2026` |
| ✅ Newsletter | `Pendle ships PT-sUSDe December 2026 market at ~18% implied APY` |
| ❌ Description-of | `Post-mortem of the Base-chain lending fork exploit` |
| ✅ Headline | `TrustedVolumes exploited for $5.87M via broken signer authorisation on Base` |
| ❌ Hedged | `Some kind of governance update happened on Sky` |
| ✅ Decisive | `Sky raises Savings Rate from 6% to 7.5% in out-of-schedule executive vote` |

### Verb cheat-sheet (rotate, don't repeat)

| Item type | Verbs to lead with |
|---|---|
| Protocol launch | `launches`, `ships`, `lands on`, `goes live with`, `rolls out` |
| Governance | `proposes`, `votes on`, `approves`, `rejects`, `files for`, `opens` |
| Rate / parameter change | `raises`, `cuts`, `tightens`, `loosens`, `adjusts`, `reduces` |
| Security incident | `exploited for`, `loses`, `drained of`, `pauses after`, `recovers` |
| Market / TVL milestone | `crosses`, `hits`, `surges to`, `surpasses`, `tops` |
| Research / analysis | `argues`, `flags`, `breaks down`, `traces`, `claims` |
| Regulatory / legal | `faces`, `pushes back on`, `responds to`, `files brief on`, `freezes` |
| Migration / integration | `migrates to`, `switches from`, `integrates with`, `adds`, `partners with` |

Vary verbs across items. Don't open three items with `launches`.

## Ordering

Order by impact, not chronology. Lead with the most interesting item:

1. Major protocol launches / rate changes
2. Regulatory / legal action affecting EVM DeFi
3. Governance proposals and votes
4. New pools / market launches
5. Security incidents / post-mortems
6. Market / TVL milestones
7. Research / deep-dives
8. Points / airdrops / incentives

Don't let one category dominate (e.g. seven Aave items in a row).

## Weekly format: bundling

Weekly recaps may bundle two closely related items from the same protocol/forum into one line with a colon. Daily recaps don't bundle — write them as separate items if they're separate.

## Selection filter

Apply in order. Drop liberally — bad items always lose to no items.

1. **EVM-only.** Drop non-EVM lede items.
2. **Freshness.** Drop items whose publication date is outside the recency window or unverifiable.
3. **Noise.** Drop portfolio brags, generic price commentary, memes, "gm" threads.
4. **First-party over commentary** (when both exist). A protocol's own announcement beats a screenshot of it.
5. **Concrete subject.** Specific protocol/proposal/event > "DeFi is heating up".
6. **Dedupe.** Same protocol + same topic within 48 hours = one item. Pick the strongest angle.
7. **Link integrity.** Drop items whose only available URL is a homepage or category page.

Items that look like noise but are actually content: fund-flow stories with a concrete size attached (e.g. a major fund exiting a position with on-chain proof) can qualify if it's actually being talked about. Use judgment — generic price commentary still drops.

## Workflow

1. **Date anchor.** Use today's UTC date in `DD Month` format unless the user specifies. Compute the recency window from that anchor.
2. **Mode.** Items supplied → data-fed. None → self-fetch.
3. **The Sweep** (self-fetch). Run the **comprehensive parallel sweep** described in the Effort Floor below. One coordinated dig, not iterative back-off. Aim to surface 12–20 candidates before filtering.
4. **Capture URLs as you go.** For each candidate, record the exact URL from the tool result alongside the headline. No URL = no item.
5. **Apply the selection filter.** Drop liberally.
6. **Pick the top 5–7 by impact and intrigue.** If you have fewer than 5 after the sweep, **run a second sweep targeting different angles** — do not declare a quiet day until you've tried twice with different keywords across the full source matrix.
7. **Write each headline.** Subject-first, active verb, concrete detail.
8. **Audit before output.** For each item:
   - *Did I literally see this URL in a tool result?*
   - *Is every number/name/date/amount from a tool result?*
   - *Is the publication date within the recency window?*

   Any "no" → drop the item, **then go find a replacement**. Don't ship under 5.
9. **Assemble.** Title → blank line → numbered items separated by blank lines. No preamble, no sign-off.
10. **Output in a code block.** Optionally add 1–2 short bullets after the block noting drops and reasons.

## Effort floor — don't phone it in

**Don't be a lazy ass fuck. Dig deeper for more sources.**

You are responsible for producing **5–7 fresh items, every run**. Coming back with 2 because "the weekend was quiet" is unacceptable. There is always EVM DeFi signal — finding it is the job.

### Search everything once, then synthesise

Don't search a few sources, audit, drop, and bail. Do this instead:

**Sweep 1 — parallel comprehensive scan (run all of these in one batch):**

- **Newsletter Substacks:** Re7 Research, DeFi Saver, P2P.org DeFi Dispatch, Bankless, Dynamo DeFi, Blockworks 0xResearch, DeFi Pulse Farmer, The Defiant Daily
- **Protocol blogs:** Morpho, Lido, Aave, Pendle (Medium), Ethena, EigenCloud, Spark docs/forum, Frax news
- **Governance forums:** `site:governance.aave.com`, `site:forum.morpho.org`, `site:forum.sky.money`, `site:gov.curve.fi`, `site:forum.eigenlayer.xyz`, `site:gov.optimism.io`, `site:forum.arbitrum.foundation`, `site:forum.berachain.com`, `site:gov.frax.finance`, `site:forum.balancer.fi`, `site:research.lido.fi`
- **Newsroom homepages:** `WebFetch` thedefiant.io, bankless.com, blockworks.com/category/defi, theblock.co/category/defi, rekt.news, coindesk.com — read the dated headline list directly
- **X handles:** `site:x.com pendle_fi`, `site:x.com morpholabs`, `site:x.com aave`, `site:x.com SkyEcosystem`, `site:x.com ethena_labs`, `site:x.com HyperliquidX`, `site:x.com CurveFinance`, `site:x.com LidoFinance`, `site:x.com sparkdotfi`
- **Security feeds:** `site:rekt.news`, `site:x.com RektHQ`, `site:x.com peckshield`, `site:x.com samczsun`, `site:x.com ZachXBT`

That is **30+ searches/fetches** in the first sweep. Run them in parallel batches. Don't trickle them in.

**Sweep 2 — targeted dig (only if Sweep 1 yielded <8 candidates):**

- Search the specific protocols that *weren't covered* — Berachain BGT vaults, Pendle Boros, EigenCloud AVS launches, Spark Liquidity Layer, Linea Ignition, Aerodrome Slipstream, Hyperliquid HLP
- Re-fetch newsroom homepages with different prompts asking for the freshest items
- Search `"<today's date>" DeFi` and `"<yesterday's date>" DeFi` directly
- Try curator-analyst X accounts (`site:x.com DefiIgnas`, `site:x.com TheDeFinvestor`, `site:x.com defi_made_here`)

**Sweep 3 — only if you still have <5 (this should be rare):**

- Try regional crypto news outlets (CryptoSlate, Decrypt, Cointelegraph)
- Try DefiLlama news, Messari news, CoinGecko news
- Try Reddit (`site:reddit.com/r/defi`, `site:reddit.com/r/ethfinance`)

### Lazy behaviour that produces shit recaps

- Running 3–5 news-site searches and concluding "nothing's happening today"
- Hitting only one source category and stopping
- Skipping protocol blogs because they "feel like marketing"
- Skipping governance forums because they're noisier
- Skipping X account searches because tweets are harder to verify
- Treating "I couldn't find anything fresh" as a finished answer
- Pivoting to a "quiet day" 2-item output after one round
- Applying recency rules so strictly that fresh analysis of older events gets dropped (see Freshness section — publication date governs)
- Dropping items whose URL you could find with one more search

### What lazy looks like — verbatim

> "I've done 26 tool calls and only have 1 verified item. The skill says short honest recap is OK on quiet days." — **WRONG.** You haven't run all 30+ first-sweep queries. Go finish the sweep before claiming quiet.

> "The article is from May 16 but the underlying event is from April, so per skill rules I drop it." — **WRONG.** Fresh published analysis = fresh item. Publication date governs.

> "I can't WebFetch the article body because it 403'd, so I can't verify the date." — **PARTIAL.** If the URL contains a date slug (`/2026/05/16/…`) or appeared in a homepage scan with a relative timestamp ("2 days ago"), that's verifiable. Use it.

### Minimum item count is a hard rule

**Never ship under 5 items.** If after two full sweeps you still have <5, output an honest note inside the code block ("Sweep returned only N strong items — running a third pass") and keep digging. Do not finalise under 5.

## Past-date recaps

For "yesterday's recap" or "recap for 14 May": anchor recency to the specified date, not today. Daily window = the specified day's content + the preceding ~2 days.

## References

- `references/source-priorities.md` — ranked source list
- `references/example-recaps.md` — worked examples in the new headline style

## Common mistakes

| Mistake | Fix |
|---|---|
| Headline opens with "News and commentary on…", "Reporting on…", "Report covering…", "Discussion on…", "Announcement of…", "Launch of…" | Rewrite subject-first with an active verb. See **Writing the headline**. |
| URL ends in `/...` or matches a guessed slug | Drop the item. |
| Item uses "huge", "massive", "exciting", "controversial" | Rewrite with specificity. Adjectives don't create interest; numbers and names do. |
| Two items both about Aave governance | Pick the bigger one (daily) or bundle (weekly). |
| Headline is two sentences | Cut to one or split into two items. |
| Shipped 2 items because "the weekend was quiet" | Run a second sweep. Minimum 5. |
| Hit P0 only, never pivoted to P1/P2 | Mandatory pivot — curator X accounts, security feeds, L2 ecosystem accounts. |
| Stopped at "quiet day" after one round | Run the 30+ source comprehensive sweep first. |
| Dropped a fresh May 16 article because the underlying event was in April | **Publication date governs.** Fresh analysis = include. |
| Solana headline made it in | Drop. EVM-only. |
| Padded with "DeFi continues to grow" | Drop. Specific items only. |
| `...` left in a real-output URL | Drop the item. Examples use placeholders; output must have complete URLs. |
