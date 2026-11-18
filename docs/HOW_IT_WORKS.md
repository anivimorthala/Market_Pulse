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

Market Pulse runs an **on-device automation engine** right on your Android phone — your strategy rules and stops stay private on your device.

### Supported Automation Controls
- **Entry Trigger:** Market (`CMP`) or Trigger/Limit entry price.
- **Target & Initial Stoploss:** Automatic broker square-off the instant live LTP hits your Target or SL.
- **Trailing Stoploss (TSL):** Configure **TSL Jump** and **Trail Step** so your SL ratchets upward automatically as price moves in your favor.
- **Live Edit Mid-Trade:** Tap **`Edit Levels`** on any active or pending Algo card to adjust Target, SL, or TSL on the fly:
  - **1-Tap `SL → Cost`:** Instantly moves your Stoploss to breakeven when in profit.
  - **1-Tap `Lock 50%`:** Locks half of your current unrealized gain immediately.
  - Built-in price guardrails prevent accidental instant triggers on BUY/SELL positions.
- **Instant Manual Exit & Real Fill Sync:** Tap **`Instant Exit`** to square off immediately via Kotak API; Market Pulse verifies broker confirmation and syncs the exact executed fill price from your order book.
- **Clean Day Summary:** Filter by **`All | Live | Closed`**, view Today's Algo Net P&L bar, and auto-clear prior-day closed logs at midnight IST.

### 🛡️ Active Algo Background Guard
- Enabled by default under **Profile → Notifications → Active Algo Background Guard**.
- Whenever an Algo is actively running, Market Pulse holds an Android Foreground Service (`⚡ Active Algo · Monitoring Live`) so Android **never freezes your live quotes or Target/SL checks** while you switch apps or lock your screen.
- The moment your last active Algo finishes, the persistent bar **disappears automatically**.

---

## 4. Modular Indicators (`INDICATORS`)

Enable the **Indicators** slot in **Profile → Plugins & Modules** to access lightweight, on-device analytical tools:

- **Order Book Imbalance (OBI):** Live Buy vs. Sell depth pressure ratio and quantity bar across your watchlisted instruments — helping you gauge immediate order-flow bias without leaving the terminal.
- **Modular Plugin Architecture:** Toggle features on or off anytime so your bottom navigation bar stays clean and tailored to your trading style.

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
