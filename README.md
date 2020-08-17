# Citibike_CaseStudy_Analysis
*Analysis of **NYC's Citibike** Data for Descriptive Statistics and Predictive Modelling*

**Author: Danish Anis**

**Contact: danishanis10@hotmail.com**

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/biking-in-nyc.png)

## Aim 

Analysis of New York's Citi Bike Data to visually represent what affect different independent variables like Geographical Coordinates, User Types, Gender etc. have on the Predicting **Trip Duration** given Start & End locations. 

**Why?** The client, the Mayor of New York City needs a better understanding of Citi Bike ridership. He wants an Operating Report with *Visual Analysis* for the Year 2017 on his desk by the end of the week. He would like Citi Bike to add a new feature to their Kiosks: "Enter a destination and we'll tell you how long the trip will take". 

## Technologies/Libraries Used

Program written in Google Colab

 - *Python 3*
 - *Jupyter*
 - *Pandas*
 - *Numpy*
 - *Seaborn*
 - *Matplotlib*
 - *Scikit-Learn*
 - *Scipy*
 
## Table of Contents:

 - [Introduction to Dataset](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#introduction-to-dataset)
 - [Summary Statistics Questions](https://github.com/danishanis/Citibike_CaseStudy_Project#phase-1---descriptive-statistics-on-initial-data)
   - [Top 5 Stations with most Starts](https://github.com/danishanis/Citibike_CaseStudy_Project#top-5-stations-with-most-starts)
     - [EDA for Trip Durations per Station](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#eda-for-trip-durations-per-station)
   - [Trip Duration by User Type](https://github.com/danishanis/Citibike_CaseStudy_Project#trip-duration-by-user-type)
     - [EDA for Large Trip Durations](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#eda-for-large-trip-durations--)
     - [EDA for Circular Trips Travelled](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#eda-for-circular-trips-travelled--)
     - [EDA for '0.00' Coordinates](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#eda-for-000-coordinates--)
     - [EDA for User Type](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#eda-for-user-type--)
   - [Most Popular Trips](https://github.com/danishanis/Citibike_CaseStudy_Project#most-popular-trips)
   - [Rider Performance by Gender & Age](https://github.com/danishanis/Citibike_CaseStudy_Project#rider-performance-by-gender--age)
     - [EDA for Missing Birth Years](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#eda-for-birth-year)
   - [Busiest Bike in NYC in January 2017](https://github.com/danishanis/Citibike_CaseStudy_Project#busiest-bikes-in-nyc-in-january-2017)
 - [Data Pre-processing for Modelling](https://github.com/danishanis/Citibike_CaseStudy_Project#phase-2---data-preprocessing-for-modelling)
   - [Visualizing Target Variable - Trip Duration](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#visualizing-target-variable---trip-duration)
   - [Correlation between Features & Target Variable](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#correlation-between-features--target)
   - [Feature Engineering](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#feature-engineering)
     - [Engineering 'Weekday & Weekend' Information from Dates](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#engineering-weekday--weekend-information-from-dates)
     - [Avg. Speed & Duration for specific Rider & Route Type](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/README.md#avg-speed--duration-for-specific-rider--route-type--)
   - [Log Transformation, Scaling & Encoding](https://github.com/danishanis/Citibike_CaseStudy_Project#data-prep---log-transformation-scaling--encoding)
  - [Predictive Modelling](https://github.com/danishanis/Citibike_CaseStudy_Project#phase-3---predictive-modelling-comparison-by-distribution-plots)
    - [Baseline Model - Linear Regression](https://github.com/danishanis/Citibike_CaseStudy_Project#baseline-model---linear-regression)
    - [Random Forest & Random Forest with Important Features only](https://github.com/danishanis/Citibike_CaseStudy_Project#random-forest)
    - [XG Boost](https://github.com/danishanis/Citibike_CaseStudy_Project#xgboost)
    - [Polynomial Regression](https://github.com/danishanis/Citibike_CaseStudy_Project#polynomial-regression)
    - [Ridge Regressor]()
    - [Best Model - Gradient Boosting](https://github.com/danishanis/Citibike_CaseStudy_Project#gradient-boosting)

## Details:

### Introduction to Dataset:

The data can be obtained from the [link](https://s3.amazonaws.com/tripdata/index.html). As per the instrucitons, analysis & subsequent modelling was to be performed on only **January 2017 data**. The description of variables is provided as follows -

    Trip Duration (seconds)
    Start Time and Date
    Stop Time and Date
    Start Station Name
    End Station Name
    Station ID
    Station Lat/Long
    Bike ID
    User Type (Customer = 24-hour pass or 3-day pass user; Subscriber = Annual Member)
    Gender (Zero=unknown; 1=male; 2=female)
    Year of Birth

### Phase 1 - Descriptive Statistics & EDA on Initial Data
#### Top 5 Stations with most starts:

##### *EDA for Trip Durations per Station* 

There are some trips with total duration of less than **90 seconds (1.5 minutes)**. In ideal world, we must not factor such trips as it is very likely that the bikes may have been broken and as soon as the use found out, they docked it and picked up another bike within a minute or two. This Hypothesis was tested to see if there are considerable number of such trips that can be included. 

It was seen that *3000+* such cases existed and they cannot be ignored. **Moreover, as we suspected, many of these trips have the same start and end stations.** We can thus remove those specific trips that have the same station start & end names

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/top5_stns.png)

#### Trip Duration by User Type:

##### *EDA for Large Trip Durations* - 
We notice that the maximum value for trip duration is abnormally large. Infact, there are several values which are much larger than the mean trip duration in the dataset. This shouldn't be the case as we will not be able to deduce anything from this kind of distribution plot.

Realistically speaking, even if a rider decides to rent the bike overnight, the total trip duration shouldn't exceed 48 hours at the most. This is conservative as the mean trip duration lies somewhere around 2 hours. Therefore, we can decide to remove all those trip durations that exceed around 24-27 hrs. Also, we can try to play around with this threshold and see what percentage of trip durations in the dataset belong to those that exceed different time limits. Rows that have trip duration of more than **9999 seconds (2.7 hrs)** constitute about **0.08%** of the entire dataset. There is no harm in dropping these rows if by doing so, we can visualize our data well without compromising the effectivity of our predictive model.

##### *EDA for Circular Trips Travelled* -

We notice that of the different distances travelled, we have a vast majority of those as **zero meters**, meaning the Start & the End Station for those journeys were the same. These **'circular trips'** are very much possible in real life scenario! These could include cases where bikes were hired for a prolonged journey and returned at the same spot. But previusly, our function defaults those trips to have travelled 0 distance if only the trip duration too was minimal.

But in these cases, distance and speed both will have 0 values and the trip duration will certainly be more than 90 seconds. This will be an issue when during feature pre-processing, we subject these columns through log transformation or scaling.

It is important to decide what should be done with these values as they are significant enough to make a difference to our target variable 'Time Duration'. Can we cannot ignore them given that their distribution is not uniform (mean & 50% are not similar)? Since out goal is to be able to predict how much time it will take for a rider to get to different places, realistically speaking, we'd like to help those who want to plan their journey between **two distinct points.**

Besides, this data is irrelevant for predictive modelling in this case. Someone on a circular trip can obviously be assumed to know the trip duration and doesn't need our model to tell them that. Hence, we can safely decide to **drop these values**.

##### *EDA for '0.00' Coordinates - 
We have some Start Coordinates as (0.00,0.00). These are trips which were taken away for repair or for other purposes. These should be dropped.

##### *EDA for User Type* -
Missing values formed nearly 0.44% of the User Type variable. Hence it was deemed fit to remove those rows.

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_dur_usertype.png)

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_dur_pie.png.png)

#### Most Popular Trips:

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/popular_trips.png)

#### Rider Performance by Gender & Age:

##### *EDA for Missing Birth Years*
Nearly 4% of the total Birth Year values in the dataset are Null. We can decide to either remove these rows or impute them. Besides **NaN**, the dataset contains some unrealistic age values, including some even from the **19th Century**! These can safely be removed. The box plot below shows the noise in this variable accurately.

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/year_box.png)

Realistically speaking, we would like to include only people aged 65 and below. A quick look at the number of trips in the dataset by people 70 and above shows that the data includes a lot of noise. We cannot expect **2700** trips to be made in a month by people in that age. Hence, those rows were dropped in the beginning of the case study.

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/rider_perf1.png)

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/rider_perf2.png.png)

#### Busiest Bikes in NYC in January 2017:

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/busiest_bikes.png)

### Phase 2 - Data Preprocessing for Modelling
#### Visualizing Target Variable - Trip Duration:

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_duration_viz.png)

#### Correlation between Features & Target:

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_dur_user_corr.png)

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_dur_time.png)

#### Feature Engineering

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/feat_engg.png)

#### *Engineering 'Weekday & Weekend' Information from Dates*
The Start and Stop times can now serve only one purpose in modelling - categorizing whether a trip was made during a 'Rush Hour' or not. We are mostly looking to determine if the trip was started during a rush hour or not as that can impact the trip duration.

**1 = Weekday** and **0 = Weekend**

#### *Avg. Speed & Duration for specific Rider & Route Type* - 


Some trips are up hill, others are down hill. Some routes, such as one through times square involve heavy traffic. Tourists (Customers), will usually ride more slowly with frequent stops than a Subscriber.

Here, we'll see how these factors can correlate with the Trip Duration. We see that average trip durations between rush hours & otherwise are quiet equally divided. We can't say if adding this column will be very effective for the predictive model, but we can certainly drop the start and stop times now

#### Data Prep - Log Transformation, Scaling & Encoding:
For random distribution before modelling

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/data_distribution.png)

### Phase 3 - Predictive Modelling (Comparison by Distribution Plots):
#### Baseline Model - Linear Regression:

Accuracy: *87%*

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/lr_act_vs_pred.png)

#### XGBoost

Accuracy: 47%

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/xgb_dist.png)

#### Polynomial Regression

Accuracy: *92%*

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/polreg_dist.png)

#### Random Forest

Accuracy: 93%

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/rf_dist.png)

#### Gradient Boosting

Accuracy: *99%*

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/GBoost_dist.png)
