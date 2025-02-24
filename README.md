# **Energy Consumption Prediction Project**

### **Project Overview**
This project aims to analyze **energy consumption patterns** in South Carolina and North Carolina to develop strategies for reducing energy demand without constructing new power plants. The focus is on **July**, the month with the highest energy consumption, to understand the primary drivers of energy usage and predict future peak demand. The analysis incorporates **machine learning models** to forecast energy usage, integrating **weather, static house, and energy consumption data**.

### **Team Members**
- **Ramya Chowdary Patchala**
- **Akshay Joshi**
- **Hemanth Chowdary Thammeneni**
- **Rithika Gurram**
- **Kishan**

---

## **Table of Contents**
- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Data Preprocessing](#data-preprocessing)
- [Modeling Approach](#modeling-approach)
- [Results and Analysis](#results-and-analysis)
- [Shiny App](#shiny-app)
- [Future Work](#future-work)
- [Installation & Usage](#installation--usage)
- [Project Structure](#project-structure)
- [Acknowledgments](#acknowledgments)

---

## **Dataset Description**
The project utilizes **three primary datasets**:
1. **Static House Data** – Includes attributes such as **house size, insulation levels, heating/cooling systems, and geographic details**.
2. **Energy Usage Data** – Contains **hourly electricity consumption profiles** for each house.
3. **Weather Data** – Provides **temperature, humidity, wind speed, and solar radiation** information for July.

### **Final Cleaned Dataset:**
- **176,948 rows and 111 columns**
- Features include **building characteristics, climate zones, weather conditions, and energy usage trends**.
- Energy usage is **aggregated at the daily level** to facilitate time-series modeling.

---

## **Data Preprocessing**
To ensure high-quality input for modeling, the following steps were applied:

1. **Data Cleaning**
   - Removed **columns with excessive missing values**.
   - Handled missing values using **median imputation** for continuous variables.

2. **Feature Engineering**
   - Aggregated hourly data into **daily total energy usage** per house.
   - Merged **household data** with **weather data** using **County ID**.

3. **Data Transformation**
   - Normalized numerical variables for better model performance.
   - One-hot encoding for categorical variables like **county and climate zones**.

---

## **Modeling Approach**
We implemented multiple machine learning models to predict **energy consumption**:

### **1. Linear Regression**
- A baseline model used to assess the linear relationships between **house attributes, weather conditions, and energy usage**.
- Achieved an **R² score of 81.16%**.

### **2. XGBoost**
- A gradient boosting decision tree model trained for **high-performance energy prediction**.
- Achieved an **R² score of 84.85%**.

### **3. XGBoost with Hyperparameter Tuning**
- Tuned hyperparameters (`max_depth=8`, `learning_rate=0.2`, `subsample=0.7`, `colsample_bytree=0.7`) to improve accuracy.
- Achieved the **highest accuracy of 88.58%**.

### **Model Evaluation Metrics**
- **Regression Models:** Evaluated using **R², RMSE (Root Mean Squared Error), and MAE (Mean Absolute Error)**.
- **Feature Importance:** Used SHAP (SHapley Additive Explanations) to interpret **key drivers of energy consumption**.

---

## **Results and Analysis**
Key insights derived from the analysis:

1. **Weather Conditions Impact**
   - Higher **temperatures increase energy usage**, especially for **cooling demand**.
   - A **5-degree rise in temperature** leads to a significant increase in energy consumption.

2. **Geographical Variation**
   - Energy usage **varies across different counties** due to climate and income disparities.
   - Coastal areas showed **higher cooling needs** compared to inland regions.

3. **Building Characteristics**
   - Houses with **better insulation and modern HVAC systems** consume **less energy**.
   - Older houses and **larger properties** have **higher energy demands**.

4. **Prediction of Future Demand**
   - Simulating a **5-degree temperature increase**, the **peak energy demand** is projected to rise by **8-12%**.
   - A **demand-response strategy** is required to manage peak loads efficiently.

---

## **Shiny App**
An **interactive Shiny web application** was developed to allow users to:
- **Visualize energy usage trends**.
- **Compare current vs. predicted energy consumption**.
- **Explore the impact of temperature changes**.

### **Shiny App Features**
- **Total Energy Consumption Trends**
- **County-wise Energy Usage Patterns**
- **Impact of Climate Change on Future Demand**
- **Geographical Analysis of Energy Hotspots**

👉 **Access the Shiny App:** [Energy Consumption Dashboard](https://rpatchal.shinyapps.io/EnergyConsumption/)

---

## **Future Work**
1. **Enhancing Model Accuracy**
   - Explore deep learning models like **LSTMs (Long Short-Term Memory Networks)** for time-series forecasting.
   - Incorporate additional **socioeconomic factors** affecting energy demand.

2. **Demand Response Optimization**
   - Implement a **real-time energy demand monitoring system**.
   - Develop strategies like **dynamic pricing** to **reduce peak loads**.

3. **Real-Time Data Integration**
   - Improve energy predictions by **integrating smart meter data**.
   - Include **real-time weather API** for continuous updates.

---

## **Installation & Usage**
### **Prerequisites**
- **RStudio** (for executing `.Rmd` files)
- **Python 3.x** (for additional data analysis)
- Required R libraries: `tidyverse`, `caret`, `ggplot2`, `xgboost`, `shiny`
- Required Python libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

---

## **Project Structure**
```
📂 Energy-Consumption-Prediction
│── 📄 README.md               # Project Documentation
│── 📄 FinalProject.Rmd        # Main R Markdown Report
│── 📄 Final_Project_Report.pdf # Detailed Project Report
│── 📄 Shiny_App/              # Shiny App Source Code
│── 📄 DATA_SCIENCE_FINAL_PROJECT.pptx # Presentation
```

---

## **Acknowledgments**
This project was completed as part of a **Data Science Capstone Project**. Special thanks to **IST687 Faculty** and **stakeholders at the Energy Company (eSC)** for providing valuable feedback.

