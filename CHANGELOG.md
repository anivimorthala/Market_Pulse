# 🆕 Market Pulse — Release Notes

## `v2.4.5` — Public Release

### ✨ New Features & Portfolio Upgrades
- **Direct Holdings 1-Tap Exit & Order Pad:**
  - Demat Holdings are now fully interactive: tap to open the order pad pre-filled with `CNC`, `SELL`, and current available quantity, or tap `[EXIT]` for instant market order execution.
  - Partial exits supported: choose any quantity up to your available holdings.
- **Cross-Tab Portfolio Reconciliation (Holdings ↔ Positions):**
  - Real-time intra-day synchronization between Demat holdings and trade positions before 4:30 PM depository settlement.
  - Demat equity sold today in `CNC` is identified as a delivery sale, tagged `CNC · DELIVERY SOLD`, dimmed to `0.45` opacity, and given a disabled `[DELIVERY SOLD]` status.
  - **Shielded Square Off All:** Demat delivery sales are strictly excluded from `SQUARE OFF ALL` to prevent accidental buybacks of exited holdings.
  - **Accurate Holdings Availability:** Holdings cards dynamically show remaining available shares (`Qty: 90 (10 sold)`) and switch to `[SOLD OUT]` with disabled tap when 100% sold out today.
  - **Uncovered & Active Shorts Untouched:** Naked CNC shorts, Intraday `MIS` shorts, and F&O shorts remain active open trades with 1-tap `[EXIT (BUY)]` cover buttons.
- **Profile P&L Segregation:**
  - Dedicated separation of **`DAY P&L (TRADING)`** (today's active trading) and **`HOLDINGS P&L`** (all-time Demat equity valuation) under the Profile Portfolio summary.

### 🛠️ Reliability & API Fixes
- **Kotak Neo API Symbol Auto-Normalization:**
  - Automatically appends `-EQ` on `nse_cm` (e.g. `YESBANK` → `YESBANK-EQ`) for orders placed from Holdings, permanently eliminating the Kotak Neo API `"please provide valid symbol"` rejection.
- **Closed Positions Display Fix:**
  - Closed F&O positions cleanly display `0 lots` (resolving the `-0 lots` minus sign display bug).

## `v2.4.0` — Public Release

### ✨ New Features
- **7-Day Free Trial:** Extended the instant onboarding free trial from 3 days to **7 full days** for all new users.
- **Live Update Badge:** **`PROFILE`** now displays an amber counter badge whenever a new App Update or Plugin Update is ready.
- **On-Device Algo Live Edit (`Target / SL / TSL`):**
  - Edit Target, Stoploss, and Trailing SL on any live or pending Algo without cancelling it.
  - Added 1-tap **`SL → Cost`** and **`Lock 50%`** profit-protection chips.
  - Added `All | Live | Closed` filter tabs, Today's Algo Net P&L summary bar, and real broker fill-price sync on manual exits.
- **Active Algo Background Guard:**
  - Automatically keeps live Target/SL/TSL monitoring protected in the background while any Algo is running, and auto-dismisses the notification bar the moment the last Algo closes.
- **Cleaner Notifications:** Independent toggles for Order Execution Alerts, Active Algo Background Guard, Live P&L Tracker, and CNC/MTF Equity tracking — with zero duplicate notifications.

### 🛠️ Reliability & Privacy Fixes
- **Permanent Static IP Persistence:** Upgraded Static IP binding to a dual-storage engine so your bound AWS Static IP never disappears across app restarts or Android Keystore hiccups.
- **Updated Privacy Policy:** Clarified zero collection of personal email or phone numbers.
- **Direct Kotak TOTP Setup Link:** Added 1-tap official Kotak Neo TOTP registration link inside the Login & Setup Guides.
