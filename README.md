# 🛍️ Customer Segmentation — K-Means Clustering

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange?logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Project Overview

This project applies **K-Means Clustering** to segment mall customers into distinct groups based on their age and spending behavior. The goal is to identify meaningful customer profiles that can inform targeted marketing strategies. The optimal number of clusters is determined using the Elbow Method and Silhouette Score, and each segment is profiled with actionable marketing recommendations.

---

## 📂 Dataset Description

| Property | Details |
|---|---|
| **Source** | [Customer Segmentation Tutorial — Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) |
| **Rows** | 200 |
| **Columns** | 5 |
| **Missing Values** | None |

### Features

| Feature | Type | Description |
|---|---|---|
| `CustomerID` | Int | Unique ID — dropped before clustering |
| `Gender` | Categorical | Male/Female — label encoded |
| `Age` | Numeric | Customer age |
| `Annual Income (k$)` | Numeric | Annual income in thousands USD |
| `Spending Score (1-100)` | Numeric | Mall-assigned score based on spending behavior |

---

## 🛠️ Technologies Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` & `seaborn` | Data visualization |
| `scikit-learn` | Scaling, K-Means clustering, Silhouette Score |
| `joblib` | Model serialization |

---

## 🤖 Model Used

### K-Means Clustering

**Pipeline:**
1. Drop `CustomerID`, encode `Gender`
2. Select clustering features — `Age` and `Spending Score (1-100)`
3. Standardize features with `StandardScaler`
4. Run Elbow Method and Silhouette Score for k=2 to k=10
5. Apply K-Means with optimal k=6
6. Profile each cluster by Age, Income, Spending Score and Gender
7. Assign segment names and marketing actions

---

## 📊 Choosing Optimal k

| k | Silhouette Score |
|---|---|
| 2 | 0.4721 |
| 3 | 0.4395 |
| 4 | 0.4384 |
| 5 | 0.4475 |
| **6** | **0.4566** ✅ |
| 7 | 0.4115 |
| 8 | 0.4048 |
| 9 | 0.4086 |
| 10 | 0.4381 |

**k=6** was selected — highest silhouette score after k=2, with a clear elbow in the inertia curve.

---

## 📈 Cluster Profiles & Marketing Actions

| Cluster | Segment | Avg Age | Avg Spending | Count |
|---|---|---|---|---|
| 1 | Young High Spenders | 30 | 82 | 57 |
| 4 | Young Moderate Spenders | 25 | 50 | 38 |
| 0 | Young Low Spenders | 34 | 16 | 25 |
| 5 | Middle-Aged Moderate Spenders | 47 | 46 | 37 |
| 3 | Middle-Aged Low Spenders | 53 | 14 | 23 |
| 2 | Elderly Moderate Spenders | 65 | 50 | 20 |

### Marketing Actions

**Young High Spenders** — VIP memberships, premium products, exclusive early access deals

**Young Moderate Spenders** — Loyalty reward programs, trendy product promotions, social media campaigns

**Young Low Spenders** — Discount campaigns, budget bundles, incentivize first purchases

**Middle-Aged Moderate Spenders** — Family-oriented promotions, seasonal offers, convenience-focused products

**Middle-Aged Low Spenders** — Value-for-money deals, essential product bundles, re-engagement campaigns

**Elderly Moderate Spenders** — Premium comfort products, personalized service, health and wellness promotions

---

## 📁 Project Structure

```
customer-segmentation/
│
├── Mall_Customers.csv              # Raw dataset
├── Customer_Segmentation.ipynb     # Main notebook
├── customer_segments.csv           # Dataset with cluster labels added
├── kmeans_model.pkl                # Saved K-Means model
├── kmeans_scaler.pkl               # Saved StandardScaler
├── requirements.txt                # Dependencies
└── README.md                       # Project documentation
```

---

## 👤 Author

**Kishkaya Gayathri**
Bachelor of Science in Information Technology specialized in Artificial Intelligence
[SLIIT] — [2026]
