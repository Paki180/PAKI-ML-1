## Project Overview
Here's a brief summary of the key steps taken in this project:

### 1. Data Loading and Initial Exploration: 
Loaded the marketing campaign data and performed initial checks using df.head(), df.info(), and df.isnull().sum() to understand the data structure, identify missing values, and get a glimpse of the data.
### 2. Data Cleaning and Feature Engineering: 
Handled missing income values by filling them with the median. Then engineered new features like Age, ChildrenCount, Family_Size, Total_Spent, Total_Purchases, and Total_Campaign_Accepted to provide more meaningful insights, also addressed outliers in 'Age' and 'Income'.
### 3. Exploratory Data Analysis (EDA): 
Visualized the distributions of key features like 'Age', 'Income', and 'Total_Spent', also analyzed spending by product category and purchases by channel to understand customer behavior.
### 4. Data Preprocessing: 
Applied log transformation to skewed numerical features to normalize their distributions, also ordinally encoded the 'Education' column and created a binary 'marital_status' column.
### 5. Customer Segmentation (K-Means Clustering): 
Scaled the features and used the Elbow Method and Silhouette Score to determine the optimal number of clusters (k=4). Then applied K-Means clustering to segment the customers into these four groups.
### 6. Cluster Profiling and Interpretation: 
Analyzed the characteristics of each cluster based on the mean values of relevant features ('Age', 'Income', 'Total_Spent', 'Total_Purchases', 'Family_Size') to understand the distinct traits of each segment, also visualized the clusters using PCA to see their separation in a reduced dimension space.
### 7. Model Training and Evaluation: 
Trained and evaluated several classification models (Random Forest, Logistic Regression, SVC in a Voting Ensemble) to predict the customer cluster based on the features, also trained an SVR model to predict 'Total_Spent'.
### 8. Pipeline Creation: 
Built a data processing pipeline using ColumnTransformer and make_pipeline to automate the preprocessing steps and integrate them with a machine learning model (the Voting Classifier).
### 9. Streamlit App Development: 
Created a basic Streamlit application to potentially deploy the customer segmentation model for interactive use.

## Customer Cluster Explanation
Based on the K-Means clustering and the cluster profiling performed, here's an interpretation of the four identified customer segments:

### Cluster 0: "Value-Conscious Families"
Characteristics: These customers have a moderate average age and income. They tend to have larger families with more children (both kids and teens) and exhibit moderate overall spending and purchase frequency.
Marketing Focus: This segment is likely sensitive to price and deals due to their larger family size. Promotions focused on value, family-sized products, and budget-friendly options might resonate well.
### Cluster 1: "Affluent Singles/Couples"
Characteristics: This group has an older average age compared to Cluster 0, a significantly higher average income, and tends to have smaller family sizes (often without children at home). They show high spending and purchase frequency, particularly in categories like wine and meat products.
Marketing Focus: These customers are likely less price-sensitive and respond well to high-quality products and premium offerings. Targeted campaigns highlighting luxury items and exclusive deals could be effective.
### Cluster 2: "Established Households"
Characteristics: Similar in age to Cluster 1, but with a moderate average income (higher than Cluster 0, lower than Clusters 1 and 3). They have average family sizes and moderate to high spending and purchase frequency.
Marketing Focus: This segment represents a solid middle ground. They are likely receptive to a mix of value and quality. Loyalty programs, personalized recommendations based on past purchases, and promotions across various product categories could be successful.
### Cluster 3: "High-Spending Individuals"
Characteristics: This segment has the highest average income and the highest spending and purchase frequency among all clusters. They are typically middle-aged and have smaller family sizes.
Marketing Focus: These are the most valuable customers. Focus on retaining them with exclusive offers, early access to new products, and premium customer service. They are likely to respond to campaigns across all channels and product types.
