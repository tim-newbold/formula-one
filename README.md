# 🏎️ Formula 1 Race Position Predictor – ML + ETL + Visualization

This project combines **machine learning**, **ETL automation**, and **dashboard visualization** to predict Formula 1 drivers’ race **finishing positions** based on historical and real-time data. By integrating data from the Jalopnik API, storing it in a SQL Server backend, and applying models like **XGBoost** and **KNN**, this pipeline enables powerful F1 performance forecasting.

> 💡 **Goal**: Automatically pull and analyze Formula 1 data to predict and visualize driver race outcomes.

---

## ⚙️ System Components

### 🔄 ETL Pipeline
- Pulls real-time/historical F1 data via the **Jalopnik API**
- Cleanses and transforms data using Python
- Loads data into **SQL Server** using **SQLAlchemy**

### 🧠 Machine Learning Models

#### 🔹 XGBoost Regressor
- Predicts numeric race finishing position
- Tuned with **RandomizedSearchCV** for optimal hyperparameters

#### 🔹 KNN Classifier
- Custom built KNN Classifier for Circuits

### 📊 Visualization
- Outputs are integrated into **Power BI Dashboards**
- Enables exploration and filtering by driver, team, circuit, etc.

---

## 🧰 Tech Stack

- **Languages**: Python, SQL  
- **Libraries**: pandas, numpy, scikit-learn, XGBoost, matplotlib, seaborn  
- **ETL**: Requests, SQLAlchemy, PyODBC  
- **Storage**: Microsoft SQL Server  
- **Dashboard**: Power BI  
- **Environment**: Jupyter / Colab / Local Python

---

## 📁 Data Overview

- SQL Tables: Ingested and transformed data stored in SQL Server  

**Key Features Include:**
- Circuit layout, track direction, lap count, overtake difficulty  
- Driver stats, team engine configurations, qualifying positions  
- Temporal context: race year, event type, and driver experience

---

## 🧪 Model Training & Tuning

### 🔹 XGBoost Parameters (Optimized)

```python
Best Parameters:
{
  'subsample': 0.8,
  'reg_lambda': 3,
  'reg_alpha': 10,
  'n_estimators': 500,
  'min_child_weight': 4,
  'max_depth': 6,
  'learning_rate': 0.05,
  'gamma': 0.01,
  'colsample_bytree': 0.7
}
