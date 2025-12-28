# Customer Segmentation & Churn Analysis in E-Commerce

## Overview
This project aims to identify e-commerce customer behavior patterns through clustering (unsupervised learning).  
The analysis is conducted on a dataset of 50,000 customers with 25 demographic, engagement, and transactional features.  
The main focus is to understand customer segmentation and the factors influencing churn (discontinuation of service usage).

---

## 1. Objective & Research Questions
**Objective:** Identify e-commerce customer behavior patterns and factors that drive churn.  

**Research Questions:**  
- What are the key characteristics of churned vs. non-churned customers?  
- How do lifetime value, login frequency, and cart abandonment affect customer loyalty?  
- Which segments are most promising for retention strategies?  

---

## 2. Data Description
**Data Source**  
- Dataset: *Ecommerce Customer Behavior Dataset*  
- Link: Kaggle – Ecommerce Customer Behavior Dataset  
- Records: 50,000 customers  
- Features: 25 columns  
- Data Types: Mixed (numerical, categorical, object)  
- Geographic Coverage: Multiple countries (USA, UK, Germany, Canada, India, Japan, France, Australia)  
- Time Period: Captures customer journey from signup through current status  

**Data Quality**  
- Contains missing values (NaN) in certain columns  
- Mix of continuous numerical values (e.g., order values, engagement scores)  
- Categorical variables (Gender, Country, City, Payment methods)  
- Binary indicator (Churned: 0 = Active, 1 = Churned)  

---

## 3. Key Steps
- **Data Cleaning:** Handle missing values using imputation (median, constant, KNN) and treat outliers with capping (IQR).  
- **Feature Scaling:** Standardize numerical features to ensure equal contribution in clustering.  
- **Exploratory Data Analysis (EDA):** Pairplot & heatmap to uncover feature relationships (e.g., Lifetime Value correlates with Total Purchases).  
- **Insight:** After cleaning, all numerical features are free of missing values and outliers → ready for clustering.  

---

## 4. Methodology & Algorithms
- **Algorithm:** K-Means with K=4 (determined by Elbow Method).  
- **Reasoning:** Suitable for large datasets, easy to interpret clusters.  
- **Additional Step:** PCA applied for dimensionality reduction → 2D cluster visualization.  

**Cluster Profiles:**  
1. **High-Value Selective Shoppers** → High lifetime value, large orders, but significant cart abandonment.  
2. **At-Risk / Low Engagement Shoppers** → Low engagement, small lifetime value, primary churn candidates.  
3. **Highly Engaged Loyal Customers** → Frequent logins, long sessions, many purchases, high lifetime value.  
4. **Frequent but Budget Shoppers** → Shop often with small order values, highly price-sensitive.  

---

## 5. Evaluation Metrics
- **Silhouette Score:** 0.1705 → indicates overlap between clusters.  
- **Interpretation:** Clusters are moderately separated but could be improved with alternative methods (DBSCAN, Hierarchical).  

---

## 6. Visualization & Dashboard
- **Pairplot & Heatmap:** Strong correlation between Lifetime Value, Total Purchases, and Average Order Value.  
- **PCA Scatter Plot:** Clear visualization of 4 clusters.  
- **Boxplot:** Comparison of feature distributions between churned vs. non-churned customers.  

---

## 7. Limitations & Challenges
- **Data Quality Issues:** Extreme outliers (e.g., age = 200 years, cart abandonment >100%).  
- **Low Silhouette Score:** Indicates cluster overlap.  
- **Categorical Features:** Not yet encoded (Gender, Country, City) → potential for richer insights.  

---

## 8. Future Work / Recommendations
- Experiment with alternative clustering algorithms (DBSCAN, Gaussian Mixture) to improve separation.  
- Apply One-Hot Encoding to categorical features.  
- Build supervised churn prediction models (e.g., Random Forest, XGBoost).  

---

## 9. Business Impact
- **Cluster 2 (Highly Engaged Loyal Customers):** Potential brand ambassadors.  
- **Cluster 1 (At-Risk Shoppers):** Primary target for win-back programs.  
- **Cluster 0 (High-Value Selective Shoppers):** Focus on checkout optimization.  
- **Cluster 3 (Budget Shoppers):** Drive upselling through bundles & discounts.  

---

## 10. Strategic Insights
- **Retention Strategy:** Focus on at-risk clusters with promotions & re-engagement.  
- **Loyalty Programs:** Strengthen loyal clusters with exclusive benefits.  
- **Upselling & Bundling:** Target frequent budget shoppers with value bundles.  
- **Conversion Optimization:** Reduce cart abandonment among high-value shoppers with checkout incentives.  

---

## 11. Tools & Environment
**Python Libraries:**  
- `pandas` → data cleaning & preprocessing  
- `numpy` → numerical computation  
- `matplotlib` & `seaborn` → data visualization (heatmap, boxplot, scatter plot)  
- `scikit-learn` → clustering (K-Means), PCA, evaluation (Silhouette Score)  

**Environment:**  
- **Google Colab** → interactive notebook for analysis  
- **Kaggle** → dataset hosting & initial exploration  

✨ Now your document is fully in English, polished for academic + business presentation style.  

Would you like me to also **condense this into a 1-page executive summary** (bullet points + visuals suggestion) for quick presentation slides?
