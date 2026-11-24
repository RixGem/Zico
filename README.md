# Zico

Live broadcast-style global markets, Macau Pataca (MOP) exchange rate, and multi-city weather TV dashboard. Built as a single-file, zero-build static web app compatible with GitHub Pages and local HTTP serving.

## Features

- **Currency-Matched Real-Time Index Charts (3×2 Stage)**: Pairs each MOP-quoted currency with its primary stock market index via live TradingView Mini Symbol Overview widgets, complete with `1D` / `1M` / `1Y` timeframe switching, live cash-market session status (`Open` / `Break` / `Closed`), and synced MOP spot headers:
  - **USD** — S&P 500 (`OANDA:SPX500USD`)
  - **EUR** — Euro Stoxx 50 (`OANDA:EU50EUR`)
  - **GBP** — FTSE 100 (`OANDA:UK100GBP`)
  - **CHF** — Swiss SMI 20 (`OANDA:CH20CHF`)
  - **HKD** — Hang Seng (`OANDA:HK33HKD`)
  - **JPY** — Nikkei 225 (`OANDA:JP225YJPY`)
- **Real-Time MOP Exchange Rates**: Keyless 60-second polling using live HKD cross-rates paired with the official `1 HKD = 1.0300 MOP` parity (automatic failover across Coinbase, Open ER-API, jsDelivr `@fawazahmed0/currency-api`, and `localStorage`), displaying real 24-hour daily changes and percentages against the previous close.
- **Real-Time Multi-City Weather & Aligned World Clocks**: Batched live Open-Meteo conditions (temperature, feels-like, WMO day/night weather icons, humidity, and wind speed) paired with live `Intl.DateTimeFormat` clocks across 8 aligned financial hubs: New York, Frankfurt, London, Zurich, Hong Kong, Macau, Tokyo, and Sydney.
- **Market Wire & Global Ticker Tape**: Continuous TradingView market stories sidebar alongside a top global indices, crypto, commodities, and FX ticker tape.

## Usage

Open via any static web server (recommended so browser storage and CORS requests run cleanly under an HTTP origin):

```bash
python3 -m http.server 8765
```

Then visit `http://localhost:8765/`.
