# Supply Chain End-to-End Analysis

## Overview
An end-to-end data analysis project on a real-world supply chain dataset covering delivery performance, profitability, bottleneck detection, and late delivery risk prediction using Machine Learning.

The project answers key business questions:
- What percentage of orders are delivered late, and what is the financial impact?
- Which regions, shipping modes, and departments cause the most delays?
- Can we predict whether an order will be delivered late before it ships?

---

## Dataset
**DataCo Supply Chain Dataset**  
Source: [Kaggle - DataCo Smart Supply Chain](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)  
Size: ~180,000 orders across multiple regions, product categories, and shipping modes.

---

## Technologies Used
- Python 3.x
- Pandas — data manipulation and feature engineering
- NumPy — numerical operations
- Matplotlib & Seaborn — data visualization
- Scikit-learn — machine learning (Random Forest Classifier)
- Imbalanced-learn (SMOTE) — handling class imbalance

---

## Project Workflow

### 1. Data Cleaning
- Dropped 32 irrelevant or redundant columns (customer PII, IDs, etc.)
- Removed cancelled orders from analysis
- Parsed order and shipping date columns to datetime format

### 2. Feature Engineering
- **Order Processing Time** — actual days from order to shipment
- **Delay** — actual processing time minus scheduled shipment days
- **Is_Delayed** — binary flag for late deliveries
- **Profitability Flag** — Profit / Loss / Break-even per order
- **Temporal features** — order month, day of week, hour of day

### 3. Business KPIs
- Total Orders, Late Deliveries count
- On-Time Delivery % and Late Delivery %
- Total Profit from all orders
- Total financial loss attributed to delayed orders
- 90th percentile delay in days

### 4. Bottleneck Detection
Identified high-delay segments across:
- Order Region
- Customer Segment
- Shipping Mode
- Order Status
- Department Name

### 5. Temporal Analysis
- Delay trend by month (identified peak delay months)
- Delay % by day of week
- Delay % by hour of day

### 6. Machine Learning — Late Delivery Risk Prediction
- **Target Variable:** `Late_delivery_risk`
- **Features:** Shipping mode, scheduled days, category, region, customer segment, department, temporal features
- **Encoding:** Frequency encoding for all categorical columns
- **Class Balancing:** SMOTE applied on training data
- **Model:** Random Forest Classifier
- **Evaluation:** Accuracy, Precision, Recall, Classification Report

---

## Key Findings
- A significant portion of orders are delivered late, with the highest delay concentration in specific regions and shipping modes.
- Standard Class shipping shows the highest delay percentage among shipping modes.
- Delay has a measurable negative impact on per-order profitability.
- Random Forest Classifier achieves strong accuracy in predicting late delivery risk before shipment.

---

## How to Run
```bash
# 1. Clone the repository
git clone https://github.com/vpsingh48/end-to-end-Supply-Chain.git

# 2. Navigate to the project folder
cd end-to-end-Supply-Chain

# 3. Install required libraries
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

# 4. Download the dataset from Kaggle and place it in the project folder:
# DataCoSupplyChainDataset.csv

# 5. Open the notebook
jupyter notebook supply_chain_end_to_end_.ipynb
```

---

## Project Structure
