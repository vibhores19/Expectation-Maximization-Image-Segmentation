# 🖼️ EM-Based Color Image Segmentation

This project implements **Image Segmentation** using the **Expectation-Maximization (EM) Algorithm** to classify pixels into segments based on color distribution. The algorithm is applied on three test images with varying number of segments to explore convergence, segmentation quality, and practical outcomes.

## 🧠 What is Image Segmentation?

Image segmentation is a computer vision technique that divides an image into distinct segments or "blobs", typically to isolate regions of interest (e.g., object detection, medical imaging, satellite imagery). In this project, we use a **probabilistic clustering approach** using EM to separate image pixels based on color similarity.

---

## 📥 Inputs
- **Images**: 
  - `Jump`
  - `Water Coins`
  - `Tiger`

- **Parameters**:
  - `nSegments`: Number of clusters (2 to 5)
  - `maxIterations`: Max iterations for EM algorithm (default: 20)
  - Initial guesses for mixture coefficients (π) and color means (µ)

---

## ⚙️ Methodology

### EM Algorithm Steps:
1. **Initialization**: Random values for π and µ.
2. **E-Step**: Estimate membership weights (W) for each pixel.
3. **M-Step**: Update π and µ using weights.
4. **Convergence**: Loop until parameter change is minimal.

### Post-processing:
- Convert clusters to grayscale image.
- Apply **K-means** for final segment labeling.
- Apply **Gaussian Smoothing (σ = 2)**.
- Re-color segments for final segmented image output.

---

## 🖼️ Results Overview

### 📷 Water Coins
- 2 Segments: Clean separation of coins and water.
- 5 Segments: Captures boundary details and coin engravings.

### 📷 Jump
- 4-5 Segments: Best segmentation — snow, sky layers, and the jumper clearly visible.

### 📷 Tiger
- 5 Segments: Segments tiger, stripes, grass, water, and sand distinctly.
- Higher segments may improve even further.

---

## 📈 Key Insights
- EM converges quickly (~5–17 iterations).
- Higher segments improve detail but may over-segment.
- Initialization of parameters affects convergence and quality.
- Each image behaves differently depending on inherent complexity.

---

## 🛠️ Tools Used
- Python / NumPy
- OpenCV / matplotlib
- Gaussian Smoothing
- K-means Clustering

---

## 📚 References
- Ilea, D.E., & Whelan, P.F. (Color Image Segmentation using a Self-Initializing EM Algorithm)
- Shafarenko et al. (Histogram-based Segmentation in Perceptually Uniform Color Space)
- Comaniciu & Meer (Robust Feature Space Analysis)

---
