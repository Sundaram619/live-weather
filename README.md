# live-weather
# 🌤️ Live Weather Prediction Bot

A command-line weather bot that fetches **real-time weather data** for any city worldwide — with **no API key required**.

Built using Python and the free [Open-Meteo API](https://open-meteo.com/).

---

## 📌 Features

- 🔍 Search weather by city name (supports global cities)
- 🌡️ Current temperature & feels-like temperature
- 💧 Humidity percentage
- 🌬️ Wind speed (km/h)
- 🌤️ Weather condition (Clear, Rain, Thunderstorm, Snow, etc.)
- 📅 Today's min/max temperature & precipitation
- 🔁 Auto-retry on network failures (handles timeouts, server errors)
- ✅ No API key needed — 100% free

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| `requests` | HTTP calls to weather API |
| `urllib3` | Retry logic (HTTPAdapter) |
| Open-Meteo Geocoding API | City name → coordinates |
| Open-Meteo Forecast API | Coordinates → live weather |

---

## 📁 Project Structure

```
live-weather-prediction/
│
├── Live_Weather_Prediction.ipynb   # Jupyter Notebook (step-by-step)
├── weather_bot.py                  # Standalone Python script
├── requirements.txt                # Dependencies
├── .gitignore                      # Python gitignore
└── README.md                       # This file
```

---

## ⚙️ Installation & Setup

**1. Clone the repository**
```bash
git clone https://github.com/your-username/live-weather-prediction.git
cd live-weather-prediction
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Run the bot**
```bash
python weather_bot.py
```

Or open `Live_Weather_Prediction.ipynb` in Jupyter Notebook / VS Code.

---

## 🚀 Usage

```
🟦 Weather Bot (free, no API key)
Enter city (e.g., Guwahati / Delhi / Mumbai): Jaipur
```

**Sample Output:**
```
================ WEATHER BOT ================

📍 Location: Jaipur, India
🌡️ Current: 36°C  (Feels like: 38°C)
💧 Humidity: 22%
🌬️ Wind: 14 km/h
🌤️ Condition: Clear sky
📅 Today: Min 28°C | Max 41°C | Rain 0.0 mm

============================================
```

---

## 🔗 APIs Used

- **Open-Meteo Geocoding API** — `https://geocoding-api.open-meteo.com/v1/search`
  - Converts city name to latitude/longitude
- **Open-Meteo Forecast API** — `https://api.open-meteo.com/v1/forecast`
  - Returns live weather using WMO weather codes

Both APIs are **free and open** — no sign-up or key needed.

---

## 🧠 How It Works

```
User enters city name
        ↓
Geocoding API → Get lat/lon/timezone
        ↓
Forecast API → Get current weather + daily stats
        ↓
WMO code mapped to human-readable condition
        ↓
Formatted output printed to console
```

The session uses `urllib3.Retry` to automatically retry on errors (429, 500, 502, 503, 504) with exponential backoff — making it resilient to network glitches.

---

## 📦 Requirements

```
requests>=2.28.0
urllib3>=1.26.0
```

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

## 👤 Author

**Sundaram**  
B.Tech CSE (AI Specialization) | Poornima College of Engineering, Jaipur  
[GitHub](https://github.com/your-username) • [LinkedIn](https://linkedin.com/in/your-profile)
