# Bike Sharing Assignment on Linear Regression

> This assignment is a programming assignment wherein you have to build a multiple linear regression model for the prediction of demand for shared bikes. You will need to submit a Jupyter notebook for the same. 


## Table of Contents
* [Problem Statement]
* [Business Goal]
* [Data Preparation]
* [Model Building]
* [Technologies Used]
* [Conclusion ]
* [Final Recommendation]

## Problem Statement
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.


A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 


In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.


They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

Which variables are significant in predicting the demand for shared bikes.
How well those variables describe the bike demands
Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 


## Business Goal

You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 


## Data Preparation

1. You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
2. You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 


## Model Building

In the dataset provided, you will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. The model should be built taking this 'cnt' as the target variable.


## Technologies & libraries Used
- Python
- pandas
- numpy
- matplotlib
- seaborn
- sklearn
- statsmodels


## Conclusion

1. Comparison between Train and Test datasets:
    
    - Train dataset R^2: 0.836
    - Train dataset Adjusted R^2 0.833
    - Test dataset R^2 : 0.7965
    - Test dataset Adjusted R^2 : 0.7868

2. Understading the final coefficient output: -> round(lr6.params,4)
    
    - const (0.1344): This is the intercept term. It represents the predicted value of the target variable (demand) when all - other features are zero.
    - yr (0.2328): This coefficient shows the effect of the year (possibly coded as 0 or 1) on the demand. A value of 0.2328 - means that for every one-unit increase in the year, the demand increases by 0.2328 units.
    - holiday (-0.1067): This coefficient suggests that holidays tend to decrease the demand by 0.1067 units, holding all other variables constant.
    - temp (0.5471): This indicates that an increase in temperature by one unit increases the demand by 0.5471 units, suggesting - a positive relationship between temperature and bike demand.
    - windspeed (-0.1531): A negative coefficient, meaning that higher wind speed decreases the demand by 0.1531 units.
    - sep (0.0994): This represents the effect of September (likely a dummy variable for the month). It indicates a slight - increase in demand bu 0.0994 units in September.
    - sun (-0.0498): A small negative effect, suggesting that more sunshine slightly reduces the demand by 0.0498 units.
    - Light_snowrain (-0.2883): This suggests that light snow or rain decreases the demand by 0.2883 units.
    - Misty (-0.0806): Misty weather reduces the demand by 0.0806 units.
    - summer (0.0878): This coefficient suggests that the summer season increases demand by 0.0878 units.
    - winter (0.1311): Winter increases demand by 0.1311 units, though slightly more than summer

3. Equation:
    
    cnt = 0.1344 + 0.2328 * yr - 0.1067 * holiday + 0.5471 * temp - 0.1531 * windspeed + 0.0994 * sep - 0.0498 * sun - 0.2883 Light_snowrain - 0.0806 * Misty + 0.0878 * summer + 0.1311 * winter

## Final Recommendation

- temp: Temperature has the highest positive coefficient, indicating that higher temperatures strongly correlate with - increased bike demand.
- yr: The year variable suggests a substantial positive trend in bike demand over time, with 2019 seeing higher usage than 2018.
- Light_snowrain: This feature has the largest negative impact. Inclement weather (light snow or rain) significantly reduces bike demand, as adverse conditions discourage users.
