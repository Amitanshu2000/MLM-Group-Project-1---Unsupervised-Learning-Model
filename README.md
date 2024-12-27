MLM Project 1 - Group 18
Unsupervised Learning Models on Import-Export Dataset using Python
PROJECT CONTENTS:
Project Information
Description of Data
Data Sampling
Project Objectives | Problem Statements
Analysis of Data
Observations | Findings
Managerial Insights | Recommendations
1. Project Information
Title: Data Exploration with Python using Pandas & Numpy Libraries
Prepared By:

Anirudh Gupta (055003)

Amitanshu Tiwari (055054)

Group Number: 18

2. Description of Data
Data Source: https://www.kaggle.com/datasets/chakilamvishwas/imports-exports-15000

A live link is used in the dataset

Data Columns Description:

Transaction_ID: Unique identifier for each trade transaction.
Country: Country of origin or destination for the trade.
Product: Product being traded.
Import_Export: Indicates whether the transaction is an import or export.
Quantity: Amount of the product traded.
Value: Monetary value of the product in USD.
Date: Date of the transaction.
Category: Category of the product (e.g., Electronics, Clothing, Machinery).
Port: Port of entry or departure.
Customs_Code: Customs or HS code for product classification.
Weight: Weight of the product in kilograms.
Shipping_Method: Method used for shipping (e.g., Air, Sea, Land).
Supplier: Name of the supplier or manufacturer.
Customer: Name of the customer or recipient.
Invoice_Number: Unique invoice number for the transaction.
Payment_Terms: Terms of payment (e.g., Net 30, Net 60, Cash on Delivery).
Data Type: Since the dataset contains multiple entities (countries) and records data over time, this is an example of Panel Data (also called longitudinal data).

Data Variables:

All non-null Variables
Numbers:
Integer Variables: 3 (Quantity, Customs_Code, Invoice_Number)
Float (Decimal) Variables: 2 (Value, Weight)
Text: 9 (Country, Product, Import_Export, Category, Port, Shipping_Method, Supplier, Customer, Payment_Terms)
DateTime: 1 (Date)
3. Data Sampling
From the dataset containing 15,000 values, a sample of 5001 entries was taken. The dataset sample (now referred to as ag03_sample) was taken into account for further exploration.

Data Variables:
Index Variables: 'Transaction_ID', 'Invoice_Number'
Categorical Variables:
Nominal Variables: Country, Product, Import_Export, Category, Port, Shipping_Method, Supplier, Customs_Code, Customer
Ordinal Variable: Payment_Terms
Non-Categorical Variables: Quantity, Value, and Weight
4. Project Objectives
Perform Unsupervised Machine Learning
Segmentation of dataset using Unsupervised Machine Learning Clustering Algorithms
Identification of appropriate number of segments or clusters
Determination of segment or cluster characteristics
5. Exploratory Data Analysis
5.1. Data Preprocessing:
The data has no missing values, hence no missing data treatment was performed.
For Encoding, Ordinal Encoder was used.
For Scaling, Min-Max Scaler was used.
5.2. Descriptive Statistics
Non-Categorical Variables:

Measures of Central Tendency: Minimum, Maximum, Mean, Median, Mode, Percentile
Measures of Dispersion: Range, Standard Deviation, Skewness, Kurtosis, Correlation (Matrix)
Composite Measure: Coefficient of Variation, Confidence Interval
Categorical Variables:

Count, Frequency, Proportion, Minimum, Maximum, Mode, Rank
5.3. Data Visualization
Various subplots were used such as Bar, Heatmaps, Histograms, Violin Plots and Correlation Matrices.
5.4. Inferential Statistics
Categorical Variable (Nominal | Ordinal):
Test of Homogeneity (Chi-sq)
Non-Categorical Variable:
Test of Normality (Shapiro-Wilk, Kolmogorov-Smirnov, Anderson-Darling, Jarque-Bera)
Test of Correlation (t)
5.5. Machine Learning Models
Dimensionality Reduction: Records Clustering: K-Means (KM), DBSCAN, BIRCH
Dimensionality Reduction: Principal Component Analysis (PCA)
5.6. Model Performance Metrics
Silhouette Coefficient, Davies-Bouldin Index to evaluate the model performance
Model Run Statistics:
Time Taken
Memory Used
6. Observations and Findings
6.1. Nature of Data
Missing Data: The dataset contained no missing values.
Non-Numeric Categorical Data: Categorical variables (e.g., Country, Product) were encoded using ordinal encoding.
Scales and Outliers:
Non-categorical numeric data (Quantity, Value, Weight) were scaled using Min-Max scaling.
Box plots revealed potential outliers, but they were not removed as they might hold valuable information.
6.2. Unsupervised Machine Learning: Clustering
Clustering Model Selection:
K-Means was chosen as the preferred clustering model based on its superior performance metrics and run statistics compared to DBSCAN and Birch.
DBSCAN resulted in fewer than two clusters, making it unsuitable for segmentation.
Number of Clusters:
For K-Means, an optimal cluster number of 4 was determined based on:
Highest Silhouette Score: 0.4038
Lowest Davies-Bouldin Index: 0.7775
Niche Clusters:
While distinct clusters were observed, no specific niche clusters were identified in this analysis.
Distinguishing Features:
Each cluster exhibited unique characteristics based on the distribution of Quantity and Weight, potentially indicating different product types or customer segments.
7. Managerial Insights and Recommendations
7.1. Preprocessing of Data
Missing Data: No specific treatment is necessary due to the absence of missing data.
Encoding: Ordinal encoding proved effective for categorical variables.
Scaling: Min-Max scaling was appropriate to address potential scale differences.
Data Split: A 70:30 split for training and testing sets would be appropriate for future supervised learning tasks.
7.2. Unsupervised Machine Learning: Clustering
Purpose of Segmentation:
The clustering analysis was conducted to identify distinct customer segments or product categories based on their purchasing behavior or characteristics.
Cluster Characteristics and Naming:
Cluster 1: Characterized by low to moderate Quantity and Weight.
Suggested Name: Low-Volume Transactions
Cluster 2: Moderate to high Quantity with moderate Weight.
Suggested Name: Mid-Volume Transactions
Cluster 3: Low Quantity and high Weight.
Suggested Name: Bulky Product Transactions
Cluster 4: High Quantity and low Weight.
Suggested Name: High-Volume, Low-Weight Transactions
Potential Use of Clusters:
Targeted marketing campaigns can be tailored to specific customer segments.
Inventory management can be optimized based on product category characteristics.
Risk assessment and fraud detection can be enhanced by identifying unusual purchasing patterns.
