# K-Means and Hierarchical Clustering for Online Retail Data Analysis

## Project Overview
This project utilizes the **Online Retail** dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail), containing transactional data from a UK-based online retailer between **01/12/2010** and **09/12/2011**. The dataset includes various products, mainly all-occasion gifts, with many customers being wholesalers. The goal is to perform **customer segmentation** using **K-Means** and **Hierarchical Clustering** to group customers based on purchasing behavior, thereby enhancing customer understanding and enabling targeted marketing strategies.

## Steps Involved

1. **Data Understanding**: Initially explored the data to assess its structure, column types, and general characteristics.
2. **Data Cleaning**: Removed rows with missing `CustomerID` values to retain only complete transaction records.
3. **Feature Engineering**: Created an `amount` column representing the total transaction value for each item. Calculated the RFM metrics—**Recency** (number of days since the last purchase), **Frequency** (number of transactions), and **Monetary** (total transaction value) to quantify customer purchase behavior.
4. **Data Preparation**: Standardized the RFM metrics using scaling to ensure that all features contributed equally to clustering.
5. **Modeling**: Applied **K-Means Clustering** and **Hierarchical Clustering** on the scaled RFM data to generate customer segments.
6. **Analysis and Recommendations**: Analyzed the clusters and provided recommendations based on the insights derived from the customer segmentation.

## Clustering Techniques Used

### K-Means Clustering
K-Means is a partition-based clustering technique that aims to minimize the distance between data points and their respective cluster centroids. 

- **Advantages**:
  - Efficient and scalable, especially suitable for large datasets.
  - Straightforward implementation and easy interpretability, with clearly defined clusters.
- **Disadvantages**:
  - Requires pre-specification of the number of clusters, which can be challenging to determine accurately.
  - Sensitive to outliers, as they can distort the positioning of centroids.

- **When to Use**: 
  - K-Means is ideal when clusters are approximately spherical or evenly sized, and the dataset is large. It is especially useful when computational efficiency is a priority.

### Hierarchical Clustering
Hierarchical Clustering is an agglomerative approach that begins with each observation in its own cluster and successively merges clusters based on specified criteria.

- **Types**:
  - **Single Linkage**: Clusters are merged based on the minimum distance between points, which can result in elongated, chain-like clusters.
  - **Complete Linkage**: Clusters are merged based on the maximum distance, resulting in compact clusters.
- **Advantages**:
  - Does not require the number of clusters to be specified in advance.
  - Provides a dendrogram, offering a visual representation of the hierarchical structure of clusters.
- **Disadvantages**:
  - Less scalable for large datasets due to high computational costs.
  - Sensitive to noise and outliers.

- **When to Use**: 
  - Hierarchical clustering is beneficial for smaller datasets with an unknown number of clusters and where visualization of the hierarchy between clusters is useful.

## Data Preparation

### Data Cleaning
- Removed rows with missing `CustomerID` values to focus on complete transaction data.
- Created a new `amount` column by multiplying `Quantity` with `UnitPrice` to get the transaction value per item.

### Feature Engineering (RFM Metrics)
- Calculated **Recency** as the number of days since the customer’s last purchase.
- Counted the **Frequency** as the number of transactions per customer.
- Summed the **Monetary** value of transactions for each customer.

### Data Scaling
Standardized the RFM metrics to ensure equal weighting of features in clustering.

## Modeling

### 1. K-Means Clustering
- Used the **Elbow Method** to determine the optimal number of clusters by plotting the Sum of Squared Distances (SSD).
- Performed **Silhouette Analysis** to validate the quality of clusters, with silhouette scores closer to 1 indicating higher intra-cluster similarity and better-defined clusters.

### 2. Hierarchical Clustering
- Implemented **Single Linkage** and **Complete Linkage** clustering methods and visualized the results with dendrograms, which provided insight into the hierarchical structure and allowed for the selection of an optimal number of clusters.

## Final Analysis
- Used box plots to examine the distribution of **recency**, **frequency**, and **monetary** values across clusters to understand customer characteristics within each segment for both K-Means and Hierarchical clustering outputs.

## Conclusion and Recommendations
The clustering analysis provided distinct customer segments based on purchasing behavior, which can be leveraged for:

- **Targeted Marketing**: Tailor promotional strategies to specific customer segments.
- **Customer Retention**: Identify and prioritize high-value customers for retention efforts.
- **Product Strategy**: Optimize product offerings and inventory based on customer needs and segment preferences.

### Future Scope
- Experiment with additional clustering algorithms like **DBSCAN** for potential improvements, especially for non-spherical clusters.
- Explore further feature engineering to provide even more granular segmentation insights.

This analysis offers valuable insights into customer purchasing behavior, empowering data-driven decisions to enhance customer engagement and business growth.
