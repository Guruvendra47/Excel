# 📊 Stock Watchlist & Portfolio Strategy Tracker

An all-in-one **Excel/Google Sheets stock market dashboard** for tracking Indian equities (NSE/BSE) — built for watchlisting, buy/hold signal generation, dip-buying (pyramid) strategy, portfolio allocation, installment planning, and email alerts.

---

## 🎯 The Business Problem

Retail investors tracking a large watchlist (80+ stocks in this case) run into the same recurring problems:

- **No single view of the market** — global indices, ADRs, and individual stock signals are scattered across apps, tabs, and broker platforms.
- **Emotional buying/selling** — without a pre-defined rule (e.g. "buy at -30% from 52-week high"), decisions get made on impulse instead of a plan.
- **No structured entry strategy** — buying a full position at once is risky; averaging in as price drops (pyramid buying) needs quantity/price math done *every time*, for *every stock*.
- **Capital gets over- or under-allocated** — without tracking amount allotted vs. used, it's easy to over-invest in one stock and starve another.
- **Missed entry/exit points** — target buy/sell levels are only useful if you're notified when price crosses them; manually checking 80+ stocks daily doesn't scale.
- **No fundamentals/valuation lens** — price-only signals ignore whether a company's operating margins and profitability are actually improving.

**This workbook solves that** by turning a plain watchlist into a rules-based decision system: it pulls live prices, classifies stocks by market cap, calculates dip-based entry points automatically, tracks capital deployed, flags fundamentally strong picks, and drafts alert emails — all inside a spreadsheet, with zero external tools or subscriptions.

**Who it's for:** individual/retail investors in Indian equities who want a disciplined, rules-based system for watchlisting and phased (SIP-style) stock accumulation, without paying for a portfolio-management SaaS tool.

---

## 🖼️ Preview

### Dashboard — Global Markets + Single Stock Overview
Live snapshot of major global indices (Dow, S&P 500, Nasdaq, Nifty, Sensex, Nikkei, FTSE, DAX, etc.), a single-stock deep dive panel with 12-month trend, and ADR prices for Indian companies listed in the US.

![Dashboard overview](images/dashboard-overview.png)

### CHECK — Before/During/After Market Summary
A condensed before-market, during-market, and after-market view of key indices and major stock movers (HDFC, ICICI, TCS, Infosys, Reliance).

![Before/during/after market summary](images/check-market-summary.png)

### BOD Strategy — Buy-on-Dip Entry Calculator
Automatically calculates the target buy **price** and **quantity** at every dip level from 20% to 80% below the 52-week high, for every stock in the watchlist — with a live Buy/Hold/Next signal per level.

![Buy-on-dip strategy sheet](images/bod-strategy.png)

### OPM % Strategy — Fundamentals Overlay
Tracks Operating Profit Margin %, Net Profit, and Borrowings across multiple years, charted against a trendline — used to confirm a stock is fundamentally sound before averaging in further.

![OPM % strategy charts](images/opm-strategy-charts.png)

### Installment — Rule-Based Position Building
Tracks target quantity vs. deficit quantity, and whether the "Met/Not Met" rule has triggered at 15%/30%/50%/70% price drops — so you know exactly when to add to a position.

![Installment tracker](images/installment-tracker.png)

### History — Transaction Log
A running ledger of every buy/sell transaction — date, security, action, quantity, price, and total — feeding into the portfolio's real cost basis.

![Transaction history](images/transaction-history.png)

### Email — Auto-Drafted Buy/Sell Alerts
Compares current price against target buy/sell levels per stock and prepares an alert message (e.g. "27% Down") so you know which stocks just hit your entry rule.

![Email alert sheet](images/email-alerts.png)

### Conversion — Cost, Value & Gain Tracker
Currency-aware (INR) cost, current value, and unrealized gain/loss per holding, computed straight from the Installment and transaction data.

![Currency conversion and gain tracker](images/currency-conversion.png)

---

## 📁 What's Inside (`Watchlist.xlsx`)

