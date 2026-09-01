# 🛍️ Kshashtra — Indian D2C Customer Segmentation

<p align="center">

<img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python" />
<img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas" />
<img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn" />
<img src="https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi" />
<img src="https://img.shields.io/badge/K--Means-Clustering-00A98F?style=for-the-badge" />

</p>

<p align="center">
  <b>Turning D2C customer behavior into actionable customer segments.</b>
</p>

---

## 📌 Project Overview

**Kshashtra Customer Segmentation** is an end-to-end **Customer Analytics & Unsupervised Machine Learning project** designed to identify meaningful customer groups from e-commerce transactional, behavioral, engagement, and payment-related data.

The project combines multiple datasets to create a unified customer-level analytical dataset and applies clustering techniques to discover different customer behaviors.

The final segmentation is transformed into an interactive **Power BI dashboard** that helps businesses understand:

- 👥 Who their customers are
- 💰 Which customers generate the most revenue
- 🛒 How customers interact with the website
- 🔄 Which customers have repeat-purchase potential
- 📉 Which customers show low engagement
- 🎯 Where marketing and retention efforts should be focused

---

## 🎯 Business Problem

D2C businesses often have thousands of customers with very different purchasing behaviors.

Treating every customer in the same way can lead to:

- Inefficient marketing campaigns
- Poor customer retention
- Missed high-value customers
- Unnecessary discounts
- Low conversion from existing traffic
- Difficulty identifying customers with repeat-purchase potential

### Objective

> **Segment customers based on their purchasing behavior, engagement, value, diversity, and loyalty — and translate those segments into actionable business strategies.**

---

## 📊 Dataset

The project primarily uses the **Kshashtra E-commerce Store Marketing and Sales Dataset**, containing multiple interconnected datasets related to customers, orders, products, website activity, inventory, purchasing, and marketing.

### 🛍️ Kshashtra E-commerce Dataset

Source: Kaggle

**Kshashtra — E-commerce Store Marketing and Sales Dataset**

https://www.kaggle.com/datasets/kushsheth/kshashtra-ecommerce-store-martking-and-sales

The dataset includes information related to:

- Customers
- Orders
- Order line items
- SKU catalog
- Website sessions
- Website activity
- Inventory
- Purchase orders
- Marketing campaigns

### 💳 Digital Payment Dataset

A monthly digital-payment dataset was also explored to provide broader payment-behavior context.

Source: Kaggle

https://www.kaggle.com/datasets/nilesh2042/monthly-metrics

> **Note:** The payment dataset contains aggregate monthly metrics rather than individual customer-level transactions.

---

## 🔄 Project Workflow

```text
Raw Data
   ↓
Data Loading & Understanding
   ↓
Data Cleaning
   ↓
Data Integration
   ↓
Customer-Level Aggregation
   ↓
Feature Engineering
   ↓
Feature Selection
   ↓
Feature Scaling
   ↓
Clustering
   ↓
Model Evaluation
   ↓
Customer Segmentation
   ↓
Business Personas
   ↓
Power BI Dashboard
