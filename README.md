# 🚦 Chicago Traffic Crashes — Injury Severity Prediction

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-orange?logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-latest-green)
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