| Sheet | Purpose |
|---|---|
| **Dashboard** | Live global index snapshot plus a single-stock overview panel and the master watchlist (Buy/Hold/Sell signal, 52-week high/low, market cap, target-buy %). |
| **CHECK** | Before/during/after-market summary — key indices, ADRs, and major stock movers at a glance. |
| **Fresh Shares List** | A shortlist of newly tracked stocks with buy/hold signals and cap classification, separate from the main watchlist. |
| **BOD Stgy** *(Buy-on-Dip Strategy)* | Calculates target buy prices and quantities at 20%–80% dip levels from 52-week high, per stock. |
| **Pyramid Stgy** | Pyramid/averaging-down position sizing — Low → Medium → High → High-High quantity tiers as price drops. |
| **OPM % Stgy** | Tracks Operating Profit Margin (OPM %), net profit, and borrowings over multiple years per company — used for fundamental screening. |
| **Amount Allocation** | Tracks capital allotted vs. used vs. remaining per stock. |
| **Installment** | Rule-based installment buying — target quantity, deficit, and buy/hold rule at multiple dip thresholds (15%/30%/50%/70%). |
| **History** | Historical transaction/portfolio log. |
| **Email** | Auto-drafted buy/sell alert emails per stock, comparing current price against target buy/sell levels. |
| **Conversion** | Currency-aware cost, value, and gain/loss tracker per holding. |
| **Backend Data** | Reference data — company codes, bank/exchange codes, and annual dividend history. |
| **Links** | Reference/browser-console snippets used for data scraping helpers. |
| **Rules** | The strategy rulebook — installment percentages by market-cap category (Small/Mid/Large/Mega), pyramid-buying quantity logic, and share recovery-percentage calculator. |

---

## 🧠 Strategy Logic (Rules Sheet Summary)

**Installment Buying (by market cap):**

| Cap Size | 1st Installment | 2nd Installment |
|---|---|---|
| Small Cap | 30% | 35% |
| Mid Cap | 20% | 25% |
| Large Cap | 15% | 20% |
| Mega Cap | 10–15% | 20% |

**Pyramid Averaging Rule:** Each subsequent buy = `2 × current total shares held` (e.g. 1 → 2 → 6 → 18 → 54 shares).

**Golden Rule:** *Always buy on red. Check market conditions before every entry.*

---

## ✅ Features

- 🌍 Live global market indices (US, Europe, Asia)
- 📈 Buy/Hold/Sell signal generation per stock
- 🎯 Automatic target-buy price calculation at multiple dip %
- 🧱 Pyramid (averaging-down) position sizing
- 💰 Capital allocation & installment tracking
- 📬 Auto-generated buy/sell alert email drafts
- 📊 Market-cap based bar visualization (Small/Mid/Large/Mega)
- 🗂️ Dividend & fundamentals history log

---

## 🚀 How to Use

1. Download `Watchlist.xlsx` and open it in Excel, Google Sheets, or LibreOffice Calc.
2. Update the **Watchlists** table in the `Dashboard` sheet with your tracked tickers (NSE/BSE format, e.g. `NSE:TCS`, `BOM:514183`).
3. Refresh stock price data via your preferred live-data source (e.g. Google Finance formulas or a market-data plugin).
4. Check the `BOD Stgy` and `Pyramid Stgy` sheets for computed entry points as price drops from 52-week high.
5. Log allocated capital in `Amount Allocation` and track buy tranches in `Installment`.
6. Review `Email` for auto-generated alert drafts when price crosses your target buy/sell levels.

> ⚠️ **Note:** This tool is for personal portfolio tracking and educational purposes. It is **not financial advice**. Always do your own research (DYOR) before investing.

---

## 🛠️ Tech Used

- Google Sheets / Microsoft Excel (formulas, conditional formatting, data tables, charts)
- No macros/VBA — pure formula-driven logic
- Live price feeds via spreadsheet-native stock functions

---

## 📂 Repository Structure

```
Stock-Watchlist-Tracker/
├── Watchlist.xlsx              # Main workbook
├── images/                     # README screenshots
│   ├── dashboard-overview.png
│   ├── check-market-summary.png
│   ├── bod-strategy.png
│   ├── opm-strategy-charts.png
│   ├── installment-tracker.png
│   ├── transaction-history.png
│   ├── email-alerts.png
│   └── currency-conversion.png
├── .gitignore
└── README.md
```

---

## 📄 License

Feel free to use, modify, and adapt this tracker for your own personal investing workflow. If you build on it publicly, a credit/link back is appreciated 🙏

---

## 🙋 Contributing / Feedback

Found a formula improvement or want to suggest a new strategy sheet? Open an issue or a pull request!
