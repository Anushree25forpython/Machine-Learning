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
- 🧪 Training/Validation split (both **70:30** and **60:40** explored)
- 🧠 SVM modeling using **scikit-learn**
- 📉 Feature normalization to improve model performance
- 🔍 Accuracy analysis, overfitting/underfitting diagnostics

---

## 📌 Conclusion and Findings

- The **SVM model** achieved moderate accuracy:
  - **Pre-normalization**: ~52%–53%
  - **Post-normalization**: ~67% (train), ~57% (validation)
- **Normalization** improved training accuracy but slightly widened the gap between train and validation sets.
- Adjusting the train/validation split helped balance performance slightly.

---

## ✅ Overall Conclusion

While SVM with a few basic audio features yielded decent results, model performance could be significantly enhanced by:

- Incorporating more **advanced features** like **MFCCs**, **spectral contrast**, or **mel spectrograms**
- Trying more robust classifiers such as **Random Forest**, **KNN**, or **Neural Networks**
- Expanding dataset size or using **audio augmentation techniques**

This project demonstrates the **feasibility of environmental audio classification** using a traditional ML approach and sets the stage for more advanced audio-based scene recognition tasks.

---

## 🛠️ Tools Used

- Python (Google Colab)
- NumPy, Pandas
- Matplotlib, Seaborn
- **Librosa** – Audio processing
- **Scikit-learn** – SVM modeling
- tqdm, glob, zipfile, os
- Google Drive – Dataset storage
