# Coursera_Capstone

Applied Data Science Capstone Project 2021

## Problem Statement :
In Chennai, the population of traditional (Indian or Tamil-ian) food seekers and western and oriental cuisine lovers have been fairly even. It would prove beneficial to find out the population distribution in both the cases and see if this applies as a good feature to recommend a new user to an Indian or Western restaurant.

## Data Description :

Zomato Restaurant Rating from Kaggle:
[Chennai Restaurants Rating from Zomato](https://www.kaggle.com/phiitm/chennai-zomato-restaurants-data)

Chennai Segments geospatial info :
There are plenty of prominant areas and a lot of data sources that I found seem to have too much info. So, I settled with this csv I found on data.gov.in with the Segment names and latitudes and longitudes.

Further more, The Foursquare data will provide the reviews and tags for the hotels and restaurants in Chennai, which can be used to

1 - Label theses restaurants into Indian or Western etc. This requires a more in-depth analysis of the FourSquare json. 

2 - Build a base K-Means ( or any other Clustering algorithm) that would recommend a similar restaurant option to a new user.

3 - Add the feature created in step 1 to a new model and compare the accuracies.

## Methodology

### Formatting Result JSON from Foursquare
The structure of the JSON consisted of response, groups, venue name, venue location and venue category. I used json_normalize() from pandas.io.json library to unpack these values and store it in the chennai_venues dataframe

### Exploring Ratings from Zomato
The .csv from the Kaggle site with Chennai's restaurant rating contained more information than needed for this clustering project, which I ended up dropping. About 489 restaurant information matched the Chennai Segments file that I started with, so I used only those for further analysis.

### Pre-processing for Clustering Algorithm
I used get_dummies() from pandas to encode the categories in the chennai_venues dataframe. This was then grouped into the respective Segments which ended up with 422 rows for Clustering.

### Clustering
I tested n_clusters with 3,4 and 5. And 3 gave a clearer picture of the Clustering happening with the venues in Chennai. I then used a folium map to create the final map of Chennai with 3 clusters.

![alt text](http://url/to/img.png)

## Conclusion
