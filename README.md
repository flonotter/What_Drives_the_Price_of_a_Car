# What_Drives_the_Price_of_a_Car

# Used Car Price Analysis - CRISP-DM Framework

This project applies the CRISP-DM (Cross-Industry Standard Process for Data Mining) framework to analyze a dataset of used cars. The goal is to understand the factors that influence the pricing of used cars and provide actionable insights for a used car dealership.

## 1. Business Understanding

### Objective:
- Understand what factors influence the pricing of used cars.
- Provide recommendations to a used car dealership on what consumers value in used cars.

### Questions:
- What car features (like make, model, year, mileage, condition, etc.) most strongly influence their price?
- Are there trends or patterns in how these features affect car prices?

## 2. Data Understanding

### Dataset Overview:
- The dataset contains information on 426,000 used cars, a subset from a larger Kaggle dataset.
- Columns include `region`, `price`, `year`, `manufacturer`, `model`, `condition`, `cylinders`, `fuel`, `odometer`, `title_status`, `transmission`, `VIN`, `drive`, `size`, `type`, `paint_color`, and `state`.

### Initial Observations:
- Presence of missing values in several columns.
- Need to address data quality issues like outliers and missing data.

## 3. Data Preparation

### Outlier Handling:
- Outliers in the `price` and `odometer` columns were removed using statistical methods like IQR (Interquartile Range).

### Handling Missing Values:
- Dropped columns with significant missing data (`condition`, `cylinders`, `drive`, `size`, `type`, `paint_color`, `VIN`).
- Dropped rows with missing values in critical columns (`manufacturer`, `model`, `fuel`, `odometer`, `title_status`).

### Final Dataset:
- Refined to 381,285 entries with the following columns: `region`, `price`, `year`, `manufacturer`, `model`, `fuel`, `odometer`, `title_status`, `transmission`, `state`.

### Conclusion:
The dataset is prepared for further analysis to identify factors affecting used car prices. This analysis will help the used car dealership understand consumer preferences and pricing strategies.

### Modelling:
In this phase, we would use the data to build predictive models that can estimate the price of a used car based on its features. Techniques like linear regression, random forest, or gradient boosting machines could be employed. The choice of algorithm depends on the nature of the data (e.g., linearity, number of features, amount of data). We would preprocess the data, handling missing values, encoding categorical variables, and normalizing numerical features.

### Evaluation:
Here, we assess the performance of our models. Metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score are commonly used for regression problems. We would use a portion of the dataset (not used in training) to test the model. We also perform validation techniques like cross-validation to ensure that our model generalizes well to new data. Additionally, we would analyze the feature importance to understand what factors most significantly impact the car's price.

### Deployment:
In the final phase, the model would be deployed into a production environment. This could be integrated into a system used by the dealership to estimate the price of used cars. The deployment could be done via a web application or an API, allowing easy access for the dealership's employees. Maintenance and monitoring are crucial in this phase to ensure the model remains accurate over time. We might also consider regularly updating the model with new data.

### Restults:

A basic statistical summary of the numerical columns provides the following insights:

The price column has a wide range, with values ranging from 0 to over 3.7 billion, which suggests the presence of outliers or erroneous entries.
The year column ranges from 1900 to 2022, indicating a wide variety of vehicle ages.
The odometer readings vary significantly, with values ranging from 0 to 10 million, which also suggests some outliers or errors.
Given this information, the next step is to analyze how various features like year, manufacturer, model, condition, odometer, etc., influence the vehicle prices. To do this effectively, considering the presence of potential outliers in the price and odometer columns, we should first address these outliers to prevent them from skewing the analysis. Let's proceed with this. ​​

Output image
After removing outliers and analyzing the relationship between the vehicle price and various features, we can draw the following conclusions:

Year of Manufacture: There's a positive correlation between the year of manufacture and the vehicle price. Newer vehicles tend to be priced higher.

Odometer Reading (Mileage): There's an inverse relationship between the odometer reading and the vehicle price. Cars with lower mileage generally have higher prices.

Fuel Type: The fuel type also influences the price, though the extent of this influence varies. Some fuel types, like diesel and electric, might be associated with higher prices.

Transmission: The type of transmission appears to have an impact on price. For instance, automatic transmission vehicles might be priced differently compared to manual ones.

---
