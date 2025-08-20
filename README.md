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

- The **SVM model** achieved moderate accuracy:
  - **Pre-normalization**: ~ ~88% (train), ~60% (validation)
  - **Post-normalization**: ~66% (train), ~65% (validation)
  - **Post hyperparamater tunning:  ~64% (train), ~63% (validation)
- The SVM model achieved moderate and balanced performance after normalization and hyperparameter tuning (~64–65% accuracy), but results suggest that the current feature set (power, pitch stats, voiced fraction) is not sufficiently discriminative for indoor vs outdoor classification.

---

## ✅ Overall Conclusion

While SVM with a few basic audio features yielded decent results, model performance could be significantly enhanced by:

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
