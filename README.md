# Citibike_CaseStudy_Analysis
Analysis of **NYC's Citibike** Data for Descriptive Statistics and Predictive Modelling

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

## Details:

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
