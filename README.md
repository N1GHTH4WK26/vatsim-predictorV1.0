# vatsim-predictorV1.0
Global VATSIM ATC staffing predictor and route feasibility bot for virtual airlines.

# 🌍 VATSIM Staffing Coverage Predictor & Dispatch Analytics

An automated data-collection and predictive analytics engine designed for Virtual Airlines and flight simulation communities to forecast VATSIM Air Traffic Control (ATC) staffing probabilities. 

---

## 🚀 Features

### ✈️ Predictive Analytics
* **`/predict`**: Forecast the historical staffing probability of any VATSIM Center, ARTCC, or FIR prefix at a specific day and UTC hour.
* **`/hubs`**: Interactive drop-down menu to instantly check staffing probabilities for primary Virtual Airline operational centers.
* **`/top_atc`**: View a leaderboard of the most active, consistently staffed VATSIM facilities across database observations.

### 🛫 Global Route Checking
* **`/route_check`**: Enter an origin and destination ICAO anywhere worldwide. The bot’s global routing engine dynamically translates the airports to their controlling enroute FIR/ARTCC prefixes and forecasts end-to-end trip feasibility.

### 🔔 Proactive Alerts & Summaries
* **`/alert_me`**: Subscribe to a specific FIR/ARTCC prefix and receive a Discord Direct Message (DM) the moment that facility comes online.
* **`/daily_summary_subscribe`**: Opt-in to receive a daily DM summarizing the network's top staffing hotspots directly to your inbox.

---

## 📌 Prerequisites (What you need before starting)

1. **Python 3.8 or Higher** installed on the machine/server.
2. **A Discord Account** with "Administrator" permissions in the server where you want to add the bot.
3. **A 24/7 machine or server** (Highly recommended to run the `collector.py` 24/7 so your database continuously logs VATSIM airspace data).

---

## 🛠️ Step 1: Discord Bot Setup & Configuration

You need to register the bot with Discord to get an access token:

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications) and log in.
2. Click the blue **New Application** button in the top right. Name it something like *VA Dispatcher* and save.
3. On the left menu, click **Bot**.
4. Click **Reset Token**, confirm it, and click **Copy**. Save this massive string of numbers and letters somewhere safe—this is your bot's password.
5. Scroll down on that same Bot page to the *Privileged Gateway Intents* section.
6. Turn ON the toggle for **Message Content Intent** (and click save changes at the bottom).

### Adding Environment Credentials
1. Look inside the project folder and locate the file named `.env.example`.
2. Rename the file to exactly `.env` (remove the `.example` part).
3. Open the `.env` file with any text editor and paste your copied token:
   ```env
   DISCORD_TOKEN=your_copied_discord_token_here
