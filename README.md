<div align="center">

# Weather Dashboard

A **responsive** weather dashboard — search any city and see current conditions, an hourly breakdown, and a 5-day forecast.

[![Status](https://img.shields.io/badge/status-complete-brightgreen?style=flat-square)](#)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-5-646CFF?style=flat-square&logo=vite&logoColor=white)](https://vitejs.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind%20CSS-3-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)

**Demo:** [m-cuaca.netlify.app](https://m-cuaca.netlify.app)

**English** · [Bahasa Indonesia](README.id.md)

</div>

---

## About

A weather app built around **clarity of data**. Rather than stacking charts, the information is layered: current conditions as the focal point, then the details (humidity, wind, pressure), then hourly and 5-day forecasts. The background shifts with the weather and time of day.

## Features

- One search bar for any city.
- Current-conditions card: temperature, sky condition, humidity, and wind speed.
- Hourly forecast with horizontal scrolling (`useHorizontalScroll`).
- 5-day forecast with condition icons.
- Background changes with weather and time via `getBackground()`, with a 1-second transition.
- Dark mode follows `prefers-color-scheme`.

## Tech Stack

| Layer | Technology |
| --- | --- |
| Framework | React 18 + Vite |
| Styling | Tailwind CSS |
| Data | [OpenWeatherMap API](https://openweathermap.org/api) |
| Icons | Lucide React / FontAwesome |
| Deployment | Netlify + GitHub Pages |

## Getting Started

### 1. Clone and install

```bash
git clone https://github.com/Ilhamaji/weather-dashboard.git
cd weather-dashboard
npm install
```

### 2. API key

Sign up for free at [OpenWeatherMap](https://openweathermap.org/api), then create `.env`:

```env
VITE_OPENWEATHER_API_KEY=your_api_key_here
```

### 3. Run

```bash
npm run dev
```

## Project Layout

```
src/
  App.jsx                      # page composition
  hooks/
    useWeather.js              # fetch current + forecast (accepts a query or coordinates)
    useHorizontalScroll.js     # hourly scrolling
  components/
    SearchBar.jsx              # city search
    CurrentWeather.jsx         # current-conditions card
    WeatherDetails.jsx         # humidity, wind, pressure
    HourlyForecast.jsx         # hourly forecast
    Forecast.jsx               # 5-day forecast
    About.jsx                  # info and credits
```

## Endpoints Used

```http
GET /data/2.5/weather?q={city}&appid={key}&units=metric
GET /data/2.5/forecast?q={city}&appid={key}&units=metric
```

The `useWeather` hook also accepts `{lat, lon}` in place of `q`, but the UI currently only uses city-name search.

## License

MIT — see the `LICENSE` file.

---

<div align="center">
Built by <a href="https://github.com/Ilhamaji">Ilham Aji</a>
</div>
