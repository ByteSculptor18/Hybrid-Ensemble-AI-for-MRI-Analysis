# NeuroFusion: Hybrid Ensemble Learning for Brain Tumor Detection 🧠

## 📌 Project Overview

**NeuroFusion** is a medical imaging project for automated classification of brain MRI scans into four categories: **Glioma, Meningioma, Pituitary Tumor, and No Tumor**.

Unlike single-model approaches, NeuroFusion uses a **Hybrid Ensemble Architecture** that integrates **Transfer Learning (VGG16)**, **Unsupervised Representation Learning (Convolutional AutoEncoder)**, and **Gradient Boosting (XGBoost)** to achieve high accuracy and robustness.

---

## 🚀 Key Features

* **Dual-Stream Architecture:** Combines supervised VGG16 features with unsupervised AutoEncoder representations.
* **Deep Feature Extraction:** Custom Convolutional AutoEncoder (CAEN) compresses MRI images into a **6,272‑dimensional latent vector**.
* **Hybrid Ensemble Learning:** Weighted Soft Voting of VGG16 and CAEN+XGBoost predictions.
* **High Diagnostic Reliability:** Achieves **96.15% accuracy** with strong Precision–Recall balance and reduced false negatives.

---

## 📂 Dataset

Compatible with standard Brain Tumor MRI datasets (e.g., Kaggle / SARTAJ).

* **Classes:** Glioma, Meningioma, Pituitary Tumor, No Tumor
* **Input Size:** 224 × 224 × 3 (RGB)
* **Formats:** `.jpg`, `.png`

---

## 🛠️ Tech Stack

### Core Tools

* Python, Jupyter Notebook

### Deep Learning

* TensorFlow, Keras
* VGG16 (Transfer Learning)
* Convolutional AutoEncoder (CAEN)

### Machine Learning

* Scikit‑Learn
* XGBoost
* Random Forest

### Visualization & Utilities

* Matplotlib, Seaborn
* NumPy, Pandas
* ImageDataGenerator

---

## 📊 Methodology & Workflow

1. **Preprocessing**

   * Image resizing to 224×224
   * Normalization (1/255)
   * Data augmentation

2. **Stream A – VGG16**

   * Transfer learning with ImageNet weights
   * Fine‑tuning with **L2 regularization** to reduce overfitting

3. **Stream B – CAEN + XGBoost**

   * Train Convolutional AutoEncoder to reconstruct MRI images
   * Extract latent features from encoder bottleneck
   * Train XGBoost classifier on extracted deep features

4. **Ensemble Strategy**

   * Weighted Soft Voting:

     * **60% VGG16**
     * **40% CAEN + XGBoost**

---

## 📈 Results Comparison

| Model                    |  Accuracy  | Precision |  Recall  | F1‑Score |
| ------------------------ | :--------: | :-------: | :------: | :------: |
| Existing Benchmarks      |   ~94.00%  |    0.94   |   0.94   |   0.94   |
| VGG16 (Proposed)         |   95.23%   |    0.95   |   0.95   |   0.95   |
| CAEN + XGBoost           |   95.19%   |    0.95   |   0.95   |   0.95   |
| **NeuroFusion Ensemble** | **96.15%** |  **0.96** | **0.96** | **0.96** |

> The ensemble approach consistently outperforms individual models and existing literature.

---

## 💻 How to Run

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/neurofusion-mri.git
   ```

2. **Install dependencies**

   ```bash
   pip install tensorflow xgboost scikit-learn pandas matplotlib seaborn
   ```

3. **Run the notebook**

   * Open `MRI_Comparing_Different_Models.ipynb` in Jupyter Notebook or Google Colab

4. **Update dataset paths**

   * Modify `train_path` and `test_path` variables to point to your dataset directory

---

## 🔮 Future Scope

* Integration of **3D CNNs** for volumetric MRI analysis
* Deployment as a **web application** using Streamlit or Flask
* Evaluation on larger clinical datasets such as **BraTS**

---

## 👨‍💻 Author

**Sayan Biswas**
Computer Science Engineering (AI & ML)
2025

---

⭐ If you find this project useful, consider giving the repository a star!
