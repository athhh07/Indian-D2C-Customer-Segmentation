<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Kshashtra&fontSize=60&fontColor=white&animation=fadeIn&fontAlignY=35&desc=Indian%20D2C%20Customer%20Segmentation&descAlignY=55&descSize=20"/>

<br/>

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)
[![K-Means](https://img.shields.io/badge/K--Means-Clustering-00A98F?style=for-the-badge&logoColor=white)]()

<br/>

> **Turning D2C customer behavior into actionable segments — so every marketing rupee goes to the right customer.**

</div>

---

## 📌 What Is This Project?

Most D2C businesses treat every customer the same — same discount, same email, same campaign. That's expensive and ineffective.

**Kshashtra Customer Segmentation** fixes that. It analyzes purchasing behavior, website engagement, order history, and product preferences from a real Indian D2C clothing store to automatically group customers into distinct behavioral personas — then translates those personas into specific marketing and retention strategies.

The final output isn't just clusters. It's a **Power BI dashboard** that a business owner or marketing team can actually use to answer:

| Question | Answer from This Project |
|---|---|
| Who are my most valuable customers? | → Power Buyers segment |
| Which customers are about to churn? | → At-Risk segment with high recency |
| Who only buys during sales? | → Discount Hunters segment |
| Which segment should I target with loyalty programs? | → Loyal Explorers segment |
| Where should I stop wasting ad spend? | → One-Time Visitors segment |

---

## 🎯 Business Problem

```
D2C store has thousands of customers.
Every customer behaves differently.
Treating them the same leads to:

  ❌ Wasted ad spend on wrong audiences
  ❌ Missing high-value customers who need retention
  ❌ Giving discounts to customers who'd buy anyway
  ❌ Generic campaigns with low conversion
  ❌ No visibility into repeat-purchase potential

Solution → Segment customers, then act differently per segment.
```

---

## 📦 Datasets

<table>
<tr>
<td width="50%">

### 🛍️ Primary — Kshashtra D2C Store

**Source:** Kaggle

```
kaggle.com/datasets/kushsheth/
kshashtra-ecommerce-store-martking-and-sales
```

An AI-generated dataset closely resembling real Shopify store data for an Indian D2C clothing brand running Meta ads.

| File | Contains |
|---|---|
| customers.csv | Demographics, city tier, channel |
| orders.csv | Order dates, amounts, status |
| order_line_items.csv | Product-level order detail |
| website_sessions.csv | Session source, duration |
| website_daily.csv | Daily traffic aggregates |
| meta_ads_campaigns.csv | Paid campaign performance |
| sku_catalog.csv | Product categories, prices |
| inventory_snapshots.csv | Stock levels over time |
| purchase_orders.csv | Supplier order data |

</td>
<td width="50%">

### 💳 Supplementary — Digital Payment Context

**Source:** Kaggle

```
kaggle.com/datasets/nilesh2042/monthly-metrics
```

Monthly NPCI UPI/IMPS/NACH transaction volumes used to add a **UPI adoption growth index** — a contextual feature capturing how digitally mature the payment ecosystem was when each customer first ordered.

> ⚠️ **Note:** This dataset contains aggregate monthly metrics, not individual customer transactions. It enriches context, not direct features.

</td>
</tr>
</table>

---

## 🔄 Project Workflow

<div align="center">

```
┌─────────────────────────────────────────────────────────────┐
│                        RAW DATA                              │
│   9 CSV files · customers · orders · sessions · campaigns   │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 1 — DATA UNDERSTANDING                   │
│   Load all files · check shapes · understand join keys       │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 2 — DATA MERGING & CLEANING             │
│   Join 5 tables on Customer ID · fix nulls · remove returns  │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 3 — FEATURE ENGINEERING                  │
│   RFM features · behavioral · digital · UPI context index    │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 4 — EDA ON FEATURE MATRIX               │
│   Distributions · outlier handling · log transforms          │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 5 — CLUSTERING                           │
│   KMeans · Hierarchical · DBSCAN · Elbow · Silhouette        │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 6 — CLUSTER PROFILING                    │
│   Name each cluster · radar charts · business interpretation │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 7 — CAMPAIGN STRATEGY                    │
│   One actionable brief per segment · what to do & avoid      │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│               PHASE 8 — POWER BI DASHBOARD                   │
│   Interactive segment explorer · KPIs · marketing actions    │
└─────────────────────────────────────────────────────────────┘
```

</div>

---

## 🧠 Feature Engineering (15 Features)

The quality of clustering depends entirely on the features you build.
These 15 features capture four distinct dimensions of customer behavior:

<table>
<tr>
<td width="50%">

**📦 RFM Features**
| Feature | What It Measures |
|---|---|
| `recency_days` | Days since last purchase |
| `frequency` | Total orders placed |
| `monetary_total` | Total ₹ spent |
| `avg_order_value` | Spend per order |

**🛒 Behavioral Features**
| Feature | What It Measures |
|---|---|
| `category_diversity` | # of distinct product categories |
| `discount_sensitivity` | % of orders during sale periods |
| `return_rate` | Returned orders / total orders |
| `avg_days_between_orders` | Purchase interval consistency |

</td>
<td width="50%">

**📱 Digital / Channel Features**
| Feature | What It Measures |
|---|---|
| `city_tier` | 1 = Metro, 2 = Tier 2, 3 = Village |
| `acquisition_channel` | Instagram / Meta / Influencer / Organic |
| `is_paid_acquisition` | Came from a paid ad? (binary) |
| `session_to_order_ratio` | Orders / total sessions |
| `avg_pages_per_session` | Engagement depth per visit |

**💳 UPI Context Feature**
| Feature | What It Measures |
|---|---|
| `upi_adoption_index` | National UPI volume in the month of first order — proxy for digital payment maturity at time of acquisition |

</td>
</tr>
</table>

---

## 🤖 Clustering Approach

| Algorithm | Why We Use It |
|---|---|
| **KMeans** | Primary algorithm — fast, interpretable, works well on scaled tabular data |
| **Hierarchical (Agglomerative)** | Dendrogram helps visually confirm natural cluster count |
| **DBSCAN** | Detects outlier customers (anomalous spenders, bots, one-off bulk buyers) |

**Evaluation Metrics:**

```
Silhouette Score      → How well separated are the clusters? (higher = better)
Davies-Bouldin Index  → How compact and distinct are clusters? (lower = better)
Calinski-Harabasz     → Cluster density vs separation ratio (higher = better)
Elbow Curve           → Visual: where does adding more clusters stop helping?
```

---

## 👥 Expected Customer Personas

Based on typical D2C clustering results, you'll likely discover segments similar to:

<div align="center">

| Persona | Signal | Business Action |
|---|---|---|
| 🔴 **Power Buyers** | High frequency · high spend · low recency | VIP program · early product access |
| 🟡 **Discount Hunters** | Buys only during sales · medium frequency | Early sale access · flash deals |
| 🟢 **Loyal Explorers** | Consistent orders · high category diversity | Cross-sell campaigns · loyalty points |
| 🔵 **One-Time Visitors** | Single purchase · high recency · paid channel | Win-back email · second purchase incentive |
| ⚫ **At-Risk Customers** | Was frequent, now inactive | Re-engagement offers · feedback survey |

</div>

> *Actual personas depend on your data — these are illustrative starting points.*

---

## 📁 Project Structure

```
kshashtra-segmentation/
│
├── 📂 data/
│   ├── raw/kshashtra/          ← 9 raw CSV files from Kaggle
│   ├── raw/npci_upi/           ← NPCI monthly payment CSVs
│   ├── processed/              ← merged master customer table
│   └── enriched/               ← 15-feature matrix for clustering
│
├── 📂 notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_merging.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_eda.ipynb
│   ├── 05_clustering.ipynb
│   ├── 06_cluster_profiling.ipynb
│   └── 07_campaign_strategy.ipynb
│
├── 📂 models/
│   ├── kmeans_final.pkl
│   └── scaler.pkl
│
├── 📂 reports/
│   ├── figures/                ← exported charts
│   └── campaign_briefs.md      ← business output per segment
│
├── 📂 dashboard/
│   └── kshashtra_segments.pbix ← Power BI dashboard file
│
└── requirements.txt
```

---

## 🛠️ Tech Stack

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

</div>

---

## ⚡ Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/athhh07/kshashtra-segmentation.git
cd kshashtra-segmentation

# 2. Install dependencies
pip install -r requirements.txt

# 3. Download datasets from Kaggle links above
#    Place files in data/raw/kshashtra/ and data/raw/npci_upi/

# 4. Run notebooks in order (01 → 07)
jupyter notebook
```

---

## 👨‍💻 Developer

<div align="center">

**Atharva Desai**
B.Tech CSE (Data Science) · SSGBCOET Bhusawal

[![GitHub](https://img.shields.io/badge/GitHub-athhh07-181717?style=flat-square&logo=github)](https://github.com/athhh07)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/atharva-desai-3b24142a8)
[![Live App](https://img.shields.io/badge/RBI%20Alert%20Desk-Live-FF4B4B?style=flat-square&logo=streamlit)](https://rbi-alertdesk.streamlit.app/)

</div>

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer"/>

*Built to demonstrate end-to-end unsupervised ML on real Indian D2C data*

⭐ Star this repo if you found it useful
</div>
