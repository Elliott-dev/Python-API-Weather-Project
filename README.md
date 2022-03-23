# Python API Project - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would you **prove** it?

![Equator](Images/equatorsign.png)
## Part I - WeatherPy

Created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this,I utilized a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

The first requirement was to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, I added a sentence or two explaining what the code is analyzing.

The second requirement was  to run linear regression on each relationship. This time, to separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, I took the time to explain what the linear regression is modeling. For example, describe any relationships I noticed and any other analysis I had.

The final notebook:

* Randomly selected **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Included a print log of each city as it's being processed with the city number and city name.
* Saved a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Then I decided to work with weather data to plan future vacations. Used jupyter-gmaps and the Google Places API (part of Google Cloud). (I had trouble displaying the maps, so I ran jupyter nbextension enable --py gmaps in my environment.)

* **Note:** Remember that any API usage beyond the $200 credit will be charged to your personal account. You can set quotas and limits to your daily requests to be sure you can't be charged. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.


* Created a heat map that displays the humidity for every city from Part I.

  ![heatmap](Images/heatmap.png)

* Narrowed down the DataFrame to find an ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Dropped any rows that don't contain all three conditions. I wanted to be sure the weather was ideal.


* Used Google Places API to find the first hotel for each city located within 5000 meters of the coordinates.

* Plotted the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  https://github.com/Elliott-dev/Python-API-Weather-Project/blob/main/Ideal_Vacation.png

As final considerations:

* I completed my analysis using a Jupyter notebook.
* I used the Matplotlib and Pandas plotting libraries.
* I Part I, I included a written description of three observable trends based on the data.
* I Part II, I  included a screenshot of the heatmap you create and include it in your submission.
* I  properly labeled of my plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
*  Max intensity in the heat map, tried setting it to the highest humidity found in the data set.

## Considerations

* The city data I generated is based on random coordinates as well as different query times.

* If you'd like a refresher on the geographic coordinate system, [this site](http://desktop.arcgis.com/en/arcmap/10.3/guide-books/map-projections/about-geographic-coordinate-systems.htm) has great information.

* Next, I spent the requisite time necessary to study the OpenWeatherMap API. Based on your initial study, I was able to answer basic questions about the API: Where did I request the API key? Which Weather API in particular did I need? What URL endpoints did it expect? What JSON structure does it respond with? 
