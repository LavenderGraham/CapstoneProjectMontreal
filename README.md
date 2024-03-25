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

Then I prepared further scatterplots for these 96 geohashes. I saved them all as jpgs and pngs.

#### EDA Non Scatterplots

I loaded pandas, os, matplotlib, numpy, seaborn, and statsmodels packages and set my working directory and loaded my dataframes.

I defined functions that I used to calculate distance between latitude longitude pairs.

I edited my dataframes to calculate the number of nearby total stations and nearby rail stations for each establishment.

I created a series of bar graphs showing the number of nearby transit stations nearby the establishments and bars and restaurants that had the most nearby stations.

I created a series of histograms showing the distributions of how many transit stations are nearby establishments and bars and restaurants.

I created a series of box plots showing how the price categories and rating categories was associated with the number of nearby transit stations or rail stations.

I saved my results as jpgs and pngs.

#### Tableau

I created map diagrams on Tableau to show where the bars, restaurants, subway stations, light rail stations, and citybike stations are distributed throughout Montreal.

#### Regression Analysis

I loaded pandas, os, matplotlib, numpy, seaborn, and statsmodels packages and set my working directory and loaded my dataframes.

I defined functions that I used to calculate distance between latitude longitude pairs.

I edited my dataframes to calculate the number of nearby total stations and nearby rail stations for each establishment. I also added columns for whether or not an establishment was "outstanding" (Google rating 4.5 or above) or "exorbitant in price" (Price rating of 4.0).

I then did a series of multiveriable regresssion analyses to see how nearby citybikes stations, light rail stations, and subway stations predicted the ratings of establishments and the prices of establishments.

I also did a series of logistic regression analyses to see how the number of nearby transit stations predicted if an establishment was outstanding or exorbitant in price.

I saved my results as CSVs.

#### All Graphics Produced During Data Analysis Of Businesses In Montreal

I made a powerpoint containing all the graphs, images, and regression analysis results produced during this project.

## Results

When analyzing Montreal using Geohashes at precision 5, the number of nearby total transit stations and number of nearby total rail stations were consistently predicitive of the number of nearby bars and or restaurants.
These associations were very strong and had high degrees of statistical significance. For example the R-squared value for the Scatterplot of Transit vs Establishment Counts by Geohash was 0.803 and the p value was 2.96 * 10^-19.

When using Geohashes at precision 6, these associations were still consistent but weaker. For example, for Scatterplot of Transit vs Establishment Counts by Geohash Precision 6 the R-squared value was 0.305 and the p value was 3.54 * 10^-08.

Establishments with the most nearby transit stations included downtown places such as Saiko Bistrot Izakaya, Monsieur cafe & vins, The Old Dublin Pub & Restaurant, and Piranha Bar.

Histograms showed a consistently skewed right pattern with most establishments haivng few nearby transit stations and relatively fewer establishments having over 40.

Most of the multivariable logistic regression analyses and logistic regression analyses found that the number of nearby transit stations or nearby rail stations had a predictive value of the quality or price of an establishment that was so weak as to be not worth considering.
Some of these analyses found results that were technically statistically significant, but still had R-squared values close to zero. The only regression analysis that I consider to have noteworthy results was the one asking if the number of nearby rail stations predicts if
a restaurant is exorbitant in price. It found a positive R-squared value of 0.1812. I think this is sensible because very expensive restaurants are more likely to be put downtown where there are many rail stations, such as Restaurant Pangea which is located between city hall and 
the Notre Dame Basilica Cathedral.

## Challenges

The most significant challenge of this project was dealing with Google Places API call. This unfortunately restricted me to only calling for areas of Montreal near transit stations and in a grid latitude-longitude pairs surrounding downtown.
Running though my list of coordinates was very time consuming and in similar assignments I should find a way to automate these sorts of procedures.

## Future Goals

Future goals would include:

1. Find ways to automate repeated loops of Google Places API calls over lists of coordinates to query Google Places API more efficiently.
2. Scale up my investigation of bars and restuarants so that they cover all of Montreal.
3. Conduct similar analyses of other North American cities including Ottawa, Toronto, Hamilton, Quebec City, Boston, and New York.
4. Analyze if some genres of restaurants have more transit stations than other genres. For example, examine if Indian Restaurants have more nearby transit stations than pizza restaurants.
