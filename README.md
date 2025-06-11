# machine_learning_project-unsupervised-learning

## Project Objective
Identify distinct customer groups based on their purchase patterns, allowing for tailored marketing strategies, promotions, and inventory management.

## Project Outcomes

- Unsupervised Learning: perform unsupervised learning techniques on a wholesale data dataset. The project involves four main parts: exploratory data analysis and pre-processing, KMeans clustering, hierarchical clustering, and PCA.

## Dataset

- **Source:** Kaggle “Wholesale Customer Data”  
- **Features:**  
  - **Channel, Region** (client identifiers)  
  - **Fresh, Milk, Grocery, Frozen, Detergents_Paper, Delicassen** (annual spend in monetary units)  
- **Size:** 440 observations, no missing values or duplicates.


---

## Methodology

1. **Exploratory Data Analysis & Cleaning**  
   - Checked distributions with histograms and boxplots.  
   - Detected and capped outliers at 1.5×IQR to prevent skew.  

2. **Feature Engineering**  
   - Log-transformed spending columns (`log1p`) to reduce skew.  
   - Standardized features to zero mean and unit variance.  
   - Created **`Household_Goods`** by merging Grocery + Detergents_Paper (the strongest correlated pair).

3. **Clustering**  
   - **K-Means:** Used elbow method + silhouette scores → **k = 3**.  
   - **Hierarchical (Ward linkage):** Confirmed three clusters with similar profiles.  

4. **PCA**  
   - Computed principal components; **PC1 + PC2 explain >70%** of variance.  
   - Interpreted axes as “perishables vs. packaged goods” and “overall spend.”  
   - Visualized clusters in PC space to validate separation.

5. **Evaluation Metrics**  
   - **Silhouette Scores:** K-Means 0.38, Hierarchical 0.36  
   - **Adjusted Rand Index:** 0.72 (strong agreement between methods)  

---

## Key Findings

- **Cluster Profiles:**  
  1. **Pantry Shoppers:** High Grocery & Detergents_Paper, low Fresh/Frozen  
  2. **Perishables Enthusiasts:** High Fresh & Frozen, low packaged goods  
  3. **All-Around High-Volume:** High spend across all categories

- **Business Implications:**  
  - Offer bundled non-perishable deals to Pantry Shoppers.  
  - Promote fresh-produce subscriptions to Perishables Enthusiasts.  
  - Reward All-Around High-Volume clients with loyalty incentives.
