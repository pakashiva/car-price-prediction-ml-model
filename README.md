# 🚗 Car Price Prediction — Model Development

## 📌 Project Overview

This project focuses on building a robust machine learning model to predict used car prices based on vehicle specifications such as manufacturer, model, production year, fuel type, engine volume, mileage, and additional attributes.

The objective is to develop a high-performing regression model capable of accurately estimating car prices for real-world applications.

---

## 📊 Dataset Overview

The dataset contains structured vehicle information including:

* Manufacturer
* Model
* Production Year
* Category
* Fuel Type
* Engine Volume
* Mileage
* Cylinders
* Gearbox Type
* Drive Wheels
* Doors
* Wheel Type
* Color
* Airbags
* Levy

Additional engineered features:

* Age
* Mileage_per_Year

Target variable:

* Price (log-transformed during training)

---

## 🔎 Data Preprocessing

### ✅ Data Cleaning

* Removed duplicates
* Handled missing values
* Standardized categorical features

### ✅ Feature Engineering

* `Age = Current Year - Production Year`
* `Mileage_per_Year = Mileage / (Age + 1)`
* Log transformation applied to:

  * Target variable (Price)
  * Mileage feature

### ✅ Encoding Strategy

* **Target Encoding**:

  * Manufacturer
  * Category
  * Fuel Type
  * Model
  * Color

* **One-Hot Encoding**:

  * Gear box type
  * Drive wheels
  * Wheel

* Binary Mapping:

  * Leather Interior → Yes/No → 1/0
  * Turbo → Yes/No → 1/0

---

## 🤖 Model Selection

Multiple models were evaluated using cross-validation.

Final Selected Model:

* **RandomForestRegressor**

  * n_estimators = 200
  * max_depth = None
  * min_samples_split = 2
  * min_samples_leaf = 1

---

## 📈 Model Performance

* **R² Score:** 0.95
* **RMSE (Log Scale):** 0.22

The model explains approximately 95% of the variance in car prices, indicating strong predictive capability.

---

## 💾 Saved Artifacts

The following files are exported for deployment:

* `car_price_predictor.pkl` → Trained model
* `model_columns.pkl` → Final feature column order
* `target_encoding_maps.pkl` → Target encoding mappings

---

## 🚀 Conclusion

The model demonstrates strong performance and effective feature representation. Proper preprocessing, encoding strategies, and feature engineering significantly improved predictive accuracy.

This trained model is used in the Streamlit web application for real-time price prediction.

---

## Dataset Credit
The dataset used in this project is publicly available on **Kaggle** and is utilized here strictly for educational and analytical purposes.
[https://www.kaggle.com/datasets/deepcontractor/car-price-prediction-challenge]


---

## 🛠 Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* Joblib
* Matplotlib / Seaborn

---

## 📌 Future Improvements

* Use full sklearn Pipeline for deployment safety
* Hyperparameter optimization with advanced search
* Model explainability using SHAP

---

Developed as part of an end-to-end machine learning workflow.
