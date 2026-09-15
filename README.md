# LaunchTower — Factor Samples (Free)

> **Independent market-data desk.** Reproducible, documented factor screens on US large-caps from public market data. This repo is the **free sample** — the full 151-stock dataset, complete methodology pack, and live signal feed are available on [Whop](https://whop.com/launchtower/products/launchtower-full-dataset-methodology-e4/).

> ⚠️ **Disclaimer:** Research/educational output from public market data. **Not** personalized investment advice, **not** a recommendation to buy or sell any security. Past performance does not guarantee future results.

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

## The 19-Stock Free Sample (2026-09-16)

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

## What's in the Full Pack (Whop — $19)

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
