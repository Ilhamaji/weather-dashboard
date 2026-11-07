<div align="center">

# Weather Dashboard

Dashboard cuaca **responsif** — cari kota mana pun di dunia dan lihat kondisi saat ini, per jam, dan prakiraan 5 hari.

[![Status](https://img.shields.io/badge/status-complete-brightgreen?style=flat-square)](#)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-5-646CFF?style=flat-square&logo=vite&logoColor=white)](https://vitejs.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind%20CSS-3-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)

**Demo:** [m-cuaca.netlify.app](https://m-cuaca.netlify.app)

</div>

---

## Tentang

Aplikasi cuaca yang fokus pada **kejelasan data**. Alih-alih menumpuk grafik, informasi disusun berlapis: kondisi saat ini sebagai fokus utama, lalu detail (kelembapan, angin, tekanan), kemudian prakiraan per jam dan 5 hari. Latar belakang berubah mengikuti cuaca dan waktu setempat.

## Fitur

- Satu search bar untuk cuaca kota mana pun.
- Kartu kondisi saat ini: suhu, kondisi langit, kelembapan, dan kecepatan angin.
- Prakiraan per jam dengan scroll horizontal (`useHorizontalScroll`).
- Prakiraan 5 hari dengan ikon kondisi.
- Latar berubah mengikuti cuaca dan waktu lewat `getBackground()`, dengan transisi 1 detik.
- Dark mode mengikuti `prefers-color-scheme`.

## Tech Stack

| Bagian | Teknologi |
| --- | --- |
| Framework | React 18 + Vite |
| Styling | Tailwind CSS |
| Data | [OpenWeatherMap API](https://openweathermap.org/api) |
| Ikon | Lucide React / FontAwesome |
| Deploy | Netlify + GitHub Pages |

## Menjalankan

### 1. Clone & install

```bash
git clone https://github.com/Ilhamaji/weather-dashboard.git
cd weather-dashboard
npm install
```

### 2. API key

Daftar gratis di [OpenWeatherMap](https://openweathermap.org/api), lalu buat `.env`:

```env
VITE_OPENWEATHER_API_KEY=your_api_key_here
```

### 3. Jalankan

```bash
npm run dev
```

## Struktur

```
src/
  App.jsx                      # komposisi halaman
  hooks/
    useWeather.js              # fetch current + forecast (hook mendukung query maupun koordinat)
    useHorizontalScroll.js     # scroll per jam
  components/
    SearchBar.jsx              # pencarian kota
    CurrentWeather.jsx         # kartu kondisi saat ini
    WeatherDetails.jsx         # kelembapan, angin, tekanan
    HourlyForecast.jsx         # prakiraan per jam
    Forecast.jsx               # prakiraan 5 hari
    About.jsx                  # info & credit
```

## Endpoint yang Dipakai

```http
GET /data/2.5/weather?q={city}&appid={key}&units=metric
GET /data/2.5/forecast?q={city}&appid={key}&units=metric
```

Hook `useWeather` juga menerima `{lat, lon}` sebagai pengganti `q`, tapi UI saat ini hanya memakai pencarian nama kota.

## Lisensi

MIT — lihat file `LICENSE`.

---

<div align="center">
Dibuat oleh <a href="https://github.com/Ilhamaji">Ilham Aji</a>
</div>
