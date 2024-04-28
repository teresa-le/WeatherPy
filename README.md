# World Weather - Creating a Travel Itinerary 

## Purpose 
The purpose of this project was to use Python, OpenWeatherMap's APIs and Geoapify's APIs to allow PlanMyTrip's app users to do the following: 
* Find their ideal cities to vacation in based on their weather preferences,
* suggest the nearest hotels in those cities to help users find accommodations and make their trip a reality,
* and help users develop a travel itinerary and travel route for a trip between four cities. 

## Data Sources
- WeatherPy API for obtaining weather data
- Geoapify Routing API for generating the travel route

## Skills Used 
Python, Data Wrangling, Data Visualization, API Interaction and Data Retrieval 

## Actions 
In this project, I began by importing the necessary dependencies and configuring the Geoapify API key. Utilizing GeoViews, I created a map displaying all cities from the vacation_df DataFrame. The map was configured to include temperatures, city names and additional information such as hotel names, country, and current weather description.

Next, I selected four cities in close proximity within the same country from the map and created separate DataFrames for each city using the loc method. These DataFrames represented the starting point, ending point, and two stops along the travel route. Using the Pandas concat function, I merged these DataFrames to create a new DataFrame named itinerary_df to store the itinerary details. I then used the Pandas copy function to create a DataFrame named waypoints_df to store the longitude and latitude for each city in itinerary_df. 

Afterward, I configured a new map using GeoViews to display the four cities in the itinerary. I utilized the Geoapify Routing API to find a route between the cities in the itinerary. This involved setting initial parameters, fetching coordinates from each city, defining the waypoints parameter using a for loop, and making a request to the API to retrieve route directions.

From the JSON response obtained, I stored the route's legs coordinates in a variable called legs. I then looped through these coordinates to fetch latitude and longitude for each step, storing them in Python lists named longitude and latitude. Using these lists, I created a new DataFrame named route_df.

Finally, I configured a line plot using GeoViews' Path function with the route_df DataFrame. The route path was styled with a custom color and width to contrast with the map. The composed plot displayed the itinerary's route over the map containing the cities.
