# 🏠 California Housing Price Prediction

## 📌 Project Overview

This project focuses on predicting housing prices in California using machine learning techniques. The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets), and includes various features related to California housing units such as location, income level, room statistics, and household demographics.

The goal of this project is to build robust models that can help real estate stakeholders—such as investors, agents, and policymakers—make informed decisions by estimating median house values accurately.

---

## 📂 Dataset Description

The dataset contains **20,640 rows** and includes the following key features:

- `longitude` and `latitude`: Geographic location  
- `housing_median_age`: Age of the house  
- `total_rooms`, `total_bedrooms`: Structural details  
- `population`: Number of people in the area  
- `households`: Group of people residing in a housing unit  
- `median_income`: Median income in the block  
- `ocean_proximity`: Categorical variable indicating distance to ocean  
- `median_house_value`: **Target variable** (i.e., the price we aim to predict)

---

## 🧹 Data Cleaning & Preprocessing

### Handling Missing Values

- `total_bedrooms` had missing values.
- Imputation was done using the **median** to preserve distribution and reduce outlier influence.

### Outlier Treatment

Instead of removing outliers (which could lead to significant data loss), **capping** was applied using percentile thresholds (e.g., 1st and 99th percentiles). This technique is preferred in real estate datasets due to the presence of naturally extreme values (luxury homes, urban hotspots) that are still valid. 

**Capping retains valuable information** while preventing these values from disproportionately influencing the model.

---

## 🏗️ Feature Engineering

To improve model performance, new features were engineered:

- `rooms_per_household = total_rooms / households`
- `bedrooms_per_room = total_bedrooms / total_rooms`
- `population_per_household = population / households`

These features better represent housing density and affordability.

Highly correlated features like `total_rooms`, `total_bedrooms`, and `population` were dropped after correlation analysis to reduce multicollinearity, which can lead to unstable linear models.

---

## ⚙️ Modeling & Evaluation

Two regression models were trained and compared:

### 🔹 Linear Regression

- **RMSE:** 74,807.86  
- **MAE:** 52,256.77  
- **R² Score:** 0.57  

Linear Regression provides a simple, interpretable baseline and captures general trends in the data.

### 🔹 Random Forest Regressor

- **RMSE:** ~50,301  
- **MAE:** ~32,274  
- **R² Score:** 0.81  

Random Forest outperforms linear regression significantly, capturing non-linear relationships and complex interactions.

---

## ✅ Why the Models Are Suitable

### Acceptable Error Margin

In real estate, it’s normal to have **RMSE between 50,000 and 75,000**  and **MAE between 32,000 and 55,000**, due to variability in neighborhood conditions, amenities, and buyer preferences. Both models meet this acceptable error range.

### Strong R² Score

- R² of **0.57 (Linear)** and **0.81 (Random Forest)** show strong explanatory power.
- These models explain a large portion of house price variability, making them valuable for decision-making and forecasting.

---

## 📊 Technical Stack

- **Languages**: Python  
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`  
- **Techniques Used**: Data preprocessing, feature engineering, outlier capping, encoding, model training and evaluation

---

## 📈 Future Improvements

- Hyperparameter tuning with `GridSearchCV` for Random Forest  
- Incorporate external datasets (e.g., crime rate, school quality)  
- Deployment as a web app using Streamlit or Flask

---

## 🖥️ Streamlit Dashboard for Housing Price Prediction

To provide an interactive and user-friendly experience, a **Streamlit dashboard** was built to predict California housing prices. This dashboard allows users to input the housing details (such as latitude, longitude, total rooms, population, etc.) and get an estimate of the median house value in that area.

You can explore the **California Housing Price Prediction Dashboard** here:

🔗 [Explore the Dashboard](https://cg9k8wztmupcwmdg7to5uq.streamlit.app/)

---

## 📬 Contact

For questions or collaboration opportunities, feel free to reach out:

**Ibrahim Ali**  
*Data Scientist | AI Practitioner*  
📧 ibrahimgama4@gmail.com
