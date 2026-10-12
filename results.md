# Paper day-trading log

_Simulated trades only, no real money. Updated 2026-10-12 13:36 PT. Strategy v1.0. Goal: show consistent results over 30 sessions before any real capital._

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

_Final (after the 4:00 PM ET close)._

- Watchlist: CRM, IREN, ASTS, TRMD, DHT (all long setups).
- IREN ORB: paper buy-stop 230 sh @ 36.71, stop 35.74 (~$223 risk), target 2R 38.66. It never triggered and was cancelled when the ORB entry window closed at 10:30 ET.
- Final: no fills. No VWAP-reclaim long triggered; CRM and DHT stayed below or right at VWAP all morning. Day P&L $0.00, running total $0.00 after 2 of 30 sessions.

**Daily review**

**What went right:** The rules held. The one plan (IREN ORB buy-stop 36.71, about $223 risk) only would have filled on real strength, and IREN never got there: it faded to 34.83 (-4.1% open to close) and filled its gap. Missing that trade was the correct outcome. The hindsight check shows the other ORB longs (TRMD, ASTS) broke out and then closed back inside their ranges, so they'd have been small losers (-0.20R and -0.27R) that the invalidation rule cut early. No rule was broken.

**What went wrong:** Zero fills for the second session in a row. Four of five names on a gap-up watchlist faded below VWAP by the close, so the long-only setups had nothing to work with. The IREN plan was armed at 10:10 with price sitting right at its opening-range low (35.76), which echoes Friday's SAIQ plan that was armed after price had already fallen through the range.

**Constructive critique:** Two flat sessions say nothing yet about edge, but they do say something about selection: gap-ups that fade early dominate the list, and long-only ORB/VWAP setups sit idle on those days. The monitor also keeps arming breakouts when price is at the bottom of the range instead of pressing toward the top.

**Proposed change (not adopted yet):** Same as Friday's proposal, slightly sharpened. Only arm an ORB long while the last price is in the upper half of the opening range; drop the candidate if it trades at or below the range low. Two sessions show the pattern but there are no fills to measure it against, so it stays a proposal. Risk rules and playbook v1.0 unchanged.

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
| v1.0 | 2026-10-12 | No change after session 2. Proposal pending: arm ORB longs only when price is in the upper half of the opening range. | 2 sessions, 0 fills; SAIQ (10/9) and IREN (10/12) armed at or below the range low | Proposed |
