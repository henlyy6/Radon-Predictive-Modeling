# 🌬️ Air-Quality-Radon-XGBoost

This repository serves as a formal documentation of findings from a numerical investigation evaluating the capacity of tree-based ensemble methods to infer indoor **Radon ($Bq/m^3$)** dynamics. The study utilizes co-located environmental and climate metrics—specifically $CO_2$, PM2.5, PM1, Temperature, Humidity, VOCs, and atmospheric Pressure—to analyze feature dependencies.

The primary objective was to assess the predictability of localized radon accumulation using standard indoor air quality indicators and to interpret the underlying non-linear interactions using **SHAP (SHapley Additive exPlanations)** frameworks.

---

## 🔬 Methodology & Core Workflow

1. **Data Preprocessing & Synchronization:** 
   - Standardized disparate sensor formats and raw temporal logging intervals.
   - Resolved the asynchronous alignment of the raw sensor logs via linear interpolation and backward filling to establish a synchronized, structured dataframe ($96,347$ rows $\times$ $8$ variables).
2. **Predictive Modeling:**
   - Implemented an `XGBRegressor` utilizing a standardized 80/20 train/test partition.
   - Evaluated general baseline generalization capacity under default objective parameters (`reg:squarederror`).
3. **Interpretability Frameworks:**
   - Mapped weight-based feature importances to quantify the frequency of variables used across the ensemble splits.
   - Computed SHAP values to isolate the directional influence and marginal contribution of individual environmental factors on the target radon predictions.

---

## 📈 Quantitative Performance & Analytical Insights

* **Model Architecture:** Extreme Gradient Boosting (XGBoost Regressor)
* **Coefficient of Determination ($R^2$ Score):** `0.9150`
* **Key Observations:** The model successfully accounts for $\sim 91.5\%$ of the variance in the validation subset, indicating a strong mathematical coupling between general indoor climate indicators and radon accumulation. The high predictive weight assigned to ventilation-related proxies (such as $CO_2$ and VOC concentrations) highlights the structural correlation between reduced air exchange rates and localized radon stagnation.

---

## 🔧 Technical Stack

- **Data Engineering:** `pandas`, `NumPy`
- **Machine Learning Infrastructure:** `xgboost`, `scikit-learn`
- **Model Explainability & Diagnostic Plotting:** `shap`, `matplotlib`

---

## 📝 Research Limitations & Contextual Notes
- This repository functions exclusively as a static archival record of personal engineering analysis and methodology.
- The alignment strategy was tailored specifically to the structural gaps of this asynchronous dataset; variation in interpolation techniques or the introduction of boundary-condition anomalies may alter the calculated local feature importance.
