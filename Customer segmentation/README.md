# 🎯 Customer Segmentation Using Retail Dataset

## 📌 Project Overview

This project focuses on customer segmentation using a retail dataset sourced from Kaggle. The goal is to analyze transactional data to group customers based on their purchasing behavior. By segmenting customers, businesses can better understand their customers' needs, tailor marketing strategies, and optimize product offerings.

---

## 📂 Dataset Description

The dataset contains transactional data with the following columns:

- `InvoiceNo`: Unique identifier for each transaction
- `StockCode`: Unique identifier for the item purchased
- `Description`: Description of the item
- `Quantity`: Number of items purchased
- `InvoiceDate`: Date and time of the transaction
- `UnitPrice`: Price per item
- `CustomerID`: Unique identifier for the customer
- `Country`: Country of the customer

---

## 🧹 Data Cleaning & Preprocessing

### Handling Missing Values

- The `CustomerID` column had missing values. These were handled by removing rows with missing customer information.
- We also checked for and handled any discrepancies in the dataset, such as negative quantities or prices, which were corrected or removed.

### Data Transformation

- We transformed the `InvoiceDate` to extract year, month, and day features, providing deeper insights into purchasing trends.
- We also converted categorical variables like `Country` into numerical values using label encoding for easier modeling.

---

## 🧩 Feature Engineering

We engineered new features to improve model performance:

- `TotalSpend = Quantity * UnitPrice`: Total spending per transaction.
- `PurchaseFrequency`: Count of transactions per customer to assess customer loyalty.
- `AverageTransactionValue`: The average amount spent per transaction for each customer.

These features were added to help understand the purchasing patterns of customers and their potential segmentation.

---

## ⚙️ Modeling & Evaluation

### 🔹 K-Means Clustering

We applied K-Means clustering to segment customers based on their purchasing behavior. The number of clusters was determined using the Elbow Method, which suggested an optimal number of clusters for the dataset.

#### Model Results

- **Cluster 0**: Loyal Customers
- **Cluster 1**: At Risk
- **Cluster 2**: Potential Loyalists
- **Cluster 3**: Big Spenders

These segments were mapped according to the following customer behavior patterns:

- **Loyal Customers**: Customers who make frequent, consistent purchases.
- **At Risk**: Customers who have not made a purchase in a while or whose spending has decreased.
- **Potential Loyalists**: Customers with high potential for loyalty, based on purchasing patterns.
- **Big Spenders**: Customers who make large purchases infrequently.

---

## 🧑‍💼 Why the Models Are Suitable

K-Means clustering is suitable for this project as it helps in grouping customers who share similar purchasing patterns. These clusters allow businesses to identify high-value customers and tailor their marketing efforts accordingly.

---

## 📊 Technical Stack

- **Languages**: Python
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `streamlit`
- **Techniques Used**: Data preprocessing, feature engineering, K-Means clustering, data visualization

---

## 📈 Future Improvements

- Try different clustering algorithms, such as DBSCAN or Agglomerative Clustering, to compare results.
- Incorporate additional features such as customer demographics to refine the segmentation.
- Deploy the model using a web framework like Flask or Streamlit for real-time customer segmentation.

---

## 🖥️ Streamlit Dashboard for Customer Segmentation

To provide an interactive and user-friendly experience, a **Streamlit dashboard** was built to visualize the results of customer segmentation. This dashboard allows users to interactively explore the customer segments, adjust the number of clusters, and view a PCA-based visualization of the clusters.

Users can:
- Adjust the number of clusters to explore how the segmentation changes.
- View a 2D PCA visualization of the clusters, offering clear insights into customer segmentation.
- Identify key customer segments such as "Loyal Customers," "At Risk," "Potential Loyalists," and "Big Spenders."

You can explore the **Customer Segmentation Dashboard** through the following link:

🔗 [Explore the Dashboard](https://cluster-8bewupbem8rqdmgeryzy7r.streamlit.app/)
