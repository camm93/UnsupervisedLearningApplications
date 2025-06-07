# Image Segmentation with K-Means Clustering

This Jupyter Notebook demonstrates a basic image segmentation task using the K-Means clustering algorithm.

## What's Done

The notebook performs the following steps:

1. **Image Loading and Preprocessing**  
   An image (`neymar.png`) is loaded and converted to the RGB color space. Its pixel data is then reshaped into a 2D array, where each row represents a single pixel and its corresponding RGB color values.

2. **K-Means Clustering**  
   The K-Means algorithm is applied to the processed pixel data to group similar colors together. In this specific example, the image is segmented into **4 distinct color clusters**.

3. **Image Reconstruction**  
   The original image is reconstructed using the average color (centroid) of each cluster. This effectively segments the image, replacing the original pixel colors with the representative colors of their clusters.

4. **Visualization**  
   The original image and the segmented (reconstructed) image are displayed side-by-side for comparison.

## Techniques Used

- **K-Means Clustering**  
  An unsupervised machine learning algorithm used to partition *n* observations into *k* clusters, where each observation belongs to the cluster with the nearest mean (centroid). In this notebook, it's used to group pixels with similar color values.

- **OpenCV (`cv2`)**  
  Used for loading and basic image manipulation (e.g., color space conversion).

- **NumPy (`numpy`)**  
  Essential for efficient numerical operations and array manipulation, especially for reshaping the image data for clustering.

- **Matplotlib (`matplotlib.pyplot`)**  
  Used for visualizing the original and segmented images.
