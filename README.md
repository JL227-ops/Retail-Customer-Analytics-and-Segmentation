# Retail Customer Segmentation and Pattern Discovery Using Data Mining Techniques
### Data Mining  
### Final Deliverable (M4)
---

# Project Overview

This project analyzes customer purchasing behavior using the UCI Online Retail dataset from the UCI Machine Learning Repository. The dataset contains 541,909 transaction records from a UK-based online retailer between 2010 and 2011.

The goal of the project is to discover meaningful customer behavior patterns using multiple data mining techniques and generate useful business insights related to customer segmentation, recommendation systems, customer retention, and anomaly detection.

This analysis emphasizes:
- pattern discovery
- customer behavior interpretation
- probabilistic analysis
- anomaly interpretation
- business meaning of discovered patterns

The project combines clustering, association rule mining, probabilistic analysis, dimensionality reduction, and anomaly detection into a single customer analytics workflow.

---

# Discovery Questions

The project focuses on three main discovery questions:

## 1. Which products are frequently purchased together?
Addressed using:
- Apriori Association Rule Mining

Main findings:
- Tea cup and gift-related products frequently appeared together
- Strong lift values suggested meaningful product relationships
- Results support recommendation systems and cross-selling strategies

---

## 2. Are there natural customer segments based on purchasing behavior?
Addressed using:
- RFM Feature Engineering
- K-Means Clustering
- PCA Visualization
- Decision Tree Interpretation
- Naive Bayes Probabilistic Analysis

Main findings:
- Four major customer groups were identified:
  - VIP / Elite customers
  - Loyal high-value customers
  - Regular customers
  - Inactive customers

- VIP customers showed:
  - very high purchase frequency
  - very recent purchasing behavior
  - extremely high spending levels

- Inactive customers showed:
  - low spending
  - long inactivity periods
  - possible customer churn risk

---

## 3. Are there anomalous customers or unusual purchasing behaviors?
Addressed using:
- Isolation Forest
- Local Outlier Factor (LOF)

Main findings:
- High-spending and high-frequency customers were identified as anomalies
- Some anomalies overlapped with VIP customer groups
- Other anomalies represented irregular purchasing behaviors or possible wholesale buyers

An important analytical finding of the project is that:
- VIP customers and anomalies are partially overlapping rather than identical populations

This suggests that:
- clustering identifies stable customer groups
- anomaly detection identifies statistically unusual behavior patterns

---

# Dataset Information

## Dataset
- Online Retail Dataset
- Source: UCI Machine Learning Repository
- Transactions: 541,909
- Time Range: 2010–2011
- Domain: Online Retail

## Main Features
- InvoiceNo
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- CustomerID
- Country

---

# Data Preprocessing

Several preprocessing steps were applied before analysis:

- Removed missing CustomerID values
- Removed negative quantities and return transactions
- Removed invalid prices
- Removed duplicate transactions when necessary
- Created TotalPrice feature

---

# Feature Engineering

## RFM Features

The project uses RFM customer analytics features:

- **Recency**  
  Days since the customer’s last purchase

- **Frequency**  
  Number of purchases made by the customer

- **Monetary**  
  Total spending amount of the customer

These features provide a compact representation of customer purchasing behavior.

---

# Techniques Used

| Technique | Purpose |
|---|---|
| Apriori | Market basket analysis |
| K-Means | Customer segmentation |
| PCA | Cluster visualization |
| Decision Tree | Cluster interpretation |
| Naive Bayes | Probabilistic analysis |
| Isolation Forest | Anomaly detection |
| LOF | Anomaly comparison |

---

# Key Results

## Customer Segmentation
Four major customer groups were identified:

| Cluster | Description |
|---|---|
| Cluster 2 | VIP / Elite customers |
| Cluster 3 | Loyal high-value customers |
| Cluster 0 | Regular customers |
| Cluster 1 | Inactive customers |

