# MLM Project 1 - Group 18  
**Unsupervised Learning Models on Import-Export Dataset using Python**

---

## PROJECT CONTENTS:
1. Project Information  
2. Description of Data  
3. Data Sampling  
4. Project Objectives | Problem Statements  
5. Analysis of Data  
6. Observations | Findings  
7. Managerial Insights | Recommendations  

---

## 1. Project Information  
**Title**: Data Exploration with Python using Pandas & Numpy Libraries  
**Prepared By**:  

- **Anirudh Gupta (055003)**  
- **Amitanshu Tiwari (055054)**  

**Group Number**: 18  

---

## 2. Description of Data  

**Data Source**: [Kaggle - Imports-Exports Dataset](https://www.kaggle.com/datasets/chakilamvishwas/imports-exports-15000)  

**Data Columns Description**:  

- **Transaction_ID**: Unique identifier for each trade transaction.  
- **Country**: Country of origin or destination for the trade.  
- **Product**: Product being traded.  
- **Import_Export**: Indicates whether the transaction is an import or export.  
- **Quantity**: Amount of the product traded.  
- **Value**: Monetary value of the product in USD.  
- **Date**: Date of the transaction.  
- **Category**: Category of the product (e.g., Electronics, Clothing, Machinery).  
- **Port**: Port of entry or departure.  
- **Customs_Code**: Customs or HS code for product classification.  
- **Weight**: Weight of the product in kilograms.  
- **Shipping_Method**: Method used for shipping (e.g., Air, Sea, Land).  
- **Supplier**: Name of the supplier or manufacturer.  
- **Customer**: Name of the customer or recipient.  
- **Invoice_Number**: Unique invoice number for the transaction.  
- **Payment_Terms**: Terms of payment (e.g., Net 30, Net 60, Cash on Delivery).  

**Data Type**: Panel Data (Longitudinal Data)  

---

## 3. Data Sampling  
From the dataset containing 15,000 values, a sample of 5,001 entries was taken (referred to as `ag03_sample`).  

**Data Variables**:  

- **Index Variables**: `Transaction_ID`, `Invoice_Number`  
- **Categorical Variables**:  
  - **Nominal Variables**: Country, Product, Import_Export, Category, Port, Shipping_Method, Supplier, Customs_Code, Customer  
  - **Ordinal Variable**: Payment_Terms  
- **Non-Categorical Variables**: Quantity, Value, Weight  

---

## 4. Project Objectives  
1. Perform Unsupervised Machine Learning.  
2. Segment the dataset using Clustering Algorithms.  
3. Identify the appropriate number of clusters.  
4. Determine segment characteristics.  

---

## 5. Exploratory Data Analysis  

### 5.1. Data Preprocessing  
- No missing values were found.  
- **Encoding**: Ordinal Encoder was used for categorical variables.  
- **Scaling**: Min-Max Scaler was applied.  

### 5.2. Descriptive Statistics  
#### Non-Categorical Variables:  
- **Central Tendency**: Minimum, Maximum, Mean, Median, Mode, Percentile  
- **Dispersion**: Range, Standard Deviation, Skewness, Kurtosis, Correlation Matrix  
- **Composite Measures**: Coefficient of Variation, Confidence Interval  

#### Categorical Variables:  
- Count, Frequency, Proportion, Minimum, Maximum, Mode, Rank  

### 5.3. Data Visualization  
- Subplots: Bar charts, Heatmaps, Histograms, Violin Plots, and Correlation Matrices  

### 5.4. Inferential Statistics  
#### Categorical Variables:  
- **Nominal | Ordinal**: Chi-Square Test of Homogeneity  

#### Non-Categorical Variables:  
- **Normality Tests**: Shapiro-Wilk, Kolmogorov-Smirnov, Anderson-Darling, Jarque-Bera  
- **Correlation Test**: t-test  

### 5.5. Machine Learning Models  
1. **Dimensionality Reduction**:  
   - Principal Component Analysis (PCA)  
2. **Clustering Algorithms**:  
   - K-Means (KM), DBSCAN, BIRCH  

### 5.6. Model Performance Metrics  
- **Evaluation Metrics**: Silhouette Coefficient, Davies-Bouldin Index  
- **Model Run Statistics**: Time Taken, Memory Used  

---

## 6. Observations and Findings  

### 6.1. Nature of Data  
- No missing values.  
- **Categorical Variables**: Encoded using Ordinal Encoder.  
- **Scaling**: Min-Max scaling applied to numeric data.  
- **Outliers**: Box plots revealed potential outliers, which were retained for analysis.  

### 6.2. Clustering Analysis  
#### Model Selection:  
- K-Means was preferred due to superior performance compared to DBSCAN and BIRCH.  
- DBSCAN resulted in fewer than two clusters, making it unsuitable.  

#### Number of Clusters:  
- **Optimal Clusters for K-Means**: 4  
  - **Silhouette Score**: 0.4038  
  - **Davies-Bouldin Index**: 0.7775  

#### Cluster Characteristics:  
- **Cluster 1**: Low to moderate Quantity and Weight (Low-Volume Transactions).  
- **Cluster 2**: Moderate to high Quantity, moderate Weight (Mid-Volume Transactions).  
- **Cluster 3**: Low Quantity, high Weight (Bulky Product Transactions).  
- **Cluster 4**: High Quantity, low Weight (High-Volume, Low-Weight Transactions).  

---

## 7. Managerial Insights and Recommendations  

### 7.1. Preprocessing  
- **Missing Data**: No treatment required.  
- **Encoding**: Ordinal encoding was effective.  
- **Scaling**: Min-Max scaling addressed scale differences.  

### 7.2. Clustering Insights  
- **Cluster Utilization**:  
  - Targeted marketing campaigns for specific customer segments.  
  - Inventory optimization based on product categories.  
  - Risk assessment and fraud detection through unusual pattern identification.  
