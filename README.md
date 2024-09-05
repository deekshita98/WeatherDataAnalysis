# WeatherDataAnalysis
This project is a Python-based tool that collects real-time weather data from the OpenWeather API for multiple cities, processes the data by cleaning and filtering it, and generates insights in the form of a structured spreadsheet report. It allows users to fetch weather information such as temperature, humidity, wind speed, and UV index for specific cities, convert temperature units, and analyze conditions based on set thresholds. The tool is particularly useful for monitoring weather patterns across locations and can be easily extended to include additional metrics or cities.

## Cities Covered:
New York City, New York
Denver, Colorado
San Francisco, California
Boston, Massachusetts
Montrose, Colorado

## Project Features:

### API Integration:
- Utilizes the OpenWeather API to fetch weather data in imperial units.
- Specific endpoint used: Weather Overview.
- JSON data is parsed to remove the "tz" key-value pair for each city.

### Data Processing:
- JSON responses are read into a pandas DataFrame.
- The dataset includes essential weather information, such as current temperature, feels-like temperature, wind speed, air pressure, humidity, and UV index.
- Columns for current temperature, feels-like temperature, and uv_index are created.
- Fahrenheit values are converted to Celsius using a new column.
- The data is filtered to include only instances where the daily temperature is below 78°F.

### City Lat-Long Mapping:
- A City Lat-Long table is used to derive city and state names from the latitude and longitude data provided by the API.

### Output:
- The processed data is exported to a spreadsheet file (.xlsx) for easy viewing and analysis.

## Tools Used:
- Python 3.x
- Pandas for data processing and manipulation.
- Requests library for making HTTP requests to the OpenWeather API.
- OpenWeather API to fetch real-time weather data.
- Jupyter Notebook/PyCharm/VS Code (Optional - any Python IDE can be used).
- Spreadsheet Output: Exported using pandas to_excel() function.

## Installation Instructions:

### Clone this repository:

git clone https://github.com/your-username/weather-aggregation-tool.git

cd weather-aggregation-tool

### Install the required Python packages:

pip install -r requirements.txt

### Set up your OpenWeather API Key:
- Sign up at OpenWeather and obtain your free API key.
- Add your API key to the script or set it as an environment variable.
- Run the script:

python weather_data_tool.py

The processed data will be saved to an Excel file named weather_report.xlsx in the project's root directory.

### API Rate Limiting:
To avoid exceeding the free tier's limit of 1,000 API calls, the script ensures minimal calls and uses only five cities for weather data collection.

Thanks!

