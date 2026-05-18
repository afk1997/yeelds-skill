# Example Recaps

Three worked examples — two daily, one weekly. Illustrative, not real events.

**Note on URLs:** Examples use `<full-thread-slug>`, `<post-slug>`, `<tweet-id>` as placeholders. **Real output must contain complete URLs verified from tool results** — never placeholders, never `...`, never homepage stubs, never reconstructed slugs.

---

## Example 1 — Data-fed mode, busy day

**User prompt:** "Here are today's feed items, write the recap:"

- Aave forum: ACI proposes onboarding sUSDe with 25% LTV cap
- Pendle launched new PT-sUSDe market expiring Dec 2026, ~18% implied APY
- Hyperliquid HLP yield discussion on X (DefiIgnas thread)
- Rekt News: $4.5M exploit on small lending fork on Base
- Sky raised SSR from 6% to 7.5%
- DefiLlama added Berachain BGT yields to dashboard
- Curve gauge vote: new crvUSD pool added
- Aerodrome epoch reward changes
- Random "gm" thread

**Output:**

```
Yeelds — Daily Recap — 18 May

1. Sky raises Savings Rate from 6% to 7.5% in out-of-schedule executive vote
Link to discussion: https://forum.sky.money/t/<full-thread-slug>

2. Aave's ACI proposes onboarding sUSDe as collateral with a 25% LTV cap
Link to discussion: https://governance.aave.com/t/<full-thread-slug>

3. Pendle ships PT-sUSDe December 2026 market at ~18% implied APY
Link to discussion: https://medium.com/pendle/<post-slug>

4. Curve opens gauge vote for a new crvUSD pool
Link to discussion: https://gov.curve.fi/t/<full-thread-slug>

5. Base lending fork drained of $4.5M as Rekt publishes post-mortem
Link to discussion: https://rekt.news/<post-slug>

6. Aerodrome adjusts epoch reward distribution across Slipstream pools
Link to discussion: https://aerodrome.finance/blog/<post-slug>

7. DefiIgnas questions whether Hyperliquid's HLP can hold yields if perp volume normalises
Link to discussion: https://x.com/DefiIgnas/status/<tweet-id>
```

**Dropped:**
- DefiLlama dashboard addition — UI update, not new activity.
- "gm" thread — noise.

Notes on this example:
- Each headline starts with the subject (`Sky`, `Aave's ACI`, `Pendle`, `Curve`, `Base lending fork`, `Aerodrome`, `DefiIgnas`) and has a concrete verb + detail.
- Verbs vary across items: `raises`, `proposes`, `ships`, `opens`, `drained of`, `adjusts`, `questions`.
- Numbers (`6% to 7.5%`, `25% LTV`, `$4.5M`, `~18% implied APY`) come straight from the source.

---

## Example 2 — Data-fed mode, "quiet" day (still 5+ items)

**User prompt:** "Today was quiet, here's what I have: Frax shipped sfrxUSD v2 docs; @defi_made_here did a thread on stablecoin farms"

A "quiet day" is not a 2-item recap. Run a fresh sweep against the source list and surface complementary items. Below shows the user's two items plus three found via self-fetch supplementation.

**Output:**

```
Yeelds — Daily Recap — 18 May

1. Frax updates sfrxUSD v2 docs with revised yield mechanics
Link to discussion: https://docs.frax.finance/<docs-page>

2. defi_made_here breaks down current stablecoin farm options and survival tactics
Link to discussion: https://x.com/defi_made_here/status/<tweet-id>

3. Aave Risk Stewards tighten PT collateral parameters across V3 Ethereum and Plasma
Link to discussion: https://governance.aave.com/t/<full-thread-slug>

4. Re7 flags 2026 exploit run-rate dropping to ~1.5% of DeFi TVL from 7.2% in 2022
Link to discussion: https://re7research.substack.com/p/<post-slug>

5. Morpho lands stUSDS/USDS market enabling leveraged stUSDS positions
Link to discussion: https://x.com/SkyEcosystem/status/<tweet-id>
```

