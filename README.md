# Marketing-Analytics-for-ROI-Optimization
# 📊 Marketing Mix Modeling & GMV Optimization

This project focuses on analyzing a large-scale marketing dataset (1.6M+ records) to understand the impact of various marketing levers on GMV (Gross Merchandise Value), optimize marketing budgets, and drive data-informed strategic decisions. The solution applies **Bayesian Marketing Mix Modeling (Lightweight_MMM)** with advanced preprocessing, media response modeling, and ROI forecasting.

---

## 🚀 Project Objectives

- 📌 **Performance Driver Analysis**  
  Identify key KPIs influencing revenue using historical sales and marketing data.

- 📌 **Marketing ROI Measurement**  
  Quantify the return on investment for different media channels.

- 📌 **Budget Optimization**  
  Recommend optimal media allocation for maximum GMV impact.

---

## 📂 Data Overview

- **Size:** 1.6M+ rows  
- **Sources:** Order data, SKU metadata, media spends, weather, event days  
- **Features:** 23 columns with categorical, numerical, temporal, and derived metrics  
- **Challenges:** Missing values, outliers, multicollinearity, and file inconsistency

---

## 🧹 Data Preprocessing

- 🔍 **Missing Value Treatment**
  - `GMV`: dropped missing values
  - `Weather`: imputed using rolling average
- 📈 **Transformations**
  - Log transformation applied to skewed distributions
- 🔗 **Dataset Merging**
  - Joined datasets using `FSN_ID` to connect SKUs with transactions
- 🧰 **Outlier Detection**
  - Used boxplots and scatterplots to identify extreme values

---

## 🔍 Exploratory Data Insights

- **GMV Trends:**  
  - Fluctuates across months with peaks in October, December, and April
  - Drops in summer months due to seasonal vacations

- **Customer Behavior:**  
  - 78.5% new customers; average GMV ~₹2,438  
  - 21.5% repeat customers; average GMV ~₹2,494

- **Sales by Region:**  
  - Top 20% of regions contribute ₹1.28M  
  - Bottom 20% regions only ₹9.65K → growth opportunity

- **SLA Impact:**  
  - Faster delivery (low SLA) is linked to higher GMV

- **Payment Trends:**  
  - COD preferred overall; credit card use spikes in April (tax season)

---

## 📊 Strategic Analysis

### 📆 Special Days

- **Discount Days:**
  - Boost average GMV significantly
  - Don't increase units per order

- **Holiday Patterns:**
  - Slight GMV dip due to offline shopping preference

### 🌦️ Weather Correlation

- Cameras perform best on dry, warm days  
- Gaming-related products sell better during rainy weather

### 📺 Media Channel Performance

| Channel              | Best Product Fit     | Notes                                |
|---------------------|----------------------|--------------------------------------|
| Online Marketing     | Camera, Gaming       | Highest overall correlation           |
| Sponsorship          | EntertainmentSmall   | Strong event-driven impact            |
| TV Advertising       | Camera               | Still relevant for some segments      |
| Digital & SEM        | Low impact           | Need reevaluation                     |
| Affiliates           | Moderate             | Opportunity via influencer networks   |

---

## 📈 Modeling Approach – Lightweight_MMM

A robust **Bayesian Marketing Mix Modeling** pipeline using **NumPyro** and probabilistic programming.

### 🛠️ Model Components

1. **Data Collection & Cleaning**  
   Handle missing values, create features, normalize distributions.

2. **Bayesian Regression**  
   Use priors, hierarchical modeling, and MCMC sampling.

3. **Media Response Modeling**  
   - Adstock effect  
   - Saturation/diminishing returns  
   - Baseline & trend adjustments

4. **Forecasting**  
   Predict ROI and simulate future performance under different spend scenarios.

5. **Optimization**  
   Budget reallocation based on model-inferred efficiency.

---

## 💰 Results & Optimization

- **Before Optimization:**
  - Heavy reliance on sponsorship & digital
  - High spend did not always yield better ROI

- **After Optimization:**
  - Suggested rebalancing across online marketing, sponsorship, and affiliates
  - Generated higher ROI with reduced spend

- **Example:**
```python
Previous Budget:  [71.37, 23.51, 343.99, 9.59, 386.74, 123.65, 90.39, 15.03, 138.92]  
Optimized Budget: [85.68, 28.22, 322.10, 11.24, 309.50, 148.44, 105.58, 18.05, 166.77]
