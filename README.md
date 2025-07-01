# 📊 Bayesian Marketing Mix Modeling (Lightweight_MMM)

A comprehensive data science project focused on **optimizing marketing budgets**, **analyzing ROI**, and **modeling ad effectiveness** using **Bayesian Marketing Mix Modeling (MMM)**. The project evaluates the contribution of various marketing channels toward revenue growth, using real-world order and event datasets.

---

## 📌 Objective

- Quantify the effect of marketing channels on **GMV (Gross Merchandise Value)**.
- Evaluate **channel-level ROI** using historical marketing and order data.
- Forecast future performance and suggest **optimal budget allocation**.
- Build a robust, interpretable, and scalable **Bayesian MMM model**.

---

## 🧾 Dataset Overview

- 🧩 **Size:** 1.6M+ rows with detailed order, product, marketing, and event data.
- 📂 **Sources Merged:** 
  - `SKU_details.csv` (product metadata),
  - `Customers_Orders_Data.csv` (transactional info),
  - Weather & Special Events data (external signals).

---

## 🔧 Data Preprocessing & Cleaning

### ✅ Key Steps

- **Missing Value Handling:**
  - Numerical values (e.g., GMV): Dropped or imputed.
  - Weather Data: Imputed via **rolling average smoothing**.
- **Outlier Detection:**
  - Used boxplots and scatter plots to remove anomalous records.
- **Log Transformation:**
  - Applied to features to make distributions more Gaussian.
- **Categorical Consolidation:**
  - Rare venue categories grouped as “Other”.

---

## 🧠 Feature Engineering

- 🧮 Created meaningful features like:
  - `Run rate`, `Wickets in hand`, `Balls remaining`, `SLA`.
- 🧷 Joined FSN_ID to link product & transaction-level info.
- 🌦️ External signals like **weather conditions** and **holiday indicators** included to model real-world effects.

---

## 📈 Exploratory Data Analysis (EDA)

- 📊 **GMV Trends:**
  - Peaks: October, December 2023, April 2024.
  - Dips: August, January, June—linked to seasonal demand.
- 🔍 **Product Performance:**
  - Cameras: High GMV but fewer units → high-value items.
  - Entertainment Small: High volume, low per-unit GMV.
- 🌧️ **Weather Analysis:**
  - Rain ↓ → Camera Sales ↓; Game cards ↑ (indoor activity).
- 🏷️ **Discount & SLA Insights:**
  - Faster deliveries → Higher GMV.
  - Non-discounted sales dominate high-value items.

---

## 💡 Strategic Insights

- **High Sales Region Strategy:**
  - Prioritize top 20% performing zones.
- **Repeat Customers:**
  - Only 21.5% of customers are repeat buyers. Opportunity to target loyalty.
- **Luxury vs Mass Market:**
  - Skewed distribution; opportunity to grow luxury segment.

---

## 📊 Bayesian MMM Model – Lightweight_MMM

### ⚙️ Modeling Components

| Step                        | Description |
|----------------------------|-------------|
| 1️⃣ Data Preprocessing     | Handle nulls, standardize inputs |
| 2️⃣ Model Selection        | Bayesian Regression via NumPyro |
| 3️⃣ Media Response Model  | Simulate adstock, diminishing returns |
| 4️⃣ Model Training         | MCMC sampling & cross-validation |
| 5️⃣ Forecasting            | ROI simulation under new budgets |
| 6️⃣ Budget Optimization    | Scenario-based reallocation |
| 7️⃣ Deployment             | Track performance & automate reporting |

### 📐 Key Concepts

- **Adstock & Carryover:** Delayed impact of ad impressions.
- **Saturation Curve:** Models diminishing returns on spend.
- **External Factor Integration:** Seasonality, weather, holidays.
- **Bayesian Inference:** MCMC-based sampling to model uncertainty.

---

## 💸 Optimization Results

| Channel              | Previous Budget (₹) | Optimal Budget (₹) |
|----------------------|---------------------|---------------------|
| TV                   | 71,377              | 85,683              |
| Radio                | 23,512              | 28,225              |
| Online Marketing     | 343,990             | 322,105             |
| SEM                  | 9,596               | 11,242              |
| Digital              | 386,742             | 309,504             |
| Content Marketing    | 123,658             | 148,442             |
| Sponsorship          | 90,400              | 105,590             |
| Affiliates           | 15,040              | 18,054              |
| Others               | 138,926             | 166,770             |

- 🔁 Reallocation improved GMV and reduced waste.
- 📉 Channels like **Radio** and **SEM** had low ROI.
- 📈 Boosting **Online Marketing** and **Content** improved returns.

---

## 🔍 Key Takeaways

- More spend ≠ more returns → Focus on **optimization**.
- **Online marketing** and **sponsorships** deliver best ROI.
- Faster delivery (low SLA) = more high-value purchases.
- GMV is **positively correlated** with MRP and negatively with SLA.

---

## 🛠️ Technologies Used

- **Python** (Pandas, NumPy, Seaborn, Matplotlib)
- **Bayesian Libraries:** NumPyro, PyMC3
- **MCMC Sampling:** Markov Chain Monte Carlo
- **Scikit-learn:** For baseline ML experiments
- **Lightweight_MMM** (Open-source MMM framework)

---

## 📚 References

- [Wikipedia: Marketing Mix Modeling](https://en.wikipedia.org/wiki/Marketing_mix_modeling)
- [Google Meridian – Bayesian MMM](https://research.google/pubs/pub46710/)

---

## 🧠 Future Work

- Integrate **real-time marketing dashboards**.
- Enable **dynamic budget reallocation** via APIs.
- Use **Geo-level** segmentation to further personalize spend.

---

## 🙌 Authors & Contributors

**TEAM ID:** 2025111  
Built with collaboration across data science, business, and marketing functions.

---

## 📌 Appendix

- Appendix includes:
  - Raw data exploration snapshots
  - Visualization breakdowns
  - Budget simulation matrices
