# **CRYPTO WATCHER**: 
An automated Crypto Price Monitoring & Alerting System

# TABLE OF CONTENTS
- [CATEGORY](#category)
- [DETAILED DESCRIPTION](#detailed-description)
- [HOW IT WORKS (FUNCTIONALITY)](#how-it-works-functionality)
- [TOOL REQUIRED](#tool-required)
- [SIZE OF PROJECT](#size-of-project)
- [SETUP REQUIREMENTS](#setup-requirements)
- [DEPLOYMENT TIME ESTIMATE](#deployment-time-estimate)
- [VALUE PROPOSITION](#value-proposition)
- [KNOWN LIMITATION](#known-limitation)
- [USE CASES](#use-cases)
- [VERSION UPDATES](#version-updates)



# **CATEGORY**
### Finance/Trading Automation
<img width="1536" height="1024" alt="Crypto Watcher Dashboard Design" src="https://github.com/user-attachments/assets/c2228513-45a3-44e2-9f1b-eb5e42647267" />

### The lovable UI wepage can be accessed [HERE](https://coin-watch-airtable.lovable.app/)
<img width="1857" height="1012" alt="Lovable UI 2" src="https://github.com/user-attachments/assets/272117ae-0a1a-4479-a0c4-c0075fb4ec6f" />

### The make.com workflow can be scenario can be viewed [HERE](https://eu2.make.com/public/shared-scenario/WvgND3qy38u/crypto-price-monitoring-system)
<img width="1904" height="1098" alt="Crypto watcher make com workflow" src="https://github.com/user-attachments/assets/1f8f9c77-4070-4d50-858b-4399a619873c" />


## **DETAILED DESCRIPTION**
Crypto Watcher is an automated cryptocurrency monitoring system designed for independent traders who want real-time insights without constant manual checking.

Crypto markets move fast, and missing significant price movements can impact trading opportunities. Traders often spend hours refreshing apps or websites to track volatility across multiple assets. This workflow automates the entire process: fetching enriched crypto data from CoinGecko via Make.com, filtering results according to preset trading conditions, and delivering alerts across multiple Telegram channels.

The solution also stores structured data in Airtable and Google Sheets for long-term trend analysis. For traders who prefer visual dashboards, the system integrates with Supabase + Lovable.ai to provide a responsive UI that highlights price trends, significant moves, and trending coins.

### **Expected outcomes**:
-  Traders receive real-time alerts tailored to their rules.
-  Price history and metrics are logged automatically for deeper analysis.
-  Users access a clean, dark-themed dashboard to visualize metrics, alerts, and trending tokens in real time.

## **HOW IT WORKS (FUNCTIONALITY)**
-  **Trigger**
    -  A polling trigger in a HTTP module initiates the workflow in **30-minute** intervals

 <img width="1473" height="1022" alt="Screenshot 2025-12-05 191528" src="https://github.com/user-attachments/assets/eaf95162-ee96-4d99-adb5-b7e3fd827025" />

-  **Crypto Data Retrieval**
    -  The CoinGecko API from the HTTP module fetches enriched crypto data, including
          -  Current price (USD)
          -  24h price change (%)
          -  Market capitalization
          -  24-hour trading volume
          -  Last updated timestamp
          -  Coin logo
          -  Metadata (supply, ATH, trending status)

<img width="1683" height="1139" alt="Screenshot 2025-12-05 191722" src="https://github.com/user-attachments/assets/9b40345f-63a1-4f6e-a107-454221782687" />

-  **Filtering Logic**
   -  Rules applied in Make.com:
         -  When the price change of any coin in the last **24 hours is >= +5%**, an alert and details of the coins are sent to an individual Telegram bot chat named *‘paz bullish.’*
         -  When the price change of any coin in the last **24 hours is <= -5%**, it sends an alert and details of the coin to an individual Telegram bot chat named *‘paz bearish.’*

<img width="1013" height="831" alt="Screenshot 2025-12-05 192039" src="https://github.com/user-attachments/assets/f37b555d-9f24-4f20-9914-f537793ab10b" />

<img width="840" height="856" alt="Screenshot 2025-12-05 192048" src="https://github.com/user-attachments/assets/01dbee67-487e-46d5-a7c1-263a1d0e60f7" />


-  **Data Logging**
    -  Data written into Airtable (structured records).
    -  Data is also mirrored into Google Sheets for backup & lightweight analysis.
    -  Data is also logged into Superbase simultaneously.
 

<img width="1907" height="914" alt="Screenshot 2025-09-14 223221" src="https://github.com/user-attachments/assets/272d0a07-d4b9-4ef6-a39f-9fe9d6a35b31" />

<img width="1838" height="846" alt="Screenshot 2025-09-12 221842" src="https://github.com/user-attachments/assets/1955720a-8828-445d-8d61-cc136451e105" />

<img width="1859" height="966" alt="Screenshot 2025-12-05 200128" src="https://github.com/user-attachments/assets/01d3b21c-6c5c-4f29-8116-16b2196fa436" />

-  **Notifications**
    -  Alerts sent via Telegram Bot with coin name, price, % change, market cap, and logo.

<img width="1232" height="1148" alt="Screenshot 2025-12-05 192426" src="https://github.com/user-attachments/assets/5b2ad081-c4b4-462a-830b-12a26a70a39e" />

-  **Dashboard UI**
    -  Supabase backend powers Lovable. AI frontend.
    -  The dashboard displays live prices, % change, market cap, volume, logo, and alerts.
    -  Sections include Trending Coins, High-Potential Coins, and an Alerts Feed.
   
<img width="1896" height="986" alt="Lovable UI" src="https://github.com/user-attachments/assets/852e1fc1-dabc-4b8a-8362-b8a34e08d89d" />


## **TOOL REQUIRED**
-  Make.com (workflow automation)
-  CoinGecko API (crypto data)
-  Airtable (structured storage)
-  Google Sheets (backup storage + logging)
-  Telegram (alert delivery)
-  Supabase (database backend for UI)
-  Lovable.ai (frontend UI builder)

## **SIZE OF PROJECT**
Medium (**5–6 tasks**: API retrieval, filtering, logging, notification, dashboard UI).

## **SETUP REQUIREMENTS**
-  API key for CoinGecko (public/free).
-  Airtable API key + base ID.
-  Google account (Google Sheets).
-  Supabase project setup (database + API key).
-  Telegram bot token.

## **DEPLOYMENT TIME ESTIMATE**
-  Initial setup: **4–5 hours**.
-  With customizations (alert thresholds, UI refinements): **5–7 days**.

## **VALUE PROPOSITION**
### For independent traders:
-  Saves **5–10 hours** per week otherwise spent manually tracking charts.
-  Reduces the risk of missed trading opportunities.
-  Centralizes data for custom strategies.
-  Allows the crypto trader focus on more tasks while

## **KNOWN LIMITATION**
-  CoinGecko API rate limits (**50–100 calls/minute**).
-  Telegram alerts depend on internet connection.
-  Supabase hosting costs may scale with traffic.
-  Requires Airtable API access (the free tier limits **1,000 records**).

## **USE CASES**
-  Tested by independent traders to monitor Bitcoin & Ethereum.
-  Alerts successfully delivered during a 10% BTC swing.
-  The dashboard provided a snapshot of 5 tracked coins for real-time monitoring.

## **VERSION UPDATES**
-  **v1.0** - Initial set up with a webhook trigger 
-  **v1.1** - Reimagined and used a HTTP module polling trigger 
-  **v1.2** - Initial release with CoinGecko API + Airtable + Telegram.
-  **v1.3** - Added Google Sheets backup logging.
-  **v1.4** - Integrated Supabase + Lovable frontend dashboard.










