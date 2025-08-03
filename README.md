# MSCS 634 – Lab 5: Clustering with Hierarchical and DBSCAN

### Student: Sujan Dumaru  
### Course: Advanced Big Data and Data Mining  
### Lab Title: Clustering with Hierarchical and DBSCAN  
### Dataset: Wine Dataset (from sklearn.datasets)

---

## Purpose of the Lab

The purpose of this lab was to explore two unsupervised machine learning algorithms — **Hierarchical Clustering** and **DBSCAN** — using the Wine dataset. I applied both methods to better understand how they group data points based on similarities, and how parameter choices influence clustering behavior. The lab also included visual analysis using scatter plots and dendrograms, along with evaluation metrics like Silhouette Score, Homogeneity Score, and Completeness Score.

---

## What I Did

1. **Loaded and standardized the Wine dataset** using `StandardScaler` to prepare for clustering.
2. **Performed Agglomerative Hierarchical Clustering** for different values of `n_clusters` and visualized the clusters.
3. **Generated a dendrogram** to observe the natural number of clusters in the data.
4. **Applied DBSCAN Clustering** with various combinations of `eps` and `min_samples`.
5. **Evaluated clustering results** using Silhouette Score, Homogeneity Score, and Completeness Score (when valid).
6. **Compared and analyzed** the effectiveness and limitations of both algorithms.

---

## Key Insights

- **Hierarchical Clustering** worked well for this dataset, especially when using 3 clusters, which matched the original wine class labels. The dendrogram made it easier to understand how clusters were formed.
- **DBSCAN** failed to form valid clusters in high-dimensional space without dimensionality reduction. All configurations resulted in either one cluster or only noise.
- The choice of parameters like `n_clusters` for Hierarchical Clustering and `eps`, `min_samples` for DBSCAN had a major impact on the results.
- Hierarchical Clustering is more stable and interpretable, while DBSCAN requires careful tuning and is better suited to low-dimensional, spatially separated data.

---

## Challenges Faced

- DBSCAN failed repeatedly due to poor density separation in the standardized dataset. All data points were marked as noise.
- Understanding how `eps` affects density estimation in higher dimensions took some trial and error.
- It was tricky to interpret metrics when only one cluster or noise was detected — I had to suppress evaluation for those cases to avoid misleading outputs.

---

## Decisions Made

- I decided to stick with the original feature set for Hierarchical Clustering because it performed well without dimensionality reduction.
- For DBSCAN, although PCA was considered, I documented the failure in the original space to highlight its sensitivity to data characteristics.
- I manually evaluated cluster visuals and used Silhouette Score to verify cluster compactness when possible.

---

## Files in this Repository

- `lab5_notebook.ipynb`: Complete Jupyter Notebook with all steps, visualizations, and analysis.
- `README.md`: This file, summarizing my approach and findings.

---

## What I Learned

This lab helped me understand not just how to apply clustering algorithms, but also how to tune and evaluate them, especially when dealing with real-world datasets where structure may not be obvious. It reinforced the idea that algorithm choice depends on data characteristics, and that visualization and evaluation metrics are critical for interpreting unsupervised learning results.
