# Human Atlas Clustering: Why DPGMM, K-Means, and DBSCAN Failed

I attempted to cluster feature embeddings from the Human Protein Atlas dataset using:
✅ Dirichlet Process Gaussian Mixture Model (DP-GMM)
✅ K-Means
✅ DBSCAN
What Went Wrong?

❌ DP-GMM failed to converge – The model struggled with extreme non-Gaussianity.
❌ K-Means silhouette scores were near zero, indicating poor separation.
❌ DBSCAN labeled almost everything as noise (-1), suggesting no meaningful density clusters.
Key Takeaways: How to Detect Non-Gaussianity Early

🔹 Test for Gaussianity – Use Shapiro-Wilk, Q-Q plots, or skewness/kurtosis before applying GMM-based methods.
🔹 Check PCA – If principal components don’t show separable clusters, clustering may not work.
🔹 Use K-Means as a sanity check – If the elbow method and silhouette score indicate poor structure, rethink clustering.
🔹 Try DBSCAN – If everything is classified as noise, it suggests no meaningful density-based clusters exist.
