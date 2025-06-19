# Automated-Data-Pipeline-for-Real-Time-Analytics
This project automates fetching and visualization of historical and forecast weather data using the [Open-Meteo Weather API](https://open-meteo.com/). It builds an interactive hourly weather dashboard showing temperature and weather codes for a specified location, updating in real-time.

---

## API Source

Weather data is sourced from the **Open-Meteo Weather API**:

- Example API endpoint:

https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.41&hourly=temperature_2m,weather_code&timezone=Europe%2FLondon&past_days=3

yaml
Copy
Edit

- The API provides hourly temperature at 2 meters above ground and weather condition codes, both for past days and forecast.

Learn more at [https://open-meteo.com/](https://open-meteo.com/).

---

## Project Description

The script fetches hourly temperature and weather codes for a location (default: Berlin, Germany) and visualizes them on a single Plotly graph, distinguishing past and forecast data by color.

### Features:

- Fetches past 3 days of data plus forecast from the Open-Meteo API.
- Visualizes temperature and weather codes in one combined interactive graph.
- Differentiates past data (firebrick & royalblue) and forecast data (dark green & orange).
- Optionally saves fetched data as CSV and visualization as HTML files.
- Supports automated periodic runs (e.g., every hour) for real-time analytics.
- Logs progress and errors in the console.

---

## Usage

### Prerequisites

Make sure you have Python 3.7+ and install required packages:

```bash
pip install requests pandas plotly

Output
CSV files: Saved in output/ folder, containing timestamped weather data.

HTML plots: Interactive Plotly graphs saved as timestamped .html files in output/.

The dashboard clearly shows both past and forecast temperature and weather codes, with legends positioned outside the plot for clarity.

Configuration
You can adjust the following parameters inside the script:

LATITUDE and LONGITUDE — change location coordinates

TIMEZONE — set your timezone for time-aware data

PAST_DAYS — number of past days to fetch (default 3)

RUN_INTERVAL_SECONDS — time between pipeline runs in seconds (default 3600 for 1 hour)


OUTPUT_DIR — directory where CSV and HTML files are saved

