# weatherApp
A Flask-based web application that provides a 5-day weather forecast for any city in the world. Users enter a city and country, and the app resolves the coordinates via a geocoding API before fetching detailed forecast data from the OpenWeatherMap One Call API.

---
#HOW TO:<br />

🔗 **Live Demo:** ([weatherApp-jdTheBean.pythonanywhere.com](https://weatherApp-jdTheBean.pythonanywhere.com))<br />
#1. Input a relevant City and it's coresponding country into the form.<br />


---

## Features

- Search weather by **city** and **country**
- Displays a **5-day forecast** table including:
  - Date & time
  - High temperature (°C)
  - Humidity
  - Weather icon
  - Wind speed (km/h)
- Shows the **timezone** of the searched location
- Flash messages for invalid or missing input
- Responsive UI with **Bootstrap**

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3, Flask |
| Templating | Jinja2 |
| Frontend | HTML, Bootstrap |
| Geocoding | [API Ninjas Geocoding API](https://api-ninjas.com/api/geocoding) |
| Weather Data | [OpenWeatherMap One Call API 3.0](https://openweathermap.org/api/one-call-3) |
| Config | python-dotenv |

---

## Project Structure

```
weatherApp/
├── wApp.py               # Main Flask application
├── requirements.txt      # Python dependencies
├── .env                  # Environment variables (not committed)
├── static/
│   └── icons/            # Weather condition icons (e.g. 01n@2x.png)
└── templates/
    ├── home.html         # Search form page
    ├── index.html        # Forecast results page
    ├── nav.html          # Shared navigation bar
    └── bootstrap.html    # Bootstrap CDN include
```

---

## Getting Started

### Prerequisites

- Python 3.8+
- A [RapidAPI / API Ninjas](https://api-ninjas.com/) account (for geocoding)
- An [OpenWeatherMap](https://openweathermap.org/) account with One Call API 3.0 access

## Usage

1. On the home page, enter a **city** name and **country** name.
2. Click **Submit**.
3. The app geocodes the location and redirects to the forecast page.
4. A 5-day weather table is displayed with temperature, humidity, wind speed, and weather icons.

---

## API Reference

### Geocoding — API Ninjas

```
GET https://api.api-ninjas.com/v1/geocoding?city={city}&country={country}
Headers: X-Api-Key: <your_key>
```

Returns latitude and longitude for the given city/country pair.

### Weather — OpenWeatherMap One Call 3.0

```
GET https://api.openweathermap.org/data/3.0/onecall?lat={lat}&lon={lon}&units=metric&appid={key}
```

Returns current weather, hourly, and daily forecasts.

---

## Dependencies

See `requirements.txt`. Key packages include:

- `Flask` — web framework
- `requests` — HTTP client for geocoding API
- `python-dotenv` — loads environment variables from `.env`
- `Jinja2` — templating engine (bundled with Flask)

---

## License

This project is licensed under the terms found in the [LICENSE](LICENSE) file.
