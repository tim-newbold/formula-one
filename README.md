# 🏎️ Formula 1 Race Position Predictor with XGBoost

This project uses historical Formula 1 data and machine learning to predict race **finishing positions** for drivers. Leveraging XGBoost regression, the model evaluates a wide range of features including circuit attributes, driver profiles, and race characteristics to generate ranked predictions.

> 💡 **Goal**: Use real-world F1 data to predict a driver’s finish position and rank them for upcoming races.

---

## 🔧 Tech Stack

- **Language**: Python  
- **Libraries**: pandas, numpy, scikit-learn, XGBoost, seaborn, matplotlib  
- **Environment**: Google Colab

---

## 📁 Data Overview

- `f1_full_v3.csv`: Historical training dataset  
- `predict.csv`: Testing dataset with driver info for ranking  

Key Features Used:
- Circuit type, track direction, track type
- Overtake difficulty rating
- Engine, team, and year metadata
- Normalized and encoded driver and race attributes

Target Variable:
- `position`: Driver’s final race placement (numerical)

---

## ⚙️ Model Pipeline

### 🔹 Preprocessing
- Dropped irrelevant columns (e.g. driver name, URL)
- Applied one-hot encoding to categorical variables
- Split dataset into training and testing sets (80/20)

### 🔹 Hyperparameter Tuning
Used **RandomizedSearchCV** to find optimal parameters for XGBoost:

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
