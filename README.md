I used a tutorial website to build a simple weather app website. 
Link = https://www.freecodecamp.org/news/how-to-build-a-website-from-scratch-start-to-finish-walkthrough

Geocode API website = https://open-meteo.com/en/docs/geocoding-api
weather forecast API website = https://open-meteo.com/en/docs

However the Author left errors to be fixed.

The author creates a constant variable named weatherCondition but fails to define weatherDescriptions.

const weatherCondition =
    weatherDescriptions[weather.weathercode] || "Unknown Condition";

This propped an error because the program had no idea what weatherDescriptions was. Once the weather code 
was recieved from the https request, the program had no way to determine what the weather code signified. 

I created a const var that acts as a global dict that the displayWeather() function could use to decipher
the weather code by using it as a key in the weatherDescriptions dict. 

const weatherDescriptions = {
    0: "Clear sky",

    1: "Mainly clear",
    2: "Partly cloudy",
    3: "Overcast",

    45: "Fog",
    48: "Depositing rime fog",

    51: "Light drizzle",
    53: "Moderate drizzle",
    55: "Dense drizzle",

    56: "Light freezing drizzle",
    57: "Dense freezing drizzle",

    61: "Slight rain",
    63: "Moderate rain",
    65: "Heavy rain",

    66: "Light freezing rain",
    67: "Heavy freezing rain",

    71: "Slight snowfall",
    73: "Moderate snowfall",
    75: "Heavy snowfall",

    77: "Snow grains",

    80: "Slight rain showers",
    81: "Moderate rain showers",
    82: "Violent rain showers",

    85: "Slight snow showers",
    86: "Heavy snow showers",

    95: "Thunderstorm",

    96: "Thunderstorm with slight hail",
    99: "Thunderstorm with heavy hail"
};
