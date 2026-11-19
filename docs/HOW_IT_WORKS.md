# 🧠 How Market Pulse Works

A complete tour of Market Pulse's core modules and on-device execution engine.

---

## 1. Live Index Header & Navigation

- **Customizable Dual Index Header:** Tap either index slot at the top of the screen to pin any 2 of **NIFTY, BANKNIFTY, FINNIFTY, MIDCPNIFTY, SENSEX, or BANKEX** with live LTP and percentage change.
- **Modular Bottom Navigation:** Core tabs (**Watchlist**, **Orders**, **Positions**, **Profile**) plus up to **2 plug-and-play feature slots** (**Algo** and **Indicators**) that you can enable or disable anytime in **Profile → Plugins & Modules**.
- **Live Status Badges:** **`PROFILE`** displays an amber badge whenever an App Update or Plugin Update is available, so you always stay up to date with 1 tap.

---

## 2. Watchlists & 1-Tap Order Execution

- **Instant Strike Search:** Search any NSE F&O, BSE F&O (Sensex/Bankex), or NSE/BSE Cash scrip directly from Kotak's live master scrip list.
- **Multi-Watchlist Organization:** Maintain clean watchlists for indices, weekly expiries, and swing stocks.
- **Fast Order Sheet:** Tap any instrument for instant **BUY / SELL** sheets supporting **NRML / MIS / CNC**, **MKT / LIMIT / SL**, lot-size multipliers, and instant order confirmation alerts.
- **Orders & Positions Sync:** Live WebSocket order feed + auto-refreshing net Positions, MTM P&L, Holdings, and Available Margin.

---

## 3. On-Device Algo Terminal (`ALGO`)

Market Pulse runs an **on-device execution engine** right on your Android phone — your strategy rules and stops stay private on your device.

### Supported Automation Controls
- **Flexible Entry Modes:** Support for Market (CMP) and Limit/Trigger entries.
- **Automated Target & Stoploss:** Automatic broker square-off when your target or stoploss conditions are met.
- **Dynamic Trailing Stoploss (TSL):** Protect profits by dynamically trailing your stoploss as market price moves favorably.
- **Mid-Trade Level Adjustments:** Modify your Target, Stoploss, or Trailing settings on any active trade without canceling the trade.
- **Quick Profit Protection:** 1-tap chips to lock in gains or move stoploss to breakeven during active trades.
- **1-Tap Manual Exit:** Instantly square off open positions at market CMP with verified broker fill sync.
- **Trade History & Filtering:** View and filter trades by active, pending, or closed status with daily P&L tracking.

### 🛡️ Active Algo Background Guard
- Enabled under **Profile → Notifications → Active Algo Background Guard**.
- Protects active trade execution in the background so trade management continues uninterrupted when switching apps or locking your phone.
- Automatically dismisses when all active trades are closed.

---

## 4. Modular Indicators (`INDICATORS`)

Enable the **Indicators** slot in **Profile → Plugins & Modules** to access on-device analytical tools:

- **Order Book Imbalance (OBI):** Visual market depth indicator showing real-time buy and sell pressure across watchlisted contracts.
- **Modular Plugin Architecture:** Toggle analytical modules on or off anytime to keep your interface clean and customized to your workflow.

---

## 5. Independent Notification Controls

Customize alerts cleanly in **Profile → Notifications**:

| Toggle | Default | Behavior |
| :--- | :---: | :--- |
| **Order Buy & Sell Alerts** | **ON** | Instant heads-up notification & sound when Kotak fills a buy/sell order. |
| **Active Algo Background Guard** | **ON** | Keeps Target/SL/TSL monitoring alive in background while an Algo is active. |
| **Live P&L Tracker (till 4 PM)** | **OFF** | Optional persistent notification showing live intraday F&O / MIS P&L. |
| **Track Long-Term Equity (CNC/MTF)** | **OFF** | Include or exclude delivery holdings from the live P&L tracker. |

---

## 6. Themes & In-App OTA Updates

- **Themes & Fonts (`Profile → Appearance`):** Choose from 6 curated dark/glass/light themes and customize numeric font style.
- **Seamless OTA Updates (`Profile → App Updates`):** When a new version is released, Market Pulse alerts you silently after login and lets you download & install the update directly from inside the app.
