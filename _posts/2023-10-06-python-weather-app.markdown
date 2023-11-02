---
title:  "Stay Weather-Ready - Building a Python Weather App"
date:   2023-10-06
---

Welcome back to PyMakers, your source for Python projects that keep you informed and prepared. In this project, we're diving into the world of weather forecasting by building a "Weather App" using Python. This app allows you to fetch and display current weather information to stay weather-ready.

<h4>Why a Weather App?</h4>

Weather plays a crucial role in our daily lives, influencing our decisions and activities. By creating a Weather App in Python, you'll not only learn about web requests, APIs, and data parsing but also have a handy tool to access real-time weather information. It's a project that combines practicality with technical skills.

<h4>The Python Code</h4>

Let's jump straight into the Python code for our Weather App:

{% highlight python %}
import requests

# Function to fetch weather data
def get_weather(city):
    api_key = "YOUR_API_KEY"  # Replace with your API key, get it here: https://openweathermap.org/api
    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}"
    response = requests.get(url)
    data = response.json()
    return data

# Function to display weather information
def display_weather(weather_data):
    if weather_data["cod"] == 200:
        temperature = weather_data["main"]["temp"]
        weather = weather_data["weather"][0]["description"]
        print(f"Weather: {weather}")
        print(f"Temperature: {temperature} K")
    else:
        print("City not found. Please check the city name and try again.")

if __name__ == "__main__":
    city = input("Enter a city: ")
    weather_data = get_weather(city)
    display_weather(weather_data)
{% endhighlight %}

<h4>How it Works</h4>
<ol>
	<li>We import the <code>requests</code> library to make HTTP requests to a weather API.</li>
	<li>We define a function, <code>get_weather()</code>, to fetch weather data for a specified city. You'll need to replace "YOUR_API_KEY" with your actual API key from a weather service provider.</li>
	<li>The weather data is obtained in JSON format and stored in the <code>data</code> variable.</li>
	<li>We define a function, <code>display_weather()</code>, to extract and display the weather and temperature information from the JSON data.</li>
	<li>In the main block, the user is prompted to enter a city name. The <code>get_weather()</code> function is called to fetch weather data, and the <code>display_weather()</code> function is used to show the weather information.</li>
</ol>

<h4>Conclusion</h4>

Congratulations! You've just created a Python Weather App. This project equips you with the ability to access and display real-time weather data, making it an excellent tool for staying informed and prepared.

Whether you're planning outdoor activities, traveling, or just curious about the weather, the Weather App helps you make weather-conscious decisions. Stay tuned for more Python projects that empower you with practical and technical skills. Happy coding and stay weather-ready! 🐍🌦️