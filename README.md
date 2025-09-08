---
title: Unsupervised Clustering with Gradio
emoji: 📊
colorFrom: blue
colorTo: green
sdk: gradio
sdk_version: "3.50.2"  
pinned: false
---

# Wine Clustering App

An interactive machine learning application built with Python, Scikit-learn, and Gradio, designed to explore unsupervised clustering algorithms on the Wine dataset.

This app allows users to try different clustering methods (KMeans, Hierarchical, DBSCAN) and visualize results in real-time with PCA-reduced scatter plots.

🌟 Features

📊 Multiple Clustering Algorithms:

KMeans (partitioning method)

Hierarchical Clustering (nearest centroid assignment for new samples)

DBSCAN (density-based clustering with outlier detection)

🖼 Real-time Visualization: PCA 2D scatter plot for clusters + new sample

📈 Clustering Metrics: Silhouette Score (when applicable)

📝 Custom Input Values: Users can test predictions on new data points

🎛 Interactive Parameters: Change number of clusters (k) for KMeans/Hierarchical, tune DBSCAN parameters (eps, min_samples)

🧪 Usage

Login to access the clustering dashboard.

Select your preferred algorithm: KMeans, Hierarchical, or DBSCAN.

Adjust parameters:

k → number of clusters (KMeans/Hierarchical)

eps, min_samples → DBSCAN parameters

Enter feature values (default = median of dataset).

Click Find Cluster.

Results displayed:

Predicted cluster (or outlier warning for DBSCAN)

Silhouette Score (if applicable)

PCA visualization with clusters and your new sample highlighted (⭐).

📊 Example Outputs
✅ KMeans
Belongs to Cluster: 2 (KMeans, k=3)  
Silhouette Score = 0.4532
<img width="866" height="682" alt="Screenshot 2025-09-08 070921" src="https://github.com/user-attachments/assets/e9c7eab8-4348-43f4-b43d-6f5db5957e09" />


✅ Hierarchical
Belongs to Cluster: 1 (Hierarchical, k=3)  
Silhouette Score = 0.3847
<img width="1048" height="675" alt="Screenshot 2025-09-08 070937" src="https://github.com/user-attachments/assets/d85b1917-19bb-4089-be5d-6e360a08c97d" />


🚨 DBSCAN
OUTLIER: DBSCAN labeled this sample as noise
<img width="856" height="674" alt="Screenshot 2025-09-08 071003" src="https://github.com/user-attachments/assets/0b939a1c-5959-4edd-ba57-f5413f0446c0" />


⚙️ Algorithm Details
🔹 KMeans

Assigns points to the nearest centroid.

Parameter: k (number of clusters).

Strength: Simple, fast.

Weakness: Assumes spherical clusters.

🔹 Hierarchical (Agglomerative)

Builds a cluster tree (dendrogram).

Cluster assignment based on nearest centroid after clustering.

Parameter: k (number of clusters).

Strength: Intuitive, doesn’t require k initially.

Weakness: Hard to scale to large datasets.

🔹 DBSCAN

Groups together closely packed points, marking low-density points as noise.

Parameters:

eps → neighborhood radius

min_samples → minimum number of neighbors to form a cluster

Strength: Can find arbitrarily shaped clusters & detect outliers.

Weakness: Sensitive to parameter tuning.

🛠 Troubleshooting

DBSCAN found no clusters → means your chosen eps and min_samples mark everything as noise.

Try smaller/larger eps.

Adjust min_samples.

Silhouette Score not showing → happens if only 1 cluster is found.

App not starting → ensure you installed dependencies with pip install -r requirements.txt.

🚀 Future Improvements

📌 Auto-tune DBSCAN parameters (eps, min_samples)

📌 Add clustering algorithms: OPTICS, MeanShift

📌 Export clustered dataset with assigned labels

📌 Deploy on Hugging Face Spaces or Streamlit Cloud
