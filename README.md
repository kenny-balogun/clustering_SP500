# Segmenting Financial Markets: A Clustering Approach to the S&P 500 Index  

## Overview  

Financial markets are complex, and identifying patterns within them can be challenging.  
This project applies **unsupervised machine learning** to the **S&P 500 Index dataset**, using clustering techniques to segment the market into **distinct patterns**.  

By leveraging **K-Means and Agglomerative Clustering**, this study provides insights into **market conditions, risk management, and portfolio optimization**—helping investors and analysts make data-driven financial decisions.  

## Objectives  

- Use **K-Means and Agglomerative Clustering** to uncover **hidden patterns** in the S&P 500 dataset.  
- Identify different **market conditions** based on historical financial indicators.  
- Provide **data-driven insights** for **investment strategies and risk management**.  

## Dataset  

The dataset, sourced from **Datahub**, consists of **S&P 500 index data from 1870 to 2023**. It contains **1,833 observations** and **10 financial features**, including:  

-  **Date**
-  **S&P 500 Index Level**  
- **Dividends**  
- **Earnings**  
- **Consumer Price Index (CPI)**  
- **Long-Term Interest Rates**  
- **Real Price & Real Earnings**  
- **PE10 - Cyclically Adjusted PE Ratio (CAPE)**  

### Ethical Considerations  

- **Publicly Available Data**: The dataset is licensed under **Open Data Commons**, ensuring legal and ethical usage.  

## Exploratory Data Analysis (EDA)  

Key insights from the analysis:  

- **Missing Data Handling**:  
  - 0 values in earnings and dividends were converted to nulls and dropped (only 0.16% missing).  
  - **PE10 values were missing for the first 10 years** and were interpolated using **linear regression**.  
- **Feature Correlations**:  
  - **S&P 500 levels are positively correlated with earnings, dividends, and CPI**.  
  - **Negative correlation between S&P 500 and long-term interest rates**.  
- **Market Trends**:  
  - All numerical features show an **upward trend over time** except for **long-term interest rates**.  

## Data Preprocessing  

- **Handling Duplicates**: No duplicates found.  
- **Dropping Irrelevant Features**: The **date column** was removed as it was not needed for clustering.  
- **Feature Scaling**: Standardized all numeric features using **StandardScaler** to normalize values.  

## Clustering Models  

Two clustering algorithms were implemented:  

### **1. K-Means Clustering**  

- **Optimal Clusters:** Determined using the **Elbow Method (k=4)**.  
- **Silhouette Score:** **0.54**, indicating **well-separated clusters**.  
- **Principal Component Analysis (PCA)** was applied for **2D visualization** of clusters.  

### **2. Agglomerative Clustering**  

- **Dendrogram Analysis** was used to find the optimal number of clusters (**k=4**).  
- **Ward’s Linkage** was selected to **minimize intra-cluster variance**.  
- **Silhouette Score:** **0.535**, slightly lower than K-Means but provided a **hierarchical view** of clusters.  

## Cluster Interpretations  

**Cluster 0: Low Market Activity**  
- Very low S&P 500, earnings, and dividends.  
- Moderate-low interest rates and CPI.  
- Represents **economic downturn periods** (e.g., Great Depression).  

**Cluster 1: Economic Boom and Bull Markets**  
- Extremely high S&P 500, earnings, and dividends.  
- Low interest rates and high CPI.  
- Represents **strong bull markets** with **high investment opportunities**.  

**Cluster 2: Transition Periods**  
- Low-moderate S&P 500 and earnings.  
- Very high interest rates, moderate CPI.  
- Represents **inflation control phases** and **recovery periods**.  

**Cluster 3: Stable Growth**  
- Moderate-high S&P 500 and earnings.  
- Balanced interest rates and CPI.  
- Represents **long-term stable economic growth**.  

## Business Implications  

- **Market Segmentation:** Clustering allows **investors to categorize market conditions** into distinct phases.  

- **Risk Management:** Identifying clusters helps predict **periods of volatility and stability**, enabling better risk assessment.  

- **Portfolio Optimization:** Investors can **adjust investment strategies** based on historical patterns in each cluster.  

## Actionable Recommendations  

- **Cluster 0:** Hedge against stagnation with **bonds or defensive stocks**.  
- **Cluster 1:** Invest in **growth stocks, IPOs, and bullish market sectors**.  
- **Cluster 2:** Prepare for **inflation by focusing on commodities and high-yield investments**.  
- **Cluster 3:** Maintain **balanced portfolios for stable, long-term growth**.  

## Model Comparison  

| Model | Optimal Clusters | Silhouette Score | Key Strength |
|--------|----------------|----------------|--------------|
| **K-Means** | 4 | **0.54** | Better cluster separation |
| **Agglomerative** | 4 | **0.535** | Provides hierarchical insights |

- **K-Means was chosen as the final model** due to its **higher silhouette score** and **clearer cluster separation**.  

## Future Enhancements  

-  **Apply Advanced Clustering**: Try **DBSCAN or Gaussian Mixture Models** for deeper analysis.  
-  **Explore Macro-Economic Factors**: Incorporate **GDP, unemployment rates, and inflation**.  
-  **Build a Market Prediction Model**: Use **clustering outputs as features for supervised learning models**.  

## How to Run  

### Clone the Repository  

```sh
git clone https://github.com/kenny-balogun/clustering_SP500.git
```

### Install Dependencies

```sh
pip install -r requirements.txt
```
### Run the Notebook

```sh
jupyter notebook clustering_SP500.ipynb
```
