# OIBSIP_domain_taskno_3
oibsip internship projects are listed here THIRD ONE IS whether app
How It Works

1.User inputs the city name.

2.API request is sent to OpenWeatherMap.

3.JSON data is received and parsed.

4.The app prints temperature, humidity, and weather description.
import requests

# Step 1: Ask the user for a location
city = input("Enter city name: ")

# Step 2: Your API key and URL
api_key = "aa895ea407a0e18b3abfce57125ec26c"  
url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"

# Step 3: Send request and get data
response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    temperature = data['main']['temp']
    humidity = data['main']['humidity']
    description = data['weather'][0]['description']

    # Step 4: Display the weather info
    print(f"\nWeather in {city}:")
    print(f"Temperature: {temperature}°C")
    print(f"Humidity: {humidity}%")
    print(f"Condition: {description.capitalize()}")
else:
    print("Error fetching data. Please check the city name.")