Cluster 2 customers showed:
- average Recency ≈ 7 days
- average Frequency ≈ 82 purchases
- average Monetary ≈ £127,338

These customers may represent:
- VIP customers
- wholesale buyers
- corporate accounts

---

## PCA Visualization
PCA improved cluster separation and produced a clearer visualization of customer structure.

---

## Decision Tree Interpretation
The decision tree identified:
- Frequency and Monetary as the strongest indicators of high-value customers
- Recency as a major indicator of inactive customers

Several interpretable business rules were discovered from the tree structure.

---

## Naive Bayes Probabilistic Analysis
Naive Bayes was used as a probabilistic interpretation tool rather than a pure prediction model.

Main findings:
- VIP customers strongly associated with high Frequency and Monetary values
- Inactive customers associated with high Recency values
- Approximately 87% probabilistic agreement with original cluster structure

---

## Anomaly Detection
Isolation Forest and LOF identified customers with:
- extremely high spending
- unusually high purchase frequency
- irregular purchasing behavior

Important finding:
- VIP customers and anomalies partially overlap
- not all anomalies are VIP customers
- not all VIP customers are strong anomalies

---

# Business Interpretation

The findings provide several useful business insights:

- VIP customers contribute disproportionately large revenue
- Loyal customers support long-term profitability
- Inactive customers may indicate churn risk
- Association rules support recommendation systems
- Anomaly detection may identify wholesalers or rare customer behaviors

Potential applications include:
- recommendation systems
- personalized marketing
- customer retention
- cross-selling
- customer value analysis

---

# Critical Assessment

## Validity
- Multiple methods identified similar customer behavior patterns
- PCA improved cluster visualization
- K-Means clustering was tested with multiple random seeds
- Clustering and anomaly detection supported similar findings

## Limitations
- Dataset heavily dominated by UK customers
- VIP customer class imbalance
- Parameter sensitivity in clustering and anomaly detection
- Missing CustomerID removal may introduce bias

## Ethical Considerations
- Customer privacy awareness
- Responsible use of customer analytics
- Dataset bias considerations
- Fairness in customer targeting strategies

---

# Repository Structure

```text
CS4412-Retail-Analysis-Project-JL/
│
├── data/
│   └── raw/
│
├── docs/
│   ├── M1-Proposal/
│   ├── M2-Initial_Implementation/
│   ├── CS4412_JIA_LIU_M3/
│   └── CS4412_JIA_LIU_M4/
│
├── notebooks/
│   ├── M1_Proposal.ipynb
│   ├── M2_Initial_Implementation.ipynb
│   ├── M3_Complete_Implementation.ipynb
│   └── M4_Deliverable.ipynb
│
├── figures/
│   ├── M2/
│   ├── M3/
│   └── M4/
│
├── README.md
├── requirements.txt
└── .gitignore
```

### How to Run
### Requirements
   Install dependencies:
```bash
pip install -r requirements.txt
```
## Main Libraries
pandas
numpy
scikit-learn
matplotlib
seaborn
mlxtend

## Run Notebook
Open the notebooks folder and run by Google Colab:
M4_Deliverable.ipynb

## Future Work
Possible future improvements include:
DBSCAN comparison
FP-Growth comparison
hierarchical clustering
time-series customer analysis
stronger validation methods
improved anomaly detection tuning
additional demographic or seasonal analysis

## Technologies Used
Python
Pandas
NumPy
Scikit-learn
Matplotlib
Seaborn
MLxtend
Git
Google Colab

## References
1.UCI Machine Learning Repository — Online Retail Dataset
2.Mohammed J. Zaki and Wagner Meira Jr., Data Mining and Machine Learning, Cambridge University Press, 2020
3.Jure Leskovec, Anand Rajaraman, and Jeffrey Ullman, Mining of Massive Datasets, Cambridge University Press, 2014
3.Charu C. Aggarwal, Outlier Analysis, Springer, 2016

## Author
Jia Liu  
CS 4412 – Data Mining  
Kennesaw State University
