# Regression_Capstone_Project

Project Summary :
The "Bike Sharing Demand Prediction" project aims to develop a predictive model that can accurately forecast the demand for bike-sharing services in a given location and time frame. Bike-sharing systems have become increasingly popular in urban areas, offering an eco-friendly and convenient mode of transportation. Accurate demand prediction is crucial for optimizing bike allocation, ensuring user satisfaction, and managing operational costs effectively.

Key Objectives:

1) Data Collection and Preprocessing: Gather historical data on bike rentals, including variables such as date, time, weather conditions, and user information. Clean, preprocess, and transform the data to make it suitable for modeling.

2) Exploratory Data Analysis (EDA): Conduct EDA to gain insights into the dataset, identifying trends, patterns, and correlations. Visualize the data to better understand the factors influencing bike rental demand.
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/941a5c4d-0d60-4568-9f9d-77b712432003)
Observation:
* As we can see summer has the highest number of bikes rented, 37%. This could be because of the vacation mood created in summer and also the increase in the number of tourists. Winter however is the season where the least number of bikes are rented, 8%.

![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/e646b65d-679a-473f-b799-9dcc1568de59)
Observation:
* Distribution of Rented Bike Count is positively skewed and has many outliers. We will treat it later.

2.1) Univariate, Bi-variate and Multi-variate analysis of each column:

Column: 'hour'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/f719b661-c20e-44b4-a150-9d9894731acf)
Observation:
* Every hour has an equal number of counts in the dataset.
* Demand for rented bike count is higher at 8 AM and 6 PM indicating a high demand during business hours.
* Rented Bike Count follows 2 patterns one for holiday and another for no holiday.
* Holiday: The first pattern is where there is a peak in the rentals at around 8 am and another at around 6 pm. These correspond to local bikers who typically go to work on a working day, Monday to Friday.
* Non-Working Day: Second pattern where there are more or less uniform rentals across the day with a peak at around noon time. These correspond to probable tourists who typically are casual users who rent/drop off bikes uniformly during the day and tour the city on nonworking days which typically are Saturday and Sunday

Column: 'Humidity(%)
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/55e711db-8fd2-4e34-948e-00c7887e66cd)
Observation:
* We can see from the plots above that the average number of bikes rented goes up and down sharply with the peak at around 50. For the number of rented bikes in demand, the most preferred humid environment is 20-90.

Column: 'Wind speed (m/s)'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/c15d86ec-477e-4477-926b-8906b6bb6a13)
Observation:
* We can see from the distribution plot that wind speed is slightly positively skewed.
* Scatter Plot tells us about the distribution of the wind speed and rented bike count, and how the values of the two variables are related to each other.
* Line plot tells us that people prefer moderate wind but there is a spike at wind speed 7.

Column: 'Visibility (10m)'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/1250c823-dbe3-4434-926b-8434b44a7469)
Observation:
* Visibility is highly skewed to the left side.
* We can see from these plots above that as visibility rises, so does rented_bike_count.

Column: 'Dew point temperature(°C)'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/3079983c-900d-4fc4-98a6-c08ecd7f7f5a)
Observation:
* We can see from the above plots that dew point temperature is negatively skewed with a clear positive relationship with rented bike count.
* The average number of bikes rented with dew point temperature increases steadily, with a slight decrease at the highest dew point temperature.
* Line plot of dew point temperature is very similar to temperature pattern.

Column: 'Solar Radiation (MJ/m2)'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/ddf42499-738e-4816-8d8e-fce1fcbb8710)
Observation:
* We can see from the distribution plot that solar radiation is highly skewed to positive.
* The average number of bikes rented goes up with solar radiation.
* Additionally, this column is directly related to the temperature column.

Column: 'Rainfall'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/9b93a51e-fd39-48a2-aa74-b31ebbe5e6e3)
Observation:
* The distribution of rainfall is highly skewed to the positive side.
* People prefer almost no or very little rainfall.

Column: 'Snowfall'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/6085731c-2b99-461c-9967-6a6c74b2f03e)
Observation:
* The distribution of snowfall is highly skewed to the positive side.
* People prefer almost no or very little snowfall.

Column: 'Seasons'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/6cb59156-0653-41d2-af1b-19844d5e0fac)
Observation:
* Dataset has 4 seasons and every season has more than 2000 counts.
* The most preferred season for the rented_bike_count is summer and the least preferred is winter which means that people prefer to rent bikes in warm temperatures.
* In every season on a no holiday rented_bike_count has more count than on a holiday.

Column: 'holiday'
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/54dfc774-8fc0-44f7-a732-d6fe4b9e6294)
Observation:
* Dataset has more records of No holiday than a holiday which is obvious as most of the days are working days.
* When there are no holidays, demand for bike sharing is higher than when there are holidays, indicating that business-related bike rentals are preferred.

2.2) Outlier Analysis:
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/4da8880d-596d-43b1-b861-8aff0c9b9239)
Observation:
* Here we can see that the columns that contain outliers are Rainfall, Snowfall, Windspeed, and Solar Radiation

2.3) Checking correlation for feature removal:
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/c018f6c8-0108-47a5-893b-2b3b621a1495)
Observation:
* The Dew point temperature column is highly correlated to the Temperature column and therefore we can remove it and it most likely won't affect our model building much, so we will drop the dew point temperature column.
* I will also remove the date column because I don't think it adds any value.

2.4) Printing the regression plot for all the numerical features:
![image](https://github.com/Nik852001/Regression_Capstone_Project/assets/93510310/34f504e3-2786-45aa-86a0-85f42c0fd551)


4) Feature Engineering: Create relevant features, such as time of day, day of the week, and weather indicators, to improve the model's accuracy. Handle categorical variables through encoding techniques. For feature Engineering I used One-hot encoding.

5) Model Development: Implement various machine learning algorithms, such as linear regression, decision trees, random forests, and gradient boosting, to build predictive models. Evaluate and compare the performance of these models using appropriate metrics, like Mean Absolute Error (MAE) or Root Mean Square Error (RMSE).

6) Model Validation and Testing: Split the dataset into training and testing sets to assess the model's generalization performance. Validate the model's predictions against real-world demand data

##<b>Conclusion:</b>
1. EDA insights:
  * Most number of bikes are rented in the Summer season and the lowest in the winter season.
  * Over 96% of the bikes are rented on days that are considered as No Holiday.
  * Most number of bikes are rented when there is no snowfall or rainfall.
  * The majority of the bikes are rented for a humidity percentage range of 30 to 70.
  * The highest number of bike rentals have been done in the 18th hour, i.e. 6 pm, and the lowest in the 4th hour, i.e. 4 am.
  * Most of the bike rentals have been made when there is high visibility.

2. Results from ML models:
  * Random Forest Regression is the best-performing model with a testing r2 score of 0.6799 and a training r2 score of 0.96.
  * Lasso Regression(L1 regularization) is the worst performing model with an r2 score of 0.4377.
  * Actual vs. Prediction visualization is done for all 4 models.
  * All 4 models have been explained with the help of the SHAP library.
  * Temperature and Hour are the two most important factors according to all the models.

3. Challenges faced:
  * Removing Outliers.
  * Encoding the categorical columns.
  * Removing Multicollinearity from the dataset.
  * Choosing Model explainability technique.
