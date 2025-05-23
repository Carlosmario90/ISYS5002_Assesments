# ISYS5002_Assesments

🌦️ Weather Advisor Application
Date: 23/05/2025
Version: 1.0
Author: Carlos Mario Palacios Mosquera
Run the file " WEATHER ADVISOR APP"

🧾 Overview
This application provides weather forecasts using natural language queries. It supports multiple cities, visualizations for temperature and precipitation, and highlights conditions like rain or heat. Users can input questions like:

"Will it rain in Sydney in 2 days?"
"What's the weather in Perth on Friday?"

It supports:
🌡️ Current and forecast weather (up to 5 days)
🗺️ Multi-city comparisons
📊 Interactive visualizations
🧠 Natural Language Understanding (NLU)

🛠️ Setup and Configuration

1️⃣ Install Required Packages
Run the first section to install and import all necessary libraries:

!pip install pyinputplus fetch-my-weather hands-on-ai dateparser ipywidgets pandas matplotlib
Then import packages and configure timezone:
import matplotlib.pyplot as plt
import pandas as pd
import pyinputplus as pyip
import pytz
from datetime import datetime, timedelta
local_tz = pytz.timezone('Australia/Perth')
today = datetime.now(local_tz).date()

SECTION 1
☀️ Weather Data Functions
This section defines the function get_weather_data(location, forecast_days) to fetch:

Current conditions (temperature, humidity, wind)

5-day forecast (one point daily around noon)

✅ Run this section before querying any weather data.

SECTION 2
📊 Visualisation Functions

Temperature Chart
The function create_temperature_visualisation(weather_data) displays:

Max, Min, and Avg temperatures
Max and Min are randomly varied ±(1 to 3.5°C) from the avg to simulate realistic spread

Precipitation Chart
The function create_precipitation_visualisation(weather_data) displays:
Rainfall (mm) for each forecast day

💡 Ensure you run these functions after retrieving weather data.

SECTION 3
🤖 Natural Language Processing
parse_weather_question(question: str)
Extracts: location, forecast day offset (0–4), and attributes like rain/hot/cold.

Handles inputs like:
"What’s the weather in Tokyo tomorrow?"
"Will it rain in Melbourne in 3 days?"

⚠️ Returns an error for unsupported or unclear queries

🧠 Section 4 – Weather Response Generator
generate_weather_response(parsed_question, weather_data)

Returns a friendly sentence answering the user's weather question.

Example Output:

"On Saturday in Melbourne, the forecast is clear with 16°C and 0.0mm of rain."

🧑‍💻 Section 5 – Interactive UI
Run interactive_multi_day_city_weather_ui()
This launches the main UI:

📥 Input your natural question

➕ Add multiple cities

📊 View temperature and rain forecasts per city

🔍 Highlights the relevant day and weather attribute (e.g., rain)

✅ Final Tips
Make sure your API key from OpenWeatherMap is valid and pasted correctly in the get_weather_data() function.

Questions must include a valid city and a reference to time (e.g., tomorrow, in 2 days).

You can extend the visualizations using tooltips or Seaborn, which is already imported as sns.
