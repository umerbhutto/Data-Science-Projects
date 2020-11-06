# Kaggle-Bike-Sharing-Demand
Kaggle Competition on Bike Sharing Demand

Problem: Washington DC has recently implemented a “go-green” initiative which encourages residents and tourists to travel using bicycles. A local bike rental company, has implemented a new system for bike sharing to improve demand and ease bike rentals for customers. As consultants we have been selected to help Bicycle Inc. better understand their customer base and bike rental demand for each hour. 

Executive Summary

Washington DC has recently implemented a “go-green” initiative which encourages residents and tourists to travel using bicycles. Bicycle Inc., a local bike rental company, has implemented a new system for bike sharing to improve demand and ease bike rentals for customers. As consultants we have been selected to help Bicycle Inc. better understand their customer base and bike rental demand for each hour. 

The data provided by Bicycle Inc. has been collected by their automated sales system. The variables included in the dataset help understand the quality of the day, e.g. weather, humidity, temperature etc. and the type of day, e.g. is it a working day? Is it a holiday? etc. The data accumulated by the system complies with ASOP 23 as personal information about the customers was not gathered.

We cleaned the data to better interpret the affect of the predictor variables on the dependent variable. We created 3 new columns: year of rental, quarter of the year, time of day. This has helped us better understand the peak times of bike rentals. After reviewing missing values in the registered and non-registered user rentals columns, we concluded that the variables needed to be removed. After visualizing the variables, we also noticed that these two variables had very limited influence on the number of bike rentals

We developed a generalized linear model (GLM) to predict bike rentals. Based on the predictor variables and the nature of bike rentals, we assumed that the distribution of bike rentals could be explained by the Poisson distribution The GLM is a flexible model that predicts the number of bike rentals using the predictor variables. It allows for controlled removal of variables that lack predictive power and it indicates the direction of the influence of each variable that is retained. However, it must be noted, that the GLM does not handle non-linear relationships well. 

After investigating several forms of the GLM and variable choices, a model with the following variables provided the most accurate predictions on a random train-test partition:

•	Season – 

•	Holiday – 

•	Workingday – 

•	Weather – 

•	Temperature – 

•	Atemp – 

•	Humidity – 

•	Windspeed – 

•	Time of day – 

•	Quarter – 

•	Year – 

The score of the model is 0.8701, an improvement over the previous model with a score of 0.83783

The results show that Washington DC’s “go-green” initiative has shown some promising results as customers have been renting a bike to work. As winter shows low demand for bike rentals, Bicycle Inc. can reduce inventory and staff during the season. During all other seasons, the peak demand for bike rentals is between morning to early night. Bicycle Inc. should ensure that there is adequate inventory of bikes and staff to facilitate customers with bike rentals.

Given that the model’s predictive power is high with relatively few variables, we recommend additional discussion and testing and further validate the model’s potential use. Even though the main use of the model was to predict bike rentals, the model can also be used to judge the success of Washington DC’s go-green initiative.
 
