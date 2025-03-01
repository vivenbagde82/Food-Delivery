# Food Delivery Data Analytics Project

## Overview
This project focuses on analyzing a food delivery dataset to gain insights into delivery times and delivery person ratings. The dataset includes details such as restaurant locations, delivery locations, and rider information (mode of transport, rating, age, etc.). The primary analysis is performed on a subset of the data from Indore city and further filtered to include only data within a 10 km radius of the city's center due to resource and time constraints.

## Data Preparation
1. **Subset Data for Indore City:**
   - Filtered the dataset to include only entries from Indore city.

2. **Filter Data Within 10 km Radius:**
   - Further subsetted the data to include only delivery entries within a 10 km radius from the city's center.

3. **Calculate Distance Between Locations:**
   - Used the `networkx` and `osmnx` libraries to calculate the distance between the restaurant and the delivery location.

## Regression Analysis
### Model 1: Predicting Delivery Time
- **Predictive Variable:** Time Taken (minutes)
- **Methodology:** Linear Regression with Train-Test-Split model
- **Metrics:** Root Mean Square Error (RMSE)
- **Insights:** Analyzed the factors affecting delivery time and their impact.

### Model 2: Predicting Delivery Person's Ratings
- **Predictive Variable:** Delivery Person's Ratings
- **Methodology:** Linear Regression with Train-Test-Split model
- **Metrics:** Root Mean Square Error (RMSE)
- **Insights:** Evaluated the factors influencing delivery person ratings and their significance.

## Libraries and Tools Used
- `pandas`
- `numpy`
- `networkx`
- `osmnx`
- `scikit-learn`
- `matplotlib`

## Project Structure
- `data/`: Directory containing the dataset.
- `notebooks/`: Jupyter notebooks with data analysis and model development.
- `src/`: Source code for data processing and model implementation.
- `README.md`: Project documentation.
