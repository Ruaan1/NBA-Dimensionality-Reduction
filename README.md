# NBA Player Representation Learning & Dimensionality Reduction

This project explores **unsupervised representation learning** and **dimensionality reduction** techniques on high-dimensional NBA player statistics, with the goal of uncovering latent structure and meaningful groupings in player performance data.

Rather than focusing on prediction, the emphasis is on **understanding how different embedding methods shape the geometry of the data** and how clustering behaves in reduced latent spaces.

---

## 📊 Dataset

The dataset consists of advanced NBA player statistics derived from publicly available sources (Basketball Reference / Kaggle).

Features include:
- Efficiency metrics
- Usage and pace-adjusted statistics
- Advanced performance indicators

These features form a high-dimensional representation of player performance that is well-suited for unsupervised analysis.

---

## 🧹 Data Cleaning & Preparation

Before applying dimensionality reduction, the dataset was:
- inspected for anomalous or implausible values
- cleaned to handle missing or inconsistent entries
- standardised to ensure comparability across features

These steps are critical, as dimensionality reduction methods are highly sensitive to scale and noise.

---

## 🧠 Methods Explored

The project compares multiple dimensionality reduction pipelines:

### 🔹 Autoencoders
- Neural autoencoders were trained to learn compact latent representations
- The learned embeddings capture non-linear structure in the data

### 🔹 Autoencoders + SOM
- Self-Organising Maps were applied to autoencoder embeddings
- Useful for topology-preserving visualisation and cluster intuition

### 🔹 Autoencoders + t-SNE
- t-SNE applied to learned embeddings
- Emphasises local neighbourhood structure

### 🔹 Autoencoders + UMAP
- UMAP applied to embeddings for better global structure preservation
- Provides more stable cluster separation than t-SNE in this setting

### 🔹 Variational Autoencoder (VAE)
- VAEs introduce a probabilistic latent space
- Allows exploration of smoothness, continuity, and latent uncertainty

---

## 🔍 Clustering & Visual Analysis

For each 2D embedding:
- **k-means clustering** was applied
- clusters were visualised and compared across methods
- consistency and interpretability of clusters were evaluated

The comparison highlights how:
- some methods produce visually separable but unstable clusters
- others preserve meaningful global structure at the cost of local detail

---

## 📈 Key Observations

- Dimensionality reduction method choice significantly affects perceived structure
- Autoencoder + UMAP produced the most interpretable balance between local and global structure
- t-SNE produced sharp separations but was sensitive to parameter choices
- VAEs introduced smoother embeddings but less distinct clusters
- Clustering results must be interpreted jointly with the embedding method used

No single method is universally “best” — each reveals different aspects of the data.

---

## 🧠 Takeaways

- Representation learning is as much about **interpretation** as compression
- Visual separability does not always imply meaningful structure
- Combining neural embeddings with classical methods (SOM, k-means) can yield richer insight
- Careful preprocessing is essential for trustworthy unsupervised analysis

---

## 📌 Notes

This project was completed as part of coursework, but the implementation, analysis, and interpretation were carried out independently.

The focus is exploratory and analytical rather than predictive, with an emphasis on understanding **latent structure in complex, high-dimensional data**.

---

## 📂 Repository Contents

- Jupyter notebook containing all preprocessing, modelling, and visualisations
- Dataset used for analysis
- Supporting outputs generated during experimentation
