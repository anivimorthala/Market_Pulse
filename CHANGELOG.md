# 🆕 Market Pulse — Release Notes

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
