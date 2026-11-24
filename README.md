# Zico

Live broadcast-style global markets, Macau Pataca (MOP) exchange rate, and multi-city weather TV dashboard. Built as a single-file, zero-build static web app compatible with GitHub Pages and local HTTP serving.

## Features

- **Enlarged Two-Deck Markets Ticker**: Live TradingView ticker tapes replacing the previous 3×2 chart grid:
  - **Indices and equities** — S&P 500 (`OANDA:SPX500USD`), Nasdaq 100 (`FOREXCOM:NSXUSD`), Dow Jones / US30 (`OANDA:US30USD`), Euro Stoxx 50, FTSE 100, DAX 40, Swiss SMI 20, Hang Seng, Nikkei 225, plus US mega-caps (Apple, Microsoft, Nvidia, Amazon, Alphabet, Meta, Tesla, JPMorgan) and Macau gaming operators (Las Vegas Sands, Wynn, MGM).
  - **FX majors and macro** — EUR/USD, USD/JPY, GBP/USD, USD/CHF, AUD/USD, USD/CAD, NZD/USD, EUR/GBP, EUR/JPY, USD/HKD, USD/CNH, gold, silver, WTI, Brent, Bitcoin and Ethereum.
  - With `prefers-reduced-motion`, each deck switches to a static quote strip.
- **Cash Market Session Board**: Open / Break / Closed status for New York, Frankfurt, London, Zurich, Hong Kong and Tokyo in the desk bar.
- **Open Centre Stage**: The middle area is intentionally left as clean negative space.
- **Real-Time MOP Exchange Rates**: Keyless 60-second polling using live HKD cross-rates paired with the official `1 HKD = 1.0300 MOP` parity (automatic failover across Coinbase, Open ER-API, jsDelivr `@fawazahmed0/currency-api`, and `localStorage`), displaying real 24-hour daily changes and percentages against the previous close.
- **Real-Time Multi-City Weather & Aligned World Clocks**: Batched live Open-Meteo conditions (temperature, feels-like, WMO day/night weather icons, humidity, and wind speed) paired with live `Intl.DateTimeFormat` clocks across 8 aligned financial hubs: New York, Frankfurt, London, Zurich, Hong Kong, Macau, Tokyo, and Sydney.
- **Top Stories Wire**: Vertically auto-scrolling headlines from CNBC and BBC Business RSS feeds (keyless via rss2json, deduplicated, newest first, cached in `localStorage`, refreshed every 10 minutes). Pauses on hover/focus and has a Pause/Play button; with `prefers-reduced-motion` it becomes a static scrollable list. Falls back to an auto-scrolled TradingView stories widget if no feed or cache is available.

## Usage

Open via any static web server (recommended so browser storage and CORS requests run cleanly under an HTTP origin):

```bash
python3 -m http.server 8765
```

Then visit `http://localhost:8765/`.
