# CapstoneProjectMontreal

## Project/Goals

This is my capstone project investigating how the numbers and the qualities of the Bars and Restaurants in Montreal can be predicted by the numbers of nearby transit stations including CityBikes stations, subway stations, and light rail stations.
The project was focused on data retreival from APIs, data visualization, and statistical modelling. All of the data collected in this project was from either CityBikes API or Google Places API.

This project produced many different variations of the analysis in an attempt to find which were the most predictive.

The things I worked to predict include:
1. How the number of nearby transit stations predicts the number of nearby bars and restaurants.
2. How the number of nearby rail stations preducts the number of nearby bars and restaurants.
3. How the number of nearby transit stations predicts the number of nearby bars.
4. How the number of nearby rail stations predicts the number of nearby bars.
5. How the number of nearby transit stations predicts the number of nearby restaurants.
6. How the number of nearby rail stations predicts the number of nearby restaurants.
7. How the number of nearby transit stations predicts the rating of bars and restaruants on Google API.
8. How the number of nearby rail stations predicts the rating of bars and restaruants on Google API.
9. How the number of nearby transit stations predicts the rating of bars on Google API.
10. How the number of nearby rail stations predicts the rating of bars on Google API.
11. How the number of nearby transit stations predicts the rating of restaurants on Google API.
12. How the number of nearby rail stations predicts the rating of restaurants on Google API.
13. How the number of nearby transit stations predicts the price of bars and restaruants on Google API.
14. How the number of nearby rail stations predicts the price of bars and restaruants on Google API.
15. How the number of nearby transit stations predicts the price of bars on Google API.
16. How the number of nearby rail stations predicts the price of bars on Google API.
17. How the number of nearby transit stations predicts the price of restaurants on Google API.
18. How the number of nearby rail stations predicts the price of restaurants on Google API.

Types of data visualization I produced include:

1. Map diagrams.
2. Scatterplots.
3. Bar Graphs.
4. Histograms.
5. Box Plots.

Types of regression analysis I did include:

1. Multivariable linear regression analysis.
2. Logistic regression analysis.

## Process

#### city_bikes_capstone

First step was to import my pandas, os, and requests packages.

Second step was to query the citybikes API, parse the results as a data frame, and then sort through the data frame to find the API call link specific to Montreal.

Third step was to query the API for citybikes specific to Montreal, then parse the results as a data frame.

Fourth step was to import my geohashes package and add precision 5 geohashes to my dataframe.

#### extracting_montreal_subway_from_google_places_api

First step was to import my pandas, numpy, os, and requests packages and set my working directory.

Second step was to set my API key.

Third step was to do a test call of the API to ensure that it worked.

Fourth step was to call the API to retrieve all of the subway stations in Montreal.

I also added precision 6 geohashes in this notebook and saved my results as a CSV.

I noticed that the API would only give me the first 60 subway statons when there are 68 stations in montreal. I looked up the remaining stations and added their information to the CSV in Excel.

#### extracting_montreal_light_rail_from_google_places_api

This was the same process as my extracting_montreal_subway_from_google_places_api except I called the API on light rail stations instead of subways stations.

#### extracting_bars_from_google_places_api

This was the same process as my previous google places api notebooks. However I ran into a problem that my Google Places API call loop was returning a maximum of 60 places per API call. I looked this up and this maximum is built into the function of the API itself.
So I prepared a list of latitude longitude coordinates for all the citybikes and rail stations and a grid covering downtown Montreal. I broke the list into chunks and looped over all of them, concatenated the results, and removed the duplicates. I saved the results as a CSV.

#### extracting_restaurants_from_google_places_api

This was the same process as my notebook for the bars except I called it on the restaurants.

#### joining_data

In this notebook I created concatenated data frames containing information about all the transit stations, all the rail stations, and all the bar/restaurant establishments. I also added geohashes to remaining data. I saved them as CSVs.

#### Geohash based scatterplots

In this notebook the first step was to import os, pandas, numpy, statsmodels, seaborn, and matplotlib. Also to set my working directory and load my data.

The second step was to prepare dataframes that contain one row per precision 5 geohash about the number of transit stops (all transit or just all rail) and the number of establishments (all establishments, just bars, or just restaurants) per geohash.

The third step was to prepare scatterplots with the x axis being number of transit nearby transit stops and y axis being number of nearby bars and or restaurants and the points being individual geohashes. I added regression lines with p values.

I identified three geohashes in downtown montreal with high numbers of bars, restaurants, and transit stops. These geohashes were f25dv, f25dy, f25ej.

The next step was that I split these three geohashes into 96 more precise geohashes and created data frames with the number of transit stations and bars/restaurants in each of the smaller geohashes.

Then I prepared further scatterplots for these 96 geohashes. I saved them all.

## Results

## Challenges

## Future Goals
