# Source Priorities for Yeelds Recap (EVM-only)

Ranked source list for self-fetch mode. All sources reachable via `WebSearch` or `WebFetch` — no APIs, no subgraphs, no RPC.

**Hit P0 first** (newsletters and protocol blogs — pre-aggregated, dated, first-party). Move to P1/P2 only if P0 doesn't yield enough verified candidates. Stop when you have 6–10 dated, EVM-relevant candidates.

If a URL 404s, search for the source name to find the replacement — never guess a new URL.

---

## P0 — Always check

### Curator newsletters & Substacks

Highest signal-to-noise. Pre-aggregated digests with specific URLs and confirmed publish dates.

- **Re7 Research Weekly** — `https://re7research.substack.com/` (institutional DeFi yield + risk, weekly)
- **Bankless** — `https://www.bankless.com/` (homepage feed carries the freshest dated articles; not `/newsletter`)
- **DeFi Saver Newsletter** — `https://blog.defisaver.com/` (monthly recap with position-of-the-month; strong on Aave/Spark/Morpho)
- **P2P.org DeFi Dispatch** — `https://p2p.org/economy/` (twice-monthly institutional roundup; RWAs, ETFs, regulatory)
- **The Defiant Daily** — `https://thedefiant.io/newsletter/defi-daily`
- **Dynamo DeFi** — `https://newsletter.dynamodefi.com/` (weekly on-chain analysis)
- **Blockworks 0xResearch** — `https://blockworks.co/newsletter/0xresearch` (weekday research)
- **DeFi Pulse Farmer** — `https://yieldfarmer.substack.com/` (weekly yield digest)
- **DeFi Education Fund Debrief** — `https://defieducationfund.substack.com/` (weekly; policy/regulation focus — useful for context, not yield)

### Protocol blogs (first-party, dated)

- **Morpho** — `https://morpho.org/blog/` (monthly "Morpho Effect")
- **Lido** — `https://blog.lido.fi/`
- **Aave** — `https://aave.com/blog`
- **Pendle** — `https://medium.com/pendle` (Medium + X `@pendle_fi`. No `pendle.finance/blog` path exists — don't construct one.)
- **Ethena** — `https://ethena.fi/blog`
- **EigenLayer / EigenCloud** — `https://blog.eigencloud.xyz/tag/eigenlayer/` is the current blog after the EigenCloud rebrand. Older posts may still live at `blog.eigenlayer.xyz`.

Some protocols have no dedicated blog path:

- **Sky / Maker** — use forum `https://forum.sky.money/` + governance portal `https://vote.sky.money/` + X `@SkyEcosystem`
- **Spark** — use `https://spark.fi/` (homepage updates) + `https://docs.spark.fi/` + X `@sparkdotfi`

### Governance forums

Best source for concrete events (proposals, votes, rate changes). Search with `site:<domain> <topic>` or `WebFetch` the recent-activity page.

- **Aave** — `https://governance.aave.com/` (ARFC, AIP)
- **Compound** — `https://www.comp.xyz/`
- **Curve** — `https://gov.curve.fi/` (alt `gov.curve.finance/`) — gauge proposals, fee distribution
- **EigenLayer** — `https://forum.eigenlayer.xyz/`
- **Morpho** — `https://forum.morpho.org/`
- **Sky / Maker** — `https://forum.sky.money/` + `https://vote.sky.money/`
- **Arbitrum** — `https://forum.arbitrum.foundation/` (STIP, LTIPP)
- **Optimism** — `https://gov.optimism.io/`
- **Berachain** — `https://forum.berachain.com/` (UI at `hub.berachain.com/governance/`)
- **Frax** — `https://gov.frax.finance/`
- **Balancer** — `https://forum.balancer.fi/`
- **Lido** — `https://research.lido.fi/` (not `forum.lido.fi` — doesn't exist)

### Newsrooms (specific article URLs)

Use after newsletters/blogs. Cleanest for breaking news, but snippets often re-surface old articles — verify dates carefully.

- **The Defiant** — `https://thedefiant.io/`
- **Blockworks (DeFi)** — `https://blockworks.co/category/defi`
- **The Block (DeFi)** — `https://www.theblock.co/category/defi`
- **Unchained** — `https://unchainedcrypto.com/news/`
- **Rekt News** — `https://rekt.news/` (exploits, post-mortems)
- **CoinDesk** — `https://www.coindesk.com/` — homepage scan only. Never construct article URLs from headlines; every CoinDesk article must come from a search result with the full slug.

### Protocol X accounts

Real and active. The URL for any specific announcement must come from a search result — never construct `x.com/<handle>/status/<id>` from memory.

@aave · @CurveFinance · @ethena_labs · @HyperliquidX · @MakerDAO · @SkyEcosystem · @morpholabs · @pendle_fi · @sparkdotfi · @LidoFinance · @Re7Capital · @DeFiSaver

---

## P1 — Strong supporting sources

### Curators / analysts (X)
@DefiIgnas · @TheDeFinvestor · @thedefiedge · @defi_made_here · @patfscott · @DefiLlama

### Security / incident feeds
@RektHQ · @peckshield · @samczsun · @spreekaway

### EVM L2 / chain ecosystem
@aerodromefi (Base) · @VelodromeFi (Optimism) · @arbitrum · @base · @berachain · @SonicLabs · @unichain · @LineaBuild · @scroll_zkp

### Restaking / LRT / LST
@eigenlayer · @ether_fi · @LidoFinance · @symbioticfi · @karak_network · @PufferFinance · @swellnetworkio

### RWA / stablecoin yield
@ondofinance · @resolv_im · @usual_money · @maplefinance · @SyrupFi

---

## P2 — Fill only when needed

### Additional EVM protocols
@ConvexFinance · @eulerfinance · @0xfluid · @gearboxprotocol · @GMX_IO · @SiloFinance · @synthetix_io · @yearnfi

### Points / airdrop trackers
@merkl_xyz · @turtleclubhouse · @earnifi

### Risk managers / delegates
@AaveChan · @bgdlabs · @chaos_labs · @gauntlet_xyz · @LlamaRisk

### Reddit
`site:reddit.com/r/defi`, `site:reddit.com/r/ethfinance`

---

## What to drop

- **Solana-first items.** Jupiter, Kamino, Marginfi, Sanctum, Drift, Meteora, Orca, Raydium, Solend/Save, Saber. Even when an EVM protocol expands to Solana, the Solana side is not the lede.
- **Sui, Aptos, TON, Cosmos chains, BTC L2s.**
- **Price-action stories** without a substantive on-chain event behind them.
- **Funding-round announcements** without a concrete product/yield launch.
- **Generic market commentary**, daily TVL fluctuations, routine APY drift.

---

## Categories to try to cover

When the day is abundant, touch several — not all, not in fixed proportion:

1. Protocol launches / new products
2. Governance (proposals, votes, rate changes)
3. Yield / rate changes (SSR, sUSDe APY, gauge weight shifts)
4. Security / incidents (exploits, post-mortems, depegs)
5. Points / airdrops / incentives
6. Research / deep-dives
7. Ecosystem / chain news (L2 incentive programs, new EVM chain launches)
8. Community discussion

---

## Link selection rules

For each item's `Link to discussion:`:

1. Prefer the **first-party** source (forum thread, protocol blog, official tweet).
2. Otherwise the **original news article** (The Defiant, Blockworks, The Block, Rekt).
3. Otherwise the **original X post**.

Never link to a screenshot of a post. Never link to an aggregator's summary if the original is one click away. The URL must point to the specific article/thread/post — never a homepage, category page, or aggregator summary.
