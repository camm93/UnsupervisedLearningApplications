# 🧠 Unsupervised Learning Projects

This repository contains hands-on projects applying **unsupervised machine learning** to extract structure and insights from unlabelled data. It includes clustering, dimensionality reduction, and image-based segmentation techniques. Each project is built with practical use cases and robust evaluation.

> 🚧 This is a growing repository. More projects will be added over time.  

---

## 📁 Projects

### 🎨 Color Palette Generation from Artwork

- **Objective**: Extract dominant color palettes from artwork images.
- **Use Case**: Useful for design inspiration, branding, or digital asset management.
- **Techniques**:
  - Image preprocessing with OpenCV and NumPy
  - Clustering in color space using `KMeans`, `MeanShift`, `HDBSCAN`, and `AgglomerativeClustering`
  - Dimensionality reduction using `PCA` and `t-SNE`
  - Cluster quality evaluation via `Silhouette Score` and `Davies-Bouldin Index`

🔗 [View Project](./color-palette-from-images/README.md)

---

### 👥 Customer Segmentation

- **Objective**: Group customers based on purchasing behavior and demographics.
- **Use Case**: Market segmentation for targeted marketing and personalization.
- **Techniques**:
  - Data preprocessing and feature engineering
  - Clustering with `KMeans`, `AgglomerativeClustering`, `DBSCAN`, and `GaussianMixture`
  - Dimensionality reduction using `PCA`
  - Cluster evaluation using inertia, silhouette score, and interpretability

🔗 [View Project](./customer-segmentation/README.md)

---

### 🧩 Image Segmentation using Clustering

- **Objective**: Segment images into meaningful regions (e.g., objects, textures) using clustering.
- **Use Case**: Preprocessing for computer vision pipelines, scene understanding, or artistic effects.
- **Techniques**:
  - Pixel-level feature extraction (RGB, spatial coordinates)
  - Unsupervised segmentation using `KMeans`, `MeanShift`, `AgglomerativeClustering`
  - Optional dimensionality reduction (`PCA`) for performance
  - Visual evaluation of segmented regions

🔗 [View Project](./image-segmentation/README.md)

---

## 🧰 Techniques Covered

- Clustering: `KMeans`, `MeanShift`, `AgglomerativeClustering`, `DBSCAN`, `GaussianMixture`
- Dimensionality Reduction: `PCA`, `t-SNE`
- Evaluation: `Silhouette Score`, `Davies-Bouldin Index`, inertia
- Image Processing: `OpenCV`, `PIL`, NumPy
- Data Manipulation: `pandas`, `scikit-learn`

---

## 🚀 What's Next?

This repo is part of a larger machine learning learning journey. Watch this space and its sibling repositories:

- 📊 **Supervised Learning** – classification, regression, feature selection
- 🧠 **Deep Learning** – CNNs, RNNs, Transformers
- 🕹 **Reinforcement Learning** – agents, environments, policies
- 🧬 **Generative AI** – diffusion, GANs, LLMs, retrieval-augmented generation (RAG)

---

## 👤 Author

Built by **Cristian Murillo** – Data Scientist and Machine Learning Engineer passionate about data-driven storytelling and real-world impact.

📫 [Connect on LinkedIn](https://www.linkedin.com/in/cristianmurillom/)  
🌐 More projects coming soon.
