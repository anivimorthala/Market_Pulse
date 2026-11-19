# 📖 Market Pulse — Setup & Onboarding Guide

Get from download to live trading in under 5 minutes.

---

## Step 1: Download & Install the APK

1. Download **`MarketPulse-v2.4.5-arm64.apk`** from the [main page](../README.md) *(or the `arm32` build if you are on an older 32-bit Android device)*.
2. Tap the downloaded APK file in your browser or **Files** app.
3. If Android prompts **"Install unknown apps"**, tap **Settings → Allow from this source**, then tap **Install**.
4. Open **Market Pulse** and allow **Notifications** when prompted so you receive instant order execution and Target/SL alerts.

> **Tip:** To ensure uninterrupted Algo Target/SL monitoring when your screen is off, set **Battery Usage → Unrestricted** for Market Pulse in Android App Info.

---

## Step 2: Start Your 7-Day Free Trial (or Activate a License Key)

1. Open your official **Kotak Neo** app → tap **Profile** (top-left) → note your **Client Code (UCC)** (e.g., `YX3X1`).
2. In **Market Pulse**, enter your **Client Code (UCC)**.
3. Choose either:
   - Tap **`START 7-DAY FREE TRIAL`** — activates immediately for 7 full days using your Client Code, **or**
   - Enter your `KAT-XXXX-XXXX-XXXX` License Key and tap **`ACTIVATE WITH KEY`**.

> Your trial/license binds securely to your Client Code and device. You can activate or update a license key anytime via **Profile → Subscription & Upgrade Key** without losing your watchlists or settings.

---

## Step 3: Get Your Kotak Neo Trade API Credentials

Market Pulse connects directly to your Kotak Neo account via Kotak's official Trade API:

1. **Trade API Access Token:**
   - Open **Kotak Neo** (App or Web) → **More → Trade API** → create or open your Trade API application → copy your **Access Token**.
2. **Register TOTP (Authenticator App):**
   - If you haven't enabled TOTP for Kotak Neo Trade API yet, register it directly on Kotak's official portal:
     👉 **https://www.kotakneo.com/platform/kotak-neo-trade-api/totp-registration/**
   - Scan the QR code with **Google Authenticator**, **Microsoft Authenticator**, or **Authy** to generate your 6-digit TOTP codes.
3. **Enter Broker Credentials Once:**
   - Inside Market Pulse Step 1, enter your **UCC**, **Registered Mobile (+91XXXXXXXXXX)**, **Access Token**, and **MPIN**.
   - These credentials are encrypted locally using **Android Hardware Keystore (AES-GCM)**.

---

## Step 4: Bind Your AWS Static IP (Required for API Orders)

Per **SEBI & Exchange regulations**, Kotak Neo requires API order requests (place, modify, cancel) to originate from a **whitelisted Static IP**.

1. Follow our 5-minute AWS Free Tier walkthrough:
   - 👉 **[AWS Static IP Setup Guide (Web)](AWS_STATIC_IP_SETUP.md)**
   - 📄 **[Download 2-Page PDF Guide](AWS_Kotak_Static_IP_Setup_Guide.pdf)**
2. Whitelist your AWS Elastic IP inside **Kotak Neo → More → Trade API → Add IP**.
3. In **Market Pulse**, go to **Profile → Static Order IP Binding**, enter `http://YOUR_AWS_ELASTIC_IP`, tap **Test Ping** (confirm *Proxy Online*), and tap **Save & Bind Static IP**.
4. Complete the prompted quick **TOTP Re-login** so Kotak issues your active trading session directly through your Static IP.

---

## Step 5: Daily Login (3 Seconds)

Kotak Neo trading sessions refresh daily after midnight. Every trading morning:
1. Open **Market Pulse**.
2. Enter your **6-digit TOTP** from your authenticator app (your encrypted credentials & MPIN are already remembered).
3. Tap **Verify & Connect** — your live feeds, Watchlists, Positions, and Algo Terminal load immediately!

---

## Need Help?

- **In-App Help:** Every setup screen includes a **`? Guide`** chip with quick visual tips.
- **Need Support?** If any support is needed regarding the app or setup, contact us on Telegram **[@ANIVIREDDY](https://t.me/ANIVIREDDY)** or email **[anivimorthala@gmail.com](mailto:anivimorthala@gmail.com)**.
