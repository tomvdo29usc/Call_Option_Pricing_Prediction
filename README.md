<!-- ABOUT THE PROJECT -->
## About The Project

Build 2 machine learning models: a regression model to predict Black-Scholes option price and a classification model to predict whether Black-Scholes model overestimates or underestimate the actual option price.

**Tools**: Python (NumPy, Pandas, Scikit-learn, ...), MS Excel, PowerPoint

**Skills**: Exploratory Data Analysis, Applied Statistics, Data Visualization, Machine Learning, Feature Engineering, Project Management, Team Collaboration, Business Communication, 

## **1. Exploratory Data Analysis**

The dataset contains **1,680 records** and **6 columns** as followings: 
<img width="1122" alt="Untitled" src="https://github.com/user-attachments/assets/94eb4b7f-2644-462f-b021-1eb5f93c93df">

### **1.1 Data Quality Summary Table**

<img width="1218" alt="image" src="https://github.com/user-attachments/assets/9214646b-322a-46cf-8ef8-fb7abfbb3bb6">

> [!NOTE]
> There are **missing values** and **outliers** in some fields of the data by looking at % Populated and Min, Max, and Mean. Therefore, we will considering dropping missing values and outliers before modeling step.

### **1.2 Data Cleaning**

We decided to removed any record with missing value and with outliers that fell beyond 3 standard deviation from the mean of any field. Below is the detailed view of detected records with missing values and/or outliers in any field:

<img width="1259" alt="image" src="https://github.com/user-attachments/assets/120fe21f-ebea-4c80-ad10-da0f9a8e2700">

> [!NOTE]
> We only dropped **7 over 1,680 records** from the original data, which won’t be significant. There are 1,673 records after the data cleaning step.

### **1.3 Visualization of each Field Before and After Cleaning the Data**

<img width="1240" alt="image" src="https://github.com/user-attachments/assets/19ceafc5-befb-4001-be63-3900daaa9143">

<img width="1240" alt="image" src="https://github.com/user-attachments/assets/8d9fece7-90e7-4f7a-a25c-bb1102811670">

> [!NOTE]
> The distribution of field **Stock Price (S)** and field **Time to Maturity (t)** become clearer after dropping outliers and missing values.

### **1.4 Feature Engineering**

<img width="1041" alt="image" src="https://github.com/user-attachments/assets/1d1ea637-98ac-4985-ae80-8faf68674572">

# 2. Model Development

Our objective for model exploration was to experiment with different models to select the best model for both regression and classification problems. 

- In the regression problem, we wanted to train a model that can accurately predict the option price.
- In the classification problem, we wanted to build a model that can accurately classify whether using the Black-Scholes algorithm would underestimate or overestimate the actual option price.

We tried different combinations of these tuning hyperparameters to find the best performing models:

<img width="1717" alt="image" src="https://github.com/user-attachments/assets/50711f4a-6932-4e37-9594-6e4e3d16d6c3">

Below is our method to evaluate and select the best model for each problem:

<img width="1548" alt="image" src="https://github.com/user-attachments/assets/a9668a2b-aadf-436c-94e8-2d05be5f79db">


### **2.1 Regression Model Results**

<img width="1247" alt="image" src="https://github.com/user-attachments/assets/5e53faa3-aec1-45b4-ac2a-19d3e5a91262">

> [!NOTE]
> In general, non-linear models outperformed the baseline Linear Regression model significantly. Gradient Boosting Regression model performs the best with the highest and the least variability in testing and cross validation R-squared score. This means that this model is more consistent and robust.

### **2.2 Classification Model Results**

<img width="1247" alt="image" src="https://github.com/user-attachments/assets/57e3f89e-7692-4e18-b14b-23cba52ab83e">

> [!NOTE]
> In general, non-linear models outperformed the baseline Logistic Regression by a little. Logistic Regression shows less sign of overfitting comparing to other models. CatBoost model performs the best with the highest and the least variability in testing and cross validation accuracy score. This means that this model is quite more accurate and robust than other models.

### **2.3 Baseline Models**

### **2.4 Final Model Selection**

<img width="1688" alt="image" src="https://github.com/user-attachments/assets/41f0dcfe-b2eb-4ee4-aae7-5cb0c477b91c">

# 3. Business Understandings

Some business understandings need to be considered when predicting option values:

1. Accurately predicting European call option values is essential to achieve the most optimal financial outcomes, but the interpretation is also important for decision-making. Understanding the relationships between predictor variables and response variables can provide valuable insights to guide investment strategies, risk management, or policy decisions.
2. Machine learning models can outperform the Black-Scholes model in predicting option prices due to their flexibility and adaptability. While the Black-Scholes model, primarily used in European option trading, relies on a fixed set of assumptions and features, machine learning models can capture complex patterns, nonlinear relationships, varying volatility, changing interest rates, and non-continuous trading scenarios. This enables machine learning models to achieve higher accuracy and greater practicality in real-world trading environments.
3. Applied to predict Tesla’s option price? Tesla is very unique compared to other S&P 500 stock options. Due to its high volatility, the CEO’s sentiments, emerging industry dynamics, and growth expectations, predicting Tesla’s call option price using these existing patterns would be very challenging or yield poor performance.
