# Project Title: Indoor vs outdoor Acoustic Scene Classification using SVM

 ## Overview

This project focuses on classifying short audio recordings based on their acoustic environment — specifically whether the recording was made indoors or outdoors. Using machine learning techniques (specifically Support Vector Machines), we extract meaningful audio features such as pitch, power, and voiced region fractions to predict the recording environment.


--

## 🎯 Problem Statement

Given an audio segment of 7 seconds, the objective is to determine whether the recording was done indoors or outdoors. This classification task has practical implications in environmental understanding, surveillance, sound-based geolocation, and content tagging.

--

## 📁 Dataset

-Source: MLEnd London Sounds Dataset
 - Total samples: 2500 audio files (.wav), each 7 seconds long
 - Attributes:
   - 'Audio' (file ID)
   - 'Area'
   - 'Spot'
   - 'In/Out label' (binary classification target)
   - 'Participant'
- The dataset is manually downloaded, unzipped, and loaded from Google Drive into a Colab notebook.

--

## 📒 Notebook

All steps of the pipeline — from data loading and feature extraction to model training and evaluation — are executed in a single .ipynb notebook:

👉 Indoor_Outdoor_Audio_Classification.ipynb

--

## ✨ Key Features

🎧 Feature extraction from raw .wav files using librosa:
Power
Pitch (mean and standard deviation)
Fraction of voiced region
📊 Binary classification (indoor = 1, outdoor = 0)
🧪 Training/Validation split (both 70:30 and 60:40 explored)
🧠 Support Vector Machine (SVM) modeling using scikit-learn
📉 Feature normalization to improve model performance
🔍 Analysis of model accuracy, overfitting, and underfitting
📌 Conclusion and Findings

The SVM model achieved moderate accuracy:
Pre-normalization: ~52%–53%
Post-normalization: ~67% (train) and ~57% (validation)
Normalization improved training performance but slightly widened the accuracy gap between train and validation sets.
Adjusting the train/validation split helped balance performance slightly.

--

## ✅ Overall Conclusion

While SVM with four basic audio features yielded acceptable results, the performance could be enhanced by:

Incorporating more advanced features like MFCCs or Mel spectrograms
Trying alternative classifiers such as Random Forest, KNN, or Neural Networks
Increasing dataset diversity or audio augmentation
This project lays the groundwork for audio-based scene understanding and demonstrates the feasibility of environmental audio classification using traditional ML techniques.

--

## 🛠️ Tools Used

Python
Google Colab
NumPy, Pandas
Matplotlib
Librosa (for audio processing)
Scikit-learn (for SVM modeling)
tqdm, glob, zipfile, os
Google Drive for dataset storage