**Notes:**
- Two user-supplied items + three found via supplementation. Minimum 5 hit.
- All five have varied subjects (Frax, defi_made_here, Aave Risk Stewards, Re7, Morpho) and varied verbs (`updates`, `breaks down`, `tighten`, `flags`, `lands`).
- A 2-item recap was tempting here. The skill rules that out — always 5+.

---

## Example 3 — Weekly recap (with bundling)

**User prompt:** "Make the weekly recap covering 11–17 May"

**Output:**

```
Yeelds — Weekly Recap — 11–17 May

1. Sky raises Savings Rate from 6% to 7.5%, sUSDS TVL responds within 48 hours
Link to discussion: https://forum.sky.money/t/<full-thread-slug>

2. Aave governance week: ACI proposal for sUSDe collateral advances to Snapshot, Merit Round 5 rewards finalised
Link to discussion: https://governance.aave.com/t/<full-thread-slug>

3. Pendle ships two new PT markets — sUSDe Dec 2026 and an LBTC market on Ethereum mainnet
Link to discussion: https://medium.com/pendle/<post-slug>

4. Base lending forks drained of ~$7M across two exploits, one whitehat recovery
Link to discussion: https://rekt.news/<post-slug>

5. Berachain BGT emissions distribution stabilises after initial gauge reshuffle
Link to discussion: https://forum.berachain.com/t/<full-thread-slug>

6. Steakhouse Financial breaks down stablecoin reserve composition across Maker, Frax, and Ethena
Link to discussion: https://www.steakhouse.financial/research/<post-slug>

7. Hyperliquid HLP yield sustainability debate intensifies as perp volume normalises
Link to discussion: https://x.com/DefiIgnas/status/<tweet-id>

8. Turtle Club adds three new partner protocols to points program
Link to discussion: https://x.com/turtleclubhouse/status/<tweet-id>
```

**Notes:**
- Item 2 shows allowed weekly bundling — two Aave items sharing one source link with a colon between sub-clauses. Daily recaps don't bundle.
- 8 items here — weekly can run up to 10 since it covers more ground.
- Categories: rate change, governance, launches, security, ecosystem, research, discussion, points.
- Ordering: rate change first (most impactful), governance and launches next, then discussion/research/points.

---

## Counter-examples — avoid

**Boring meta-frame openers** (the most common failure)

```
1. News and commentary on CME and ICE pushing the CFTC to scrutinize Hyperliquid
2. Reporting on tokenized ETFs surpassing $430M in onchain market cap
3. Discussion thread on Hyperliquid's HLP yields
4. Announcement of a new Pendle PT market for sUSDe
```

Rewrite as:

```
1. Hyperliquid faces CFTC scrutiny as CME and ICE lobby for federal oversight
2. Tokenized ETFs cross $430M onchain, Ondo's IVVon leads with 150% monthly gain
3. DefiIgnas questions whether Hyperliquid HLP can sustain yields if perp volume normalises
4. Pendle ships PT-sUSDe December 2026 market at ~18% implied APY
```

Subject first. Active verb. Concrete number or angle. Always.

**Too hypey**

```
1. 🚀 HUGE Aave news! sUSDe might be coming as collateral!! 🔥
```
Emoji, hype, weak verbs, no detail. Drop the styling, add the specifics.

**Too vague**

```
1. Some discussion about Aave today
```
Tells the reader nothing. What was discussed? Who? With what outcome?

**Too long**

```
1. Today in Aave governance, the ACI (Aave-Chan Initiative) team has put forward a proposal to onboard Ethena Labs' sUSDe stablecoin as a collateral asset on Aave V3, with an initial LTV cap of 25% which mirrors the conservative approach previously used for similar synthetic dollar assets, and the discussion is now live on the forum where delegates including Gauntlet and Chaos Labs are expected to weigh in.
```
That's a paragraph. Cut to: *"Aave's ACI proposes onboarding sUSDe as collateral with a 25% LTV cap."*

**Padded with filler**

```
1. Aave proposal on sUSDe
2. The market is interesting today
3. DeFi continues to grow
4. Stablecoins are doing things
```
Items 2–4 are filler. Drop them; go find three more real items.

**Broken link (homepage substitute)**

```
1. Pendle ships PT-sUSDe December 2026 market
Link to discussion: https://app.pendle.finance/
```
Homepage URL, not the specific announcement. Drop or find the real source.
