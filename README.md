# Food Delivery Data Analytics Project

## Overview
This project focuses on analyzing a food delivery dataset to gain insights into key factors affecting delivery times and delivery person ratings. The dataset includes details such as restaurant locations, delivery locations, and rider information (mode of transport, rating, age, etc.). The primary analysis focuses on data from Indore city, further segmented to include only deliveries within a 10 km radius of the city's center, due to resource and time constraints.

The analysis includes hypothesis testing, feature engineering, and regression modeling to derive actionable insights and evaluate the performance of predictive models.

---

## Data Preparation
1. **Data Segmentation**:
   - The dataset was filtered to include only entries from Indore city.
   - Further segmentation was applied to restrict the data to deliveries within a **10 km radius** from the city's center.

2. **Feature Engineering**:
   - Calculated the distance between restaurant and delivery locations using the `networkx` and `osmnx` libraries.
   - Applied **one-hot encoding** to the `Type_of_vehicle` column to represent the modes of transport (bicycle, scooter, motorcycle, etc.) as binary variables.

---

## Hypothesis Testing
We conducted hypothesis testing to explore relationships between various features:

1. **Delivery Person's Age vs. Delivery Time**:
   - Null Hypothesis (H₀): Age does not significantly affect delivery time.
   - Alternate Hypothesis (H₁): Age significantly affects delivery time.

2. **Type of Vehicle vs. Delivery Time**:
   - Null Hypothesis (H₀): Vehicle type does not significantly affect delivery time.
   - Alternate Hypothesis (H₁): Vehicle type significantly affects delivery time.

3. **Delivery Time vs. Rating**:
   - Null Hypothesis (H₀): Delivery time does not significantly affect delivery ratings.
   - Alternate Hypothesis (H₁): Delivery time significantly affects delivery ratings.

Results from these tests were used to validate relationships and shape further modeling.

---

## Regression Analysis

### Model 1: Predicting Delivery Time
- **Target Variable**: `Time_taken(min)`
- **Features**:
  - Delivery Person's Age
  - Type of Vehicle (bicycle, scooter, motorcycle, etc.)
  - Driving Distance
- **Methodology**: Linear Regression with Train-Test-Split
- **Metrics**: Root Mean Square Error (RMSE)
  - Residuals were plotted to examine their distribution (roughly normal) and to check for patterns against predicted values (none observed, indicating no systemic bias).
- **Insights**: Delivery time is significantly affected by vehicle type and driving distance.

### Model 2: Predicting Delivery Person's Ratings
- **Target Variable**: `Delivery_person_Ratings`
- **Features**:
  - Delivery Person's Age
  - Time Taken (minutes)
  - Driving Distance
  - Type of Vehicle (bicycle, scooter, motorcycle, etc.)
- **Methodology**: Linear Regression with Train-Test-Split
- **Metrics**: Root Mean Square Error (RMSE)
  - RMSE = **0.2305**, indicating high accuracy.
- **Insights**:
  - Longer delivery times negatively impact ratings.
  - Vehicle type also influences ratings, with scooters and electric scooters having a positive effect, while bicycles have a negative effect.

---

## Libraries and Tools Used
- **Data Analysis**: `pandas`, `numpy`
- **Distance Calculation**: `networkx`, `osmnx`
- **Machine Learning**: `scikit-learn`
- **Data Visualization**: `matplotlib`, `seaborn`
- **Statistical Analysis**: `scipy`, `statsmodels`

---

## Key Takeaways
1. **Delivery Time Analysis**:
   - Vehicle type and driving distance significantly affect delivery time.
   - The linear regression model demonstrated good performance, with residuals distributed normally and minimal bias observed.

2. **Ratings Analysis**:
   - Delivery times and vehicle types are significant predictors of customer ratings.
   - A low RMSE (0.2305) in the ratings prediction model suggests high accuracy.

3. **Actionable Insights**:
   - **Vehicle Optimization**: Promote faster vehicles (scooters and electric scooters) for better delivery performance and customer ratings.
   - **Focus on Efficiency**: Minimize delivery times to improve both performance metrics.
