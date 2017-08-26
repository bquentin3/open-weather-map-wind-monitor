# open-weather-map-wind-monitor
import pyowm
from blinkt import *
from time import sleep

set_brightness(0.1)

while True:
    owm = pyowm.OWM('YOUR OPEN WEATHER MAP KEY HERE')  
    observation = owm.weather_at_place("Houston,TX")  
    w = observation.get_weather()  
    t = w.get_temperature('fahrenheit')['temp']
    wind = w.get_wind('miles_hour')['speed']
    wind = round(wind)
    print(w)  
    print("Wind speed: " + (str(wind)) + "mph")
    print("Temp: " + (str(t)) + "F")
    clear()

    if wind <= 3:
        set_pixel(7, 0, 255, 0)
    elif wind <= 6:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
    elif wind <= 9:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
        set_pixel(5, 100, 150, 0)
    elif wind <= 12:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
        set_pixel(5, 100, 150, 0)
        set_pixel(4, 150, 100, 0)
    elif wind <= 15:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
        set_pixel(5, 100, 150, 0)
        set_pixel(4, 150, 100, 0)
        set_pixel(3, 200, 75, 0)
    elif wind <= 18:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
        set_pixel(5, 100, 150, 0)
        set_pixel(4, 150, 100, 0)
        set_pixel(3, 200, 75, 0)
        set_pixel(2, 255, 0, 0)
    elif wind <= 21:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
        set_pixel(5, 100, 150, 0)
        set_pixel(4, 150, 100, 0)
        set_pixel(3, 200, 75, 0)
        set_pixel(2, 255, 0, 0)
        set_pixel(1, 255, 0, 100)
    else:
        set_pixel(7, 0, 255, 0)
        set_pixel(6, 50, 200, 0)
        set_pixel(5, 100, 150, 0)
        set_pixel(4, 150, 100, 0)
        set_pixel(3, 200, 75, 0)
        set_pixel(2, 255, 0, 0)
        set_pixel(1, 255, 0, 100)
        set_pixel(0, 255, 0, 200)
    show()
    sleep(60)
