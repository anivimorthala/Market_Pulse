# 🛡️ Privacy Policy, Terms & Risk Disclaimer

---

## 1. Privacy Policy

Market Pulse is designed with a **local-first, privacy-first architecture**:

- **Local Hardware Encryption:** Your broker credentials (**Client Code / UCC**, **MPIN**, **Access Token**, and daily **Kotak Neo Session Tokens**) are stored exclusively on your device using **Android Hardware Keystore (AES-GCM encryption)**.
- **Direct Broker Communication:** All market data requests, order placements, modifications, and cancellations are transmitted directly from your phone to **Kotak Neo official servers** (or through your own user-configured **AWS Static IP Proxy**). Market Pulse **never routes your broker credentials or trading orders through any third-party trade server**.
- **Minimal License Verification Data:** License and 7-Day Free Trial verification transmits **only**:
  1. Your License Key
  2. Your Client Code (UCC)
  3. A one-way hashed Device ID
- **Zero Personal Contact Harvesting:** Market Pulse **does not collect** your personal email address, phone number, contacts, SMS messages, or location data.
- **Full Data Control:** You can wipe all stored broker tokens, Static IP bindings, and local license cache at any time via **Profile → App Updates & About → Delete Account & Clear License**.

---

## 2. Independence & Non-Affiliation Notice

- **Market Pulse** is an independent software utility built for users of the **Kotak Neo Trade API**.
- Market Pulse is **not affiliated with, endorsed by, sponsored by, or officially connected to Kotak Securities Limited** or any of its subsidiaries.
- All trademarks, product names, and broker names belong to their respective owners.

---

## 3. Non-SEBI Advisor & Educational Notice

- Market Pulse and its creator(s) are **not SEBI-registered investment advisors or research analysts**.
- Any indicator outputs or order-book metrics displayed inside optional plugins are strictly for **informational and analytical purposes only** and do not constitute investment advice or solicitation to buy or sell any security.

---

## 4. Derivatives (F&O) Trading Risk Warning

- Trading in Equity Derivatives (**Futures & Options**) involves substantial risk of financial loss and is not suitable for every investor.
- Automated on-device tools (such as Target, Stoploss, and Trailing Stoploss execution) depend on active device internet connectivity, Android OS background execution policies, and broker API availability.
- By using manual order entry or on-device Algo/Indicator tools in Market Pulse, you acknowledge and accept **sole responsibility** for your strategy configuration, order sizing, risk management, and trading outcomes.
