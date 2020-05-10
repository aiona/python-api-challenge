# Python API Homework - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would you **prove** it?

![Equator](Images/equatorsign.png)

## Part I - WeatherPy

In this example, I crated a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, I utilized a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

I built a series of scatter plots to showcase the following relationships, followed by a description of the trend shown:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

I then ran linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

I provided a brief analysis of the relationship between each of these factors.

The final notebook provided the following:

* Randomly selected over 500 unique (non-repeat) cities based on latitude and longitude.
* A weather check performed on each of the cities using a series of successive API calls.
* A print log of each city as it's being processed with the city number and city name.
* A saved CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

To showcase my skills working with weather data I generated a list of potential future vacation sites. I used jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** if you have trouble displaying the maps try running `jupyter nbextension enable --py gmaps` in your environment and retry.

* I created a heat map that displays the humidity for every city from the part I of the homework.

  ![heatmap](Images/heatmap.png)

* I narrowed down the DataFrame to find my ideal weather conditions:

  * A max temperature lower than 79 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness
  
  * Humidity less than 75%


* I then used Google Places API to find the first hotel for each city located within 5000 meters of the coordinates.

* Finally, I plotted the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.


