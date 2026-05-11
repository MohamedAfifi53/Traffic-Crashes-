# 🚦 Chicago Traffic Crashes — Injury Severity Prediction

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-orange?logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-latest-green?logo=xgboost)
![License](https://img.shields.io/badge/License-MIT-yellow)

> A complete end-to-end Machine Learning project that predicts the **severity of injuries** in traffic crashes across Chicago — from raw data to a saved, deployable model.

---

## 📌 Problem Statement

Given a traffic crash report, can we predict how severe the resulting injury will be?

**Target variable:** `MOST_SEVERE_INJURY` — 5 classes:
| Label | Description |
|---|---|
| 0 | No Indication of Injury |
| 1 | Reported, Not Evident |
| 2 | Nonincapacitating Injury |
| 3 | Incapacitating Injury |
| 4 | Fatal |

---

## 📂 Dataset

- **Source:** [Chicago Data Portal — Traffic Crashes](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if)
- **Size:** 100,000 records sampled from the full dataset
- **Features:** Road conditions, weather, time of crash, traffic control devices, location, and more

---

## 🔄 Project Pipeline

```
Raw Data
   │
   ▼
EDA & Visualization
   │
   ▼
Preprocessing
 ├── Drop low-value columns
 ├── Fill missing values (median / mode)
 └── Label Encoding
   │
   ▼
Train / Test Split (80/20, stratified)
   │
   ▼
SMOTE (handle class imbalance)
   │
   ▼
Feature Selection + PCA (via GridSearchCV pipeline)
   │
   ▼
Model Training (11 models)
   │
   ▼
Hyperparameter Tuning (RandomizedSearchCV)
   │
   ▼
Model Comparison (Accuracy + Training Time)
   │
   ▼
Save Best Model (joblib)
```

---

## 🤖 Models Trained

| Model | Type |
|---|---|
| Logistic Regression | Linear |
| K-Nearest Neighbors | Instance-based |
| Support Vector Machine | Kernel-based |
| Decision Tree (via Bagging) | Tree |
| Random Forest | Ensemble |
| AdaBoost | Boosting |
| Gradient Boosting | Boosting |
| XGBoost | Boosting |
| Bagging Classifier | Ensemble |
| Stacking Classifier | Meta-ensemble |
| **Tuned Random Forest** | Ensemble + Tuning |
| **Tuned XGBoost** ⭐ | Boosting + Tuning |

---

## 📊 Key Results

- **Best Model:** Tuned XGBoost
- **Evaluation Metrics:** Accuracy, F1-weighted, Classification Report, Confusion Matrix
- **Feature Selection:** SelectKBest (f_classif, k=20) — avoids chi2's limitation with negative PCA values
- **Dimensionality Reduction:** PCA with best n_components found via GridSearchCV

---

## 💡 Business Insights

- 🌤️ Most crashes happen in **clear weather** — high traffic volume, not high risk per trip
- 🕐 Peak crash hours: **6–8 AM** and **2–5 PM** (commute times)
- 📅 **Saturday** has the highest crash count
- 🛣️ **Undivided roads** see the most serious injuries
- ⚠️ Top causes of serious injuries: failing to yield, improper lane use, distracted driving

---

## 🗂️ Repository Structure

```
Traffic-Crashes/
│
├── Chicago_Traffic_Crashes_Final.ipynb   # Full notebook (EDA → Model → Save)
├── README.md                             # This file
└── requirements.txt                      # Python dependencies
```

---

## ⚙️ Requirements

```bash
pip install -r requirements.txt
```

**Main dependencies:**
```
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
xgboost
folium
joblib
```

---

## 🚀 How to Run

1. **Clone the repo**
```bash
git clone https://github.com/MohamedAfifi53/Traffic-Crashes.git
cd Traffic-Crashes
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Download the dataset** from [Chicago Data Portal](https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if) and place it as:
```
Traffic_Crashes_-_Crashes.csv
```

4. **Run the notebook**
```bash
jupyter notebook Chicago_Traffic_Crashes_Final.ipynb
```

---

## 📁 Output Files (generated after running)

| File | Description |
|---|---|
| `best_model.pkl` | Saved best model (Tuned XGBoost) |
| `pca_pipeline.pkl` | Fitted preprocessing pipeline |
| `model_comparison.png` | Accuracy & time chart for all models |
| `feature_importance.png` | Top features from RF & XGBoost |
| `business_insights.png` | EDA insights dashboard |

---

## 👤 Author

**Mohamed Afifi**
- GitHub: [@MohamedAfifi53](https://github.com/MohamedAfifi53)

---

## 📄 License

This project is licensed under the MIT License.
