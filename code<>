import requests
import json

api_key = "The National Weather Service "


base_url = "http://api.openweathermap.org/data/2.5/weather?"


def get_weather(city):
    
    complete_url = base_url + "appid=" + api_key + "&q=" + city

    
    response = requests.get(complete_url)

    
    data = response.json()

    
    if data["cod"] == "404":
        return "City not found. Please enter a valid city name."

    
    weather = data["weather"][0]["description"]
    temperature = round(data["main"]["temp"] - 273.15, 2) # convert Kelvin to Celsius
    humidity = data["main"]["humidity"]

    
    message = f"Current weather in {city}: {weather}, Temperature: {temperature}°C, Humidity: {humidity}%."

    return message


if __name__ == '__main__':
    city = input("Enter city name: ")
    print(get_weather(city))
