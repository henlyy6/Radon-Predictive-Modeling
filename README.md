# 🌬️ Radon Prediction Using Machine Learning

This project investigates whether indoor radon concentration can be predicted from environmental sensor measurements, including CO₂, PM2.5, PM1, temperature, humidity, VOCs, and atmospheric pressure.

The objective was to develop a machine learning model capable of estimating radon levels from commonly available indoor air quality measurements while identifying the environmental factors that contribute most to radon accumulation.

---

## 📊 Dataset

- ~96,000 observations
- 8 environmental variables
- Target variable: **Radon concentration (Bq/m³)**

### Features

- CO₂
- PM2.5
- PM1
- Temperature
- Humidity
- VOC
- Pressure

---

## 🔬 Workflow

### Data Processing
- Timestamp standardization
- Missing value interpolation and backfilling
- Data cleaning and preparation
- Synchronization of asynchronous sensor measurements

### Exploratory Data Analysis
- Descriptive statistics
- Distribution analysis
- Correlation assessment
- Feature importance investigation

### Machine Learning
- XGBoost Regressor
- 80/20 train-test split
- Model evaluation using R² score

### Model Interpretation
- Feature importance analysis
- SHAP (SHapley Additive exPlanations)

---

## 📈 Results

### Model Performance

- **Model:** XGBoost Regressor
- **R² Score:** **0.915**
- **Samples:** ~96,000

The model explained approximately **91.5% of the variance** in unseen test data, demonstrating a strong relationship between indoor environmental conditions and radon concentration.

---

## 🔍 Key Findings

- Environmental sensor measurements contain significant predictive information for indoor radon levels.
- Ventilation-related variables such as **CO₂** and **VOC concentrations** were among the most influential predictors.
- SHAP analysis provided insight into how individual features contributed to model predictions and overall model behavior.

---

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib

---

## 📂 Repository Contents

- Data preprocessing workflow
- Exploratory data analysis (EDA)
- Machine learning model training
- Performance evaluation
- Feature importance visualizations
- SHAP explainability analysis

---

## ⚠️ Disclaimer

This project was conducted as a personal exploration of machine learning methods applied to environmental sensor data. The results demonstrate predictive potential but should not be interpreted as a validated radon monitoring system without further testing on independent datasets.
