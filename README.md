# Citibike_CaseStudy_Analysis
*Analysis of **NYC's Citibike** Data for Descriptive Statistics and Predictive Modelling*

**Author: Danish Anis**

**Contact: danishanis10@hotmail.com**

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/biking-in-nyc.png)

## Aim 

Analysis of New York's Citi Bike Data to visually represent what affect different independent variables like Geographical Coordinates, User Types, Gender etc. have on the Predicting **Trip Duration** given Start & End locations. 

**Why?**: Our client, the Mayor of New York City needs a better understanding of Citi Bike ridership. He wants an Operating Report with *Visual Analysis* for the Year 2017 on his desk by the end of the week.

## Technologies/Libraries Used

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
   - [Trip Duration by User Type](https://github.com/danishanis/Citibike_CaseStudy_Project#trip-duration-by-user-type)
   - [Most Popular Trips](https://github.com/danishanis/Citibike_CaseStudy_Project#most-popular-trips)
   - [Rider Performance by Gender & Age](https://github.com/danishanis/Citibike_CaseStudy_Project#rider-performance-by-gender--age)
   - [Busiest Bike in NYC in January 2017](https://github.com/danishanis/Citibike_CaseStudy_Project#busiest-bikes-in-nyc-in-january-2017)
 - [Data Pre-processing for Modelling](https://github.com/danishanis/Citibike_CaseStudy_Project#phase-2---data-preprocessing-for-modelling)

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

### Phase 1 - Descriptive Statistics on Initial Data
#### Top 5 Stations with most starts:

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/top5_stns.png)

#### Trip Duration by User Type:

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_dur_usertype.png)

![alt text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/trip_dur_pie.png.png)

#### Most Popular Trips:

![alt_text](https://github.com/danishanis/Citibike_CaseStudy_Project/blob/master/images/popular_trips.png)

#### Rider Performance by Gender & Age:

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

#### Data Prep - Log Transformation, Scaling & Encoding:

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
