# Retail Analytics & Return Prediction

## Business Problem
Product returns create operational and financial costs for retail businesses.
This project analyzes transaction-level data to identify revenue drivers,
customer behavior patterns, and assess whether returns can be predicted
using available transactional features.

## Data Overview
Multiple datasets were integrated into a single analytical table:
- Customers
- Products
- Stores
- Sales transaction

Primary key uniqueness and schema consistency were verified prior to merging.

## Data Preparation & Validation
- Verified data types across all source tables
- Confirmed uniqueness of primary keys
- Identified non-positive quantities and prices
- Retained transactions sold below cost to preserve business context
- Converted date fields to datetime format

## Feature Engineering
- Revenue calculated as: quantity × list_price × (1 − discount)
- Profit calculated where cost data was available
- Aggregated revenue by customer, product, store, and region

## Exploratory Insights
- Revenue is well distributed across stores and regions
- Top 10% of customers generate ~25% of total revenue
- No strong dependence on a small customer group
- Certain products exhibit higher return rates

## Machine Learning: Return Prediction
A baseline classification model was built to predict whether a transaction
would be returned.

**Approach**
- One-hot encoding of categorical variables
- Train-test split with stratification due to class imbalance
- Random Forest classifier with class weighting
- Evaluation focused on recall for returned transactions

## Results & Limitations
Despite class weighting, recall for returned transactions remained limited.
This indicates that transactional features alone are insufficient to
reliably predict returns.

## Business Recommendations
- Enrich data with customer purchase history
- Include product quality or defect indicators
- Incorporate behavioral or post-purchase feedback

## Tools & Technologies
- Python 
- Scikit-learn
- Jupyter Notebook
