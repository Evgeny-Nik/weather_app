# My Weather Application
this is a python application that gets and shows weather forecast for day (7AM) and night (7PM)
and daily humidity levels for the next 7 days using Visual Crossing Weather API.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install requirements on your virtual environment.

```bash
pip install -r requirements.txt
```


## How To Run

Use the following python file to run the program

```bash
run app.py
```

## Functions
 Use the functions within:
```python
import weather_funcs

# receives a string for a location
# returns a parsed list with location name and 7 dictionaries with keys: 
# day, date, day_icon, day_temp, night_temp, humidity
# using parse_json_data
weather_funcs.send_request('haifa')

# receives a 15 day weather forecast data from visual crossing api
# returns a parsed weather_json with the data state above
weather_funcs.parse_json_data(weather_json)
```

## Data
 Example of typical visual crossing API json response:
```json
{
     "latitude" : 38.9697,
     "longitude" : -77.385,
     "resolvedAddress" : "Reston, VA, United States",
     "address" : " Reston,VA",
     "timezone" : "America/New_York",
     "tzoffset" : -5, 
     "description":"Cooling down with a chance of rain on Friday.", 
     "days" : [{ //array of days of weather data objects
         "datetime":"2020-11-12",
         "datetimeEpoch":1605157200,
         "temp" : 59.6,
         "feelslike" : 59.6,
         ...
         "stations" : {
         },
         "source" : "obs",
         "hours" : [{  //array of hours of weather data objects  
             "datetime" : "01:00:00",
             ...
         },...]
     },...],
     "alerts" : [{
             "event" : "Flash Flood Watch",
             "description" : "...",
             ...
         }
     ],
     "currentConditions" : {
         "datetime" : "2020-11-11T22:48:35",
         "datetimeEpoch" : 160515291500,
         "temp" : 67.9,
         ...
     }
}
```
Example data for 'haifa, israel' post parse_json_data function:
```python
[
    "\u05d7\u05d9\u05e4\u05d4, \u05d9\u05e9\u05e8\u05d0\u05dc", 
    {
        "day": "Saturday",
        "date": "27-01-2024",
        "day_icon": "rain",
        "day_temp": 12.0,
        "night_temp": 15.0,
        "humidity": 65.0
    },
    {
        "day": "Sunday",
        "date": "28-01-2024",
        "day_icon": "rain",
        "day_temp": 10.4,
        "night_temp": 11.3,
        "humidity": 82.4
    },
    {
        "day": "Monday",
        "date": "29-01-2024",
        "day_icon": "rain",
        "day_temp": 10.0,
        "night_temp": 10.6,
        "humidity": 85.2
    },
    {
        "day": "Tuesday",
        "date": "30-01-2024",
        "day_icon": "rain",
        "day_temp": 9.6,
        "night_temp": 10.6,
        "humidity": 86.4
    },
    {
        "day": "Wednesday",
        "date": "31-01-2024",
        "day_icon": "rain",
        "day_temp": 9.4,
        "night_temp": 9.9,
        "humidity": 83.0
    },
    {
        "day": "Thursday",
        "date": "01-02-2024",
        "day_icon": "rain",
        "day_temp": 9.7,
        "night_temp": 9.8,
        "humidity": 82.5
    },
    {
        "day": "Friday",
        "date": "02-02-2024",
        "day_icon": "rain",
        "day_temp": 8.9,
        "night_temp": 12.2,
        "humidity": 65.6
    }
]
```

## References
API ->
[Visual-Crossing](https://www.visualcrossing.com/weather-api)

Python code ->
[Bootstrap-5](https://getbootstrap.com/)
[Flask](https://flask.palletsprojects.com/en/3.0.x/)

Animated Icons ->
[Makin-Things](https://github.com/Makin-Things)