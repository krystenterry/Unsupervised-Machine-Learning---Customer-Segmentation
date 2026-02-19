# Python/Unsupervised Machine Learning Customer Segmentation Project

## Project Overview

To understand the Target Customers for the Marketing Team to plan a strategy, I segmented customer data utilizing the following techniques:

1. **Bivariate Analysis/Bivariate Clustering**
2. **K-Means Algorithm and the Elbow Methodology**
3. **Summary Statistics**

With these techniques, I identified the most important shopping groups based on income, age and the mall shopping score and created labels for each of the ideal number of groups.

## Objectives

1. **Perform EDA**
2. **Use KMEANS Clustering Algorithm to Create Segments**
3. **Use Summary Statistics on the Clusters**
4. **Visualize the Results**

## Project Structure

### 1. Importing Required Libraries

The project begins by importing the required libraries for data analysis, visualization, and clustering and then importing the data.

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

import warnings 
warnings.filterwarnings('ignore')
```
```python
df = pd.read_csv("Mall_Customers.csv")
```

### 2. Data Analysis and Findings

- **Univariate Analysis**: Understand the data by using Histograms, Probability Density Plots and KDE Plots.

```python
sns.distplot(df['Annual Income (k$)']);
```
```python
sns.kdeplot(data=df, x='Annual Income (k$)', hue='Gender', fill=True)
```
```python
columns = [ 'Age', 'Annual Income (k$)','Spending Score (1-100)']
for i in columns: 
    plt.figure()
    sns.boxplot(data=df, x='Gender', y= df[i], hue='Gender')
```





## Findings

- **Cluster**: Target Marketing Group would be Cluster 3, which has a high Spending Score and high income.
- **Demographics**: 54% of Cluster 3 shoppers are women. We develop marketing campaigns that target popular items in this cluster to attract these customers.
- **Customer Insights**: Cluster 2 shoppers (low Annual Income but high Shopping Score) present an interesting opportunity to market to customers for sales events on popular items. 

## Conclusions

Based on the clustering analysis, the customer base can be segmented into groups representing various spending behaviors and income levels, enabling more targeted and data-driven marketing strategies. Using bivariate analysis, summary statistics and K-Means algorithms guided by the elbow method, clear patterns emerged across income, age and spending score.

Cluster 3 represents the primary target marketing group, which are customers who exhibit both high annual income and high spending scores. This indicates strong purchasing power and a high liklihood of engagement with premium or high value products. With 54% of this cluster consisting of women, marketing campaigns can be strategically tailored toward products and promotions that resonate with this demographic to maximise conversion and retention. 

Cluster 2, characterized by lower annual income but high spending scores, reveals a high-engagement segment that is price-sensitive yet active. This group presents a valuable opportunity for promotional campaigns, discounds and sales events on popular items, as they are likely to respond positively to value-driven marketing strategies. 

Overall, the segmentation approach allowed for the identification of key customer groups and their behavioral patterns, providing actionable insights for the marketing team. By leveraging K-Means clustering alongside exploratory and bivariate analysis, the project successfully transformed raw customer data into meaningful segments that support strategic decision-making, personalized marketing, and improved customer targeting.



