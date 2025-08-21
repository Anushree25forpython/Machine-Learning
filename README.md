# 📍 Project Title: Indoor vs Outdoor Acoustic Scene Classification using SVM

---

## 🧠 Overview

This project focuses on classifying short audio recordings based on their acoustic environment — specifically whether the recording was made **indoors** or **outdoors**. Using machine learning techniques (specifically **Support Vector Machines**), we extract meaningful audio features such as **pitch**, **power**, and **voiced region fractions** to predict the recording environment.

---

## 🎯 Problem Statement

Given an audio segment of 7 seconds, the objective is to determine whether the recording was done indoors or outdoors. This classification task has practical applications in **environmental monitoring**, **surveillance**, **sound-based geolocation**, and **media tagging**.

---

## 📁 Dataset

- **Source**: [MLEnd London Sounds Dataset](https://www.kaggle.com/datasets/jesusrequena/mlend-london-sounds)
- **Total samples**: 2500 audio files (`.wav`), each 7 seconds long
- **Attributes**:
  - `Audio`: File ID
  - `Area`: General region of recording
  - `Spot`: Specific location
  - `In/Out label`: Binary target label (1 = indoor, 0 = outdoor)
  - `Participant`: Who made the recording

The dataset was manually downloaded, unzipped, and loaded from Google Drive into a Colab notebook.

---

## 📓 Notebook

All steps of the pipeline — from **data loading** and **feature extraction** to **model training** and **evaluation** — are executed in a single Jupyter notebook:

👉 [`Indoor vs outdoor Acoustic Scene Classification using SVM.ipynb`]( ./ Indoor vs outdoor Acoustic Scene Classification using SVM.ipynb)

---

## ✨ Key Features

- 🎧 Feature extraction from raw `.wav` files using **librosa**:
  - Power
  - Pitch (mean and standard deviation)
  - Fraction of voiced region
- 📊 Binary classification: `indoor = 1`, `outdoor = 0`
- 🧪 Training/Validation split (both **70:30**)
- 🧠 Models - SVM using **scikit-learn**, RF and XGBoost
- 📉 Feature normalization and hyperparamater tuning to improve model performance
- 🔍 Accuracy analysis, overfitting/underfitting diagnostics

---

## 📌 Conclusion and Findings

1. SVM
Training: 66%, Validation: 60%
Gap is small → model generalizes reasonably, but overall accuracy is low.
Indicates underfitting with current features — SVM is not able to extract strong discriminative boundaries.
2. Random Forest
Training: 70%, Validation: 61%
Slightly higher training accuracy, but validation does not improve.
Suggests the model learns some non-linear structure, but it still cannot capture enough useful signal.
3. XGBoost
Training: 67%, Validation: 61%
Balanced training/validation, no major overfitting.
Performance is nearly identical to RF, but with better regularization control.

All three models stabilize around ~60–61% validation accuracy after proper tuning.
Training vs validation gaps are small → models are not overfitting (good sign).
The bottleneck is not the algorithm, but the feature set (power, pitch stats, voiced fraction) which lacks strong discriminative power for indoor vs outdoor classification.

---

## ✅ Overall Conclusion and way forward

Best performing models: Random Forest and XGBoost (≈61% validation accuracy), slightly better than SVM.
SVM: Balanced but underfitting with limited features.
RF & XGBoost: Handle non-linearities better, but still plateau at ~61%.
Overall: The chosen features provide some signal but are insufficient for reliable indoor/outdoor classification.

- Incorporating more **advanced features** like **MFCCs**, **spectral contrast**, or **mel spectrograms**
- Trying more robust classifiers such as **Neural Networks**
  
This project demonstrates the **feasibility of environmental audio classification** using a traditional ML approach and sets the stage for more advanced audio-based scene recognition tasks.

---

## 🛠️ Tools Used

- Python (Google Colab)
- NumPy, Pandas
- Matplotlib, Seaborn
- **Librosa** – Audio processing
- **Scikit-learn** – SVM modeling
- Random Forest classifier
- XGBoost
- tqdm, glob, zipfile, os
- Google Drive – Dataset storage
