# Cash-Carry Trade Scanner

A single-file, browser-based scanner for **cash-and-carry arbitrage** opportunities across Binance, OKX, and Bybit — no backend, no dependencies, open `cash-carry-scanner.html` directly in any modern browser.

## What is Cash-Carry Arbitrage?

Buy spot + short a quarterly futures contract on the same asset. At expiry, the futures price converges to spot, locking in the basis spread as risk-free profit. The strategy is market-neutral (delta-hedged) with low directional risk.

**APY formula:**

```
APY = (Futures − Spot) / Spot × (365 / Days to Expiry) × 100
```

## Features

- **Live data** from three exchanges simultaneously — Binance, OKX, Bybit
- **Auto-refresh** every 10 seconds with a circular countdown timer
- **Stats bar** — best APY, average APY, pair counts per exchange
- **Filters** — filter by exchange or APY threshold (All / Positive / >5% / >10%)
- **Sortable columns** — click any column header to sort ascending/descending
- **Clickable contracts** — direct links to spot and futures trading pages
- **APY colour gradient** — red (negative) → yellow (near zero) → green (positive)
- **Expiry urgency badges** — red (<7d), yellow (<30d), neutral (>30d)

## Exchanges & APIs

| Exchange | Futures Type | API Used |
|----------|-------------|---------|
| Binance  | CURRENT_QUARTER, NEXT_QUARTER | `fapi.binance.com` |
| OKX      | USDT-settled Futures | `okx.com/api/v5` |
| Bybit    | Linear Futures (USDT) | `api.bybit.com/v5` |

All APIs are public and require no authentication or API key.

## Usage

1. Clone or download the repo
2. Open `cash-carry-scanner.html` in your browser
3. Data loads automatically — no server required

```bash
git clone git@github.com:Zaranity/cash-carry-trade-scanner.git
cd cash-carry-trade-scanner
open cash-carry-scanner.html   # macOS
# or double-click the file in your file manager
```

## Screenshot

The dark-themed UI shows a live-updating table ranked by annualised yield, with exchange badges, expiry dates, basis %, and a visual APY bar per row.

## Disclaimer

This tool is for informational purposes only. Cash-carry arbitrage involves real financial risk including exchange risk, liquidation risk, and execution slippage. Always do your own research before trading.
