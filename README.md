# Upper-Body Sitting Posture Recognition Using Skeletal Keypoints

This repository presents a machine learning pipeline for **upper-body sitting posture recognition**
using privacy-preserving skeletal keypoints extracted via **MediaPipe Pose**.

The project is developed as part of a **Graduation Project (Machine Learning Module)** and focuses on
real-time, camera-based ergonomic posture analysis without using raw images or videos.

---

## 📌 Overview

- **Dataset:** MultiPosture Dataset (IEEE Access, 2024)
- **Task:** Multi-class classification of upper-body sitting postures
- **Input:** 3D skeletal keypoints (x, y, z)
- **Models:** Random Forest, XGBoost
- **Final Model:** XGBoost Classifier

---

## 📊 Dataset

The experiments are conducted using the **MultiPosture dataset**, which contains skeletal pose data
extracted from video recordings using the MediaPipe Pose Heavy model.

**Key characteristics:**

- 13 participants
- ~4,800 labeled frames
- 11 key body joints (subset used in this work)
- Coordinates normalized relative to the hip center
- No raw images or videos (privacy-preserving)

### Upper-Body Classes

- **TUP:** Upright trunk position
- **TLB:** Trunk leaning backward
- **TLF:** Trunk leaning forward
- **TLR:** Trunk leaning right
- **TLL:** Trunk leaning left

---

## 📂 Dataset Availability

The dataset is **not included** in this repository due to licensing and privacy considerations.

The official dataset can be accessed here:  
🔗 **https://zenodo.org/records/14230872**

### How to reproduce the experiments:

1. Download the dataset from the link above.
2. Rename or ensure the file is named `data.csv`.
3. Place it in the root directory of this repository.
4. Run the Jupyter Notebook.

---

## ⚙️ Methodology

The proposed pipeline follows these steps:

1. Data inspection and integrity verification
2. Exploratory Data Analysis (EDA)
3. Upper-body feature selection
   - 13 upper-body joints × (x, y, z) → **39 features**
4. Preprocessing:
   - Label Encoding
   - Stratified train/test split
   - Min-Max scaling
   - Class weighting to handle imbalance
5. Model training (Random Forest, XGBoost)
6. Model evaluation and stability analysis
   - Repeated train/test splits
   - Stratified K-Fold Cross-Validation
7. Final model training and export

---

## 📈 Results

- **XGBoost Accuracy:** ~99%
- Consistent performance across multiple evaluation runs
- Very low variance, indicating strong model stability and robustness

---

## 🚀 Deployment

The final trained model, along with the scaler and label encoder, is saved and integrated into
a real-time desktop camera application for posture monitoring as part of a Smart Posture and
Attention Monitoring System.

---

## 📚 Reference

Carneros-Prado, D., Cabañero-Gómez, L., Johnson, E., González Díaz, I., Fontecha, J., & Hervás, R.  
_A Comparison Between Multilayer Perceptrons and Kolmogorov-Arnold Networks for Multi-Task Classification in Sitting Posture Recognition_,  
**IEEE Access**, 2024.
