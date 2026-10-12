# Paper day-trading log

_Simulated trades only, no real money. Updated 2026-10-12 07:47 PT. Strategy v1.0. Goal: show consistent results over 30 sessions before any real capital._

## Summary

- Sessions done: **2 / 30**
- Total P&L: **+$0.00** (avg/session +$0.00; target +$500/day)
- Trades: 0; win rate: **0%** (0W / 0L)
- Expectancy: **n/a (no trades yet)** per trade
- Rule-following: **100%** of trades
- Risk rules (fixed): $250 risk/trade, -$750 daily stop, max 3 trades, long only, no margin.

## Session 2: 2026-10-12

Day P&L **+$0.00**, running **+$0.00**, fills 0

**Session notes**

_Session in progress (as of 10:44 ET); final results and review after the close._

- Watchlist: CRM, IREN, ASTS, TRMD, DHT (all long setups).
- IREN ORB: paper buy-stop 230 sh @ 36.71, stop 35.74 (~$223 risk), target 2R 38.66. It never triggered and was cancelled when the ORB entry window closed at 10:30 ET.
- No fills so far. VWAP-reclaim setups can still trigger later in the session.

**Daily review**

_Review pending._

## Session 1: 2026-10-09

Day P&L **+$0.00**, running **+$0.00**, fills 0

**Session notes**

- 10:16 monitor: SAIQ ORB armed (OR 5.98-6.53, buy-stop 6.55, stop 5.96, 381 sh, $225 risk). Paper submit at 10:17 REJECTED: last 5.83 was already below the 5.96 stop. 10:30 entry window then closed without a trigger (day high 6.53, never reached 6.55; low 5.23).
- HUM: no setup all morning. Opening range (9:30-9:35) 434.29-453.50 = $19.21 wide vs ATR14 $15.18 (1.27x ATR; rule caps it near 0.5x ATR), so ORB skipped. No VWAP reclaim: at 10:39 last ~431-434 vs VWAP ~442.6, and below the 437.62 pre-market low.
- NN ORB invalidated (closed back inside range). BIAF ORB was a short; Phase 1 is long-only. ALHC, NEA, HASI, PCRX: no setup.

**Daily review**

**What went right:** The risk checks worked. The SAIQ plan was rejected because price (5.83) was already below the planned stop (5.96), so we didn't buy into a broken setup. HUM was skipped correctly because its opening range (1.27× ATR) was far beyond the 0.5× ATR cap. No rule was broken.

**What went wrong:** Zero fills. The watchlist had 8 names and none produced a valid long. The SAIQ plan was armed at 10:16 when price had already collapsed through the range, so the monitor spent time on a dead setup.

**Constructive critique:** Session 1 is one data point; a flat day says nothing about edge. The watchlist quality is the bottleneck: several names (BIAF short, NN invalidated) were never going to be long trades under Phase 1 rules.

**Proposed change (not adopted yet):** Have the monitor drop an ORB candidate once price closes below its opening-range low, instead of arming it. Will only adopt if this pattern repeats over the next sessions. Rules unchanged.

## Strategy changelog

Current version: **v1.0** (2026-10-09). Change rules: one small change at a time, each justified by journal data with the evidence cited, never loosening risk-rules.md ($250 risk/trade, −$750 daily stop, 3 trades max, long only, no margin, size steps up only after 30+ sessions and 60+ trades). Changes to filters/entries are re-checked after at least 5 sessions before another change to the same setup.

| Version | Date | Change | Evidence | Status |
|---|---|---|---|---|
| v1.0 | 2026-10-09 | Baseline: ORB long + VWAP reclaim long (min stop 0.25× ATR). Gap fill and VWAP short dropped. | Backtest showed no edge for gap fill / VWAP short | Active |
| v1.0 | 2026-10-12 | No change after session 1 (only 1 session, 0 fills: too little data). | — | — |
