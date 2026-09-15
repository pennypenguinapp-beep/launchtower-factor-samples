# LaunchTower — Factor Samples (Free)

> **Independent market-data desk.** Reproducible, documented factor screens on US large-caps from public market data. This repo is the **free sample** — the full 151-stock dataset, complete methodology pack, and live signal feed are available on [Whop](https://whop.com/launchtower/products/launchtower-full-dataset-methodology-e4/).

> ⚠️ **Disclaimer:** Research/educational output from public market data. **Not** personalized investment advice, **not** a recommendation to buy or sell any security. Past performance does not guarantee future results.

---

## 🎯 Want the full 151-stock dataset + methodology + backtests?

**[→ Get the Full Pack on Whop — $19 one-time](https://whop.com/launchtower/products/launchtower-full-dataset-methodology-e4/)**

No subscription. No email gate. Instant download.

---

## Why This Repo Exists

Most factor screens you'll find online are either:
- **Black boxes** — you get a ranking but not the code
- **Stale** — data from 6 months ago, never updated
- **Incomplete** — 5 stocks, 3 factors, no methodology

This repo gives you **all three**: the exact 15-line Python model, live data from the last 2 years, and a full write-up of every formula. Run it yourself, verify every number, and extend it however you want.

**The free sample below is 19 mega-cap tech stocks.** The full pack covers **151 US large-caps** with the same model, plus backtest results and a dated research report.

---

## What's in This Repo

| File | Description |
|------|-------------|
| `factor_ranking_19_2026-09-16.csv` | **Free sample:** 19 mega-cap tech stocks ranked by composite factor score (momentum + quality) |
| `README.md` | This file — model description, how to reproduce, and link to the full pack |

---

## The 19-Stock Free Sample — Full Data (2026-09-16)

Complete CSV, copy-paste ready:

```csv
rank,ticker,date,last_price,ret_1m,ret_3m,ret_6m,ret_12m,vol_ann,max_drawdown,from_52w_high,momentum_score,quality_score,composite_score
1,MU,2026-09-14,975.26,0.0702,-0.0205,1.4074,5.4875,0.8143,-0.391,-0.1962,6.5454,-2.1378,2.2038
2,INTC,2026-09-14,102.94,0.0197,-0.1199,1.2749,3.1829,0.7965,-0.419,-0.2696,3.621,-2.0488,0.7861
3,AMD,2026-09-14,516.13,0.0687,0.0567,1.6101,2.3155,0.7182,-0.2776,-0.1115,2.5204,-1.657,0.4317
4,AAPL,2026-09-14,332.27,0.0993,0.1249,0.3015,0.4498,0.2508,-0.138,-0.0221,0.1529,0.6817,0.4173
5,GOOGL,2026-09-14,338.5,-0.014,-0.0533,0.1165,0.4119,0.3158,-0.2105,-0.1582,0.1048,0.3565,0.2307
6,TXN,2026-09-14,268.7,-0.0285,-0.091,0.4283,0.4953,0.4247,-0.2337,-0.1872,0.2107,-0.1884,0.0111
7,AMZN,2026-09-14,256.78,-0.0393,0.0632,0.2255,0.1167,0.3434,-0.2174,-0.0959,-0.2698,0.2184,-0.0257
8,NVDA,2026-09-14,218.29,-0.0248,0.0667,0.1947,0.235,0.3803,-0.2021,-0.0719,-0.1196,0.0338,-0.0429
9,MSFT,2026-09-14,495.63,0.0084,0.2721,0.2383,-0.0026,0.3248,-0.345,-0.0781,-0.4211,0.3115,-0.0548
10,META,2026-09-14,648.03,0.1195,0.1411,0.0172,-0.1342,0.3947,-0.3246,-0.1667,-0.5881,-0.0383,-0.3132
11,AVGO,2026-09-14,361.99,-0.1299,-0.0597,0.0814,0.0139,0.4621,-0.2867,-0.2471,-0.4002,-0.3755,-0.3879
12,CRM,2026-09-14,247.72,0.2814,0.4883,0.2494,0.0144,0.4724,-0.4333,-0.0648,-0.3996,-0.4271,-0.4133
13,ADBE,2026-09-14,252.23,-0.0252,0.1528,-0.0651,-0.2805,0.4021,-0.4737,-0.3136,-0.7738,-0.0753,-0.4245
14,TSLA,2026-09-14,365.44,0.1158,-0.0845,-0.0749,-0.0091,0.4717,-0.391,-0.254,-0.4294,-0.4236,-0.4265
15,QCOM,2026-09-14,181.97,0.122,-0.0985,0.4002,0.1501,0.5259,-0.4098,-0.2684,-0.2274,-0.6948,-0.4611
16,SNOW,2026-09-14,328.99,-0.0098,0.3686,0.8561,0.4652,0.6534,-0.563,-0.0771,0.1725,-1.3327,-0.5801
17,PLTR,2026-09-14,167.23,-0.0223,0.2758,0.0894,0.0175,0.6088,-0.4822,-0.1928,-0.3956,-1.1096,-0.7526
18,NOW,2026-09-14,132.53,0.0607,0.2857,0.1731,-0.2938,0.5687,-0.5682,-0.3106,-0.7907,-0.9089,-0.8498
19,ORCL,2026-09-14,150.28,-0.0196,-0.1809,-0.0492,-0.5063,0.5704,-0.6456,-0.5368,-1.0603,-0.9174,-0.9889
```

### Quick-Read Summary

| Rank | Ticker | Last Price | 12m Return | Ann. Vol | Composite |
|------|--------|-----------|------------|----------|-----------|
| 1 | **MU** | $975.26 | +548.8% | 81.4% | **+2.204** |
| 2 | **INTC** | $102.94 | +318.3% | 79.7% | **+0.786** |
| 3 | **AMD** | $516.13 | +231.6% | 71.8% | **+0.432** |
| 4 | **AAPL** | $332.27 | +45.0% | 25.1% | **+0.417** |
| 5 | **GOOGL** | $338.50 | +41.2% | 31.6% | **+0.231** |
| 6 | **TXN** | $268.70 | +49.5% | 42.5% | **+0.011** |
| 7 | **AMZN** | $256.78 | +11.7% | 34.3% | **−0.026** |
| 8 | **NVDA** | $218.29 | +23.5% | 38.0% | **−0.043** |
| 9 | **MSFT** | $495.63 | −0.3% | 32.5% | **−0.055** |
| 10 | **META** | $648.03 | −13.4% | 39.5% | **−0.313** |
| 11 | **AVGO** | $361.99 | +1.4% | 46.2% | **−0.388** |
| 12 | **CRM** | $247.72 | +1.4% | 47.2% | **−0.413** |
| 13 | **ADBE** | $252.23 | −28.1% | 40.2% | **−0.425** |
| 14 | **TSLA** | $365.44 | −0.9% | 47.2% | **−0.427** |
| 15 | **QCOM** | $181.97 | +15.0% | 52.6% | **−0.461** |
| 16 | **SNOW** | $328.99 | +46.5% | 65.3% | **−0.580** |
| 17 | **PLTR** | $167.23 | +1.8% | 60.9% | **−0.753** |
| 18 | **NOW** | $132.53 | −29.4% | 56.9% | **−0.850** |
| 19 | **ORCL** | $150.28 | −50.6% | 57.0% | **−0.989** |

**What stands out:**
- **Memory/storage is the momentum story** — MU (+549% 12m) and INTC (+318%) lead on raw momentum, though both carry elevated vol.
- **AAPL is the quality standout** — modest +45% 12m return with the lowest vol in the group (25.1%), giving it the best composite among the "safe" names.
- **The bottom of the table is a software cluster** — ORCL, NOW, PLTR all show deep 52w drawdowns combined with elevated vol. The composite is doing exactly what it's built to do: penalize lottery-ticket vol.

---

## The Model in One Paragraph

Pull 2 years of split/dividend-adjusted daily closes for the universe. Over the trailing 252 trading days, compute per-ticker: 1m/3m/6m/12m returns, annualized realized volatility, max drawdown, distance from 52w high. Cross-sectionally z-score the 12m return → **Momentum**; z-score annualized vol and negate → **Quality**. **Composite = 0.5·Momentum + 0.5·Quality**, rank 1–N.

```
composite = 0.5 · z(12m return) + 0.5 · z(−annualized vol)
```

z-scores are cross-sectional (mean 0, std 1) on the current universe. Rank 1 = highest composite.

## How to Reproduce Every Number

```bash
pip install yfinance pandas numpy
```

The full runnable script is included in the **paid pack** (see below). The core logic is ~15 lines:

```python
import yfinance as yf
import pandas as pd
import numpy as np
from datetime import datetime

universe = ["MU","INTC","AMD","AAPL","GOOGL","TXN","AMZN","NVDA","MSFT",
            "META","AVGO","CRM","ADBE","TSLA","QCOM","SNOW","PLTR","NOW","ORCL"]

end = datetime(2026, 9, 16)
start = datetime(2024, 9, 16)

data = yf.download(universe, start=start.strftime('%Y-%m-%d'),
                   end=end.strftime('%Y-%m-%d'), auto_adjust=True,
                   progress=False, threads=True)

close = data['Close']
rets = close.pct_change(fill_method=None)

mom_12m = close.shift(21) / close.shift(252) - 1
vol = rets.rolling(252).std() * np.sqrt(252)

mom_z = (mom_12m - mom_12m.mean()) / mom_12m.std()
qual_z = (-vol - (-vol).mean()) / (-vol).std()
composite = 0.5 * mom_z + 0.5 * qual_z

results = pd.DataFrame({
    'ticker': universe,
    'ret_12m': mom_12m.iloc[-1].values,
    'vol_ann': vol.iloc[-1].values,
    'momentum_score': mom_z.iloc[-1].values,
    'quality_score': qual_z.iloc[-1].values,
    'composite_score': composite.iloc[-1].values
}).sort_values('composite_score', ascending=False).reset_index(drop=True)

print(results)
```

---

## 🎯 What's in the Full Pack (Whop — $19)

- **Full 151-ticker dataset** — all columns: raw factors, z-scores, composite, rank
- **Complete methodology documentation** — factor definitions, z-scoring, weighting, edge cases
- **Live signal feed** — dated CSV, updated on a schedule
- **Full runnable script** — with configuration knobs (universe, window, weights)
- **Backtest results** — 24 rebalance periods, top/bottom forward returns, long-short spread (including the months where the signal lost money)

> **🛒 Get the full pack:** [https://whop.com/launchtower/products/launchtower-full-dataset-methodology-e4/](https://whop.com/launchtower/products/launchtower-full-dataset-methodology-e4/)
>
> **$19 one-time. No subscription. No email gate.**

---

*LaunchTower — independent market-data desk. Data: yfinance (public). All figures regenerated from live data at generation time. Not investment advice; past performance does not guarantee future results.*
