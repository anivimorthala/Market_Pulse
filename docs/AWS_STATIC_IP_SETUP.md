# ☁️ AWS EC2 Static IP & Order Proxy Setup Guide

> **Prefer a downloadable 2-page PDF?** 👉 **[Download AWS_Kotak_Static_IP_Setup_Guide.pdf](AWS_Kotak_Static_IP_Setup_Guide.pdf)** *(also bundled inside the Market Pulse app under `Profile → Static Order IP Binding → ⋮ Menu`)*.

---

## Why Is a Static IP Required?

Exchange and SEBI compliance mandates that automated API order routes (**place, modify, cancel**) on **Kotak Neo** originate from a **whitelisted Static IP**.

Hosting an ultra-lightweight Nginx forwarding proxy on **AWS Free Tier (Mumbai `ap-south-1`)** gives you:
- A **permanent, unchanging Elastic IP**
- **Ultra-low latency** to Indian broker servers
- **Zero monthly cost** under AWS 12-Month Free Tier (750 hours/month)

---

## Phase 1: Create an AWS Free Tier Account

1. Go to **[aws.amazon.com](https://aws.amazon.com/)** and click **Create an AWS Account**.
2. Complete email & identity verification (AWS verifies your card via a small refundable test charge).
3. Select the **Basic Support (Free)** plan.
4. Log into the **AWS Console** and in the top-right region selector, choose **Asia Pacific (Mumbai) `ap-south-1`** for lowest trading latency.

---

## Phase 2: Launch Your EC2 Instance

1. In the AWS search bar, type **EC2** → click **Instances → Launch Instances**.
2. **Name:** `kotak-trading-proxy`
3. **OS Image (AMI):** **Ubuntu Server 24.04 LTS** *(Free Tier eligible)*
4. **Instance Type:** **`t2.micro`** or **`t3.micro`** *(Free Tier eligible)*
5. **Key Pair:** Click **Create new key pair** → name it `trading-key` → format `.pem` → download and keep it safe.
6. **Network Settings (Firewall / Security Group):**
   - ✅ Check **Allow SSH traffic from Anywhere (Port 22)** *(or your IP)*
   - ✅ Check **Allow HTTP traffic from the internet (Port 80)**
7. Click **Launch Instance** — your server boots in ~30 seconds.

---

## Phase 3: Allocate Your Permanent Elastic IP

1. In the EC2 left sidebar, go to **Network & Security → Elastic IPs**.
2. Click **Allocate Elastic IP address** → **Allocate**.
3. Select the newly created Elastic IP → click **Actions → Associate Elastic IP address**.
4. **Resource type:** `Instance` → select your **`kotak-trading-proxy`** instance → click **Associate**.
5. Copy the assigned **Public IPv4 address** (for example `13.232.xxx.xxx`). This is your permanent Static IP.

---

## Phase 4: 1-Click Browser Proxy Setup (No SSH Client Needed)

1. Go back to **EC2 → Instances**, select **`kotak-trading-proxy`**, and click **Connect** (top button).
2. Under **EC2 Instance Connect**, click **Connect** — a Linux terminal opens right inside your web browser.
3. Copy and paste this **single command block** into the browser terminal and press **Enter**:

```bash
sudo apt-get update -y && sudo apt-get install -y nginx && cat << 'EOF' | sudo tee /etc/nginx/sites-available/kotak-proxy
server {
    listen 80 default_server;
    server_name _;

    resolver 8.8.8.8 1.1.1.1 ipv6=off valid=300s;
    resolver_timeout 5s;

    location / {
        proxy_pass https://mis.kotaksecurities.com;
        proxy_set_header Host mis.kotaksecurities.com;
        proxy_ssl_server_name on;
        proxy_ssl_protocols TLSv1.2 TLSv1.3;
        proxy_ssl_session_reuse on;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
EOF
sudo rm -f /etc/nginx/sites-enabled/default
sudo ln -sf /etc/nginx/sites-available/kotak-proxy /etc/nginx/sites-enabled/
sudo nginx -t && sudo systemctl restart nginx && sudo systemctl enable nginx
```

✅ **Result:** Production Nginx proxy with DNS resolvers and TLS SNI headers is live in under 5 seconds!

---

## Phase 5: Whitelist Your Elastic IP in Kotak Neo

1. Log into **Kotak Neo** (mobile app or web portal).
2. Go to **More → Trade API** → select your **API Application**.
3. Click **Add IP**, paste your **AWS Elastic IP** from Phase 3, and click **Save**.

> **Note:** Kotak Neo allows changing the whitelisted IP once every 7 days, so always whitelist the permanent **Elastic IP** (not a temporary instance IP).

---

## Phase 6: Bind & Test Inside Market Pulse

1. Open **Market Pulse** → go to **Profile → Static Order IP Binding**.
2. In the endpoint field, enter:
   ```text
   http://YOUR_AWS_ELASTIC_IP
   ```
3. Tap **Test Ping** — confirm it shows **`Proxy Online (Kotak Connected)`**.
4. Tap **Save & Bind Static IP**.
5. Complete the prompted quick **TOTP Re-login** so Kotak Neo binds your session directly to your Static IP.

🎉 **Done!** All manual orders, Algo Terminal executions, and Target/SL exits now route cleanly through your own whitelisted Static IP.

---

## 💡 Zero-Cost Rules & Budget Safeguards

- **Keep Your Instance Running 24/7:** AWS Elastic IPs are **100% free** while attached to a running instance. Do not stop the instance while keeping an Elastic IP attached.
- **Free Tier Allowance:** `t2.micro` / `t3.micro` includes **750 hours/month free** for 12 months (enough to run 24 × 31 uninterrupted).
- **Set a $5 Budget Alert:** In AWS Console → search **Budgets** → **Create Budget** → set a monthly limit of **$5.00** with an alert at **$4.00** for complete peace of mind.
