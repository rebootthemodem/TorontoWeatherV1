# TorontoWeather

The `TorontoWeather` project contains a `WeatherService` class that fetches weather information for Toronto using the Open-Meteo API. This service retrieves daily maximum and minimum temperatures for Toronto and formats the results as a string.

## Features

- Fetches weather data asynchronously using the Open-Meteo API.
- Retrieves both daily maximum and minimum temperatures for Toronto.
- Parses the JSON response with `Newtonsoft.Json` (JObject) for easier data manipulation.

## Requirements

- .NET 5 or later.
- Internet access to fetch data from the Open-Meteo API.
- [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/) for JSON parsing.

## Getting Started

### Install Dependencies

Before using the `WeatherService` class, ensure that your project includes the necessary dependencies. Install `Newtonsoft.Json` via NuGet:

```bash
dotnet add package Newtonsoft.Json

### Example Usage

using System;
using System.Threading.Tasks;

namespace TorontoWeather
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var weatherService = new WeatherService();
            var weatherData = await weatherService.GetTorontoWeatherAsync();

            Console.WriteLine($"Toronto Weather Data:\n{weatherData}");
        }
    }
}

###How It Works
WeatherService Constructor: Initializes the HttpClient used to send HTTP requests.

GetTorontoWeatherAsync() Method:

Constructs the URL with the appropriate query parameters for latitude, longitude, daily max and min temperature, and timezone.
Sends an asynchronous GET request to fetch weather data in JSON format.
Returns a formatted string with the dates and corresponding maximum temperatures.
ExtractMaxTemperaturesAndDays() Method:

Extracts the daily maximum temperatures and the corresponding days from the parsed JSON response.
Builds a formatted string that displays each day along with its maximum temperature in Celsius.

###Sample Output
Toronto Weather Data:
2024-11-08: 12.3°C
2024-11-09: 13.5°C
2024-11-10: 14.6°C
2024-11-11: 15.2°C
2024-11-12: 16.1°C

###API Details
The service uses the Open-Meteo API to fetch weather data. Specifically, it requests:

latitude: 43.7 (Toronto's latitude).
longitude: -79.42 (Toronto's longitude).
daily: temperature_2m_max, temperature_2m_min (daily maximum and minimum temperature).
timezone: America/Toronto (to get the weather data in the Toronto timezone).
For more information on the Open-Meteo API, visit the Open-Meteo Documentation.

###Contributing
Contributions are welcome! If you have suggestions or improvements for this service, feel free to fork this repository and submit a pull request.

###License
This project is licensed under the MIT License - see the LICENSE file for details.


This `README.md` provides a detailed explanation of the updated `WeatherService`, highlighting the ability to fetch both daily maximum and minimum temperatures for Toronto, and gives example usage, expected output, and more. Let me know if you need further modifications!







