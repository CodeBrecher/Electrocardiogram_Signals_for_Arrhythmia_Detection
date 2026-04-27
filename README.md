# ECG Arrhythmia Classification: 1D to 2D Spectrograms & Deep Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-ee4c2c)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-F7931E)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

This repository contains a complete pipeline for classifying Electrocardiogram (ECG) beats as either **Normal (N)** or **Premature Ventricular Contraction (V / PVC)**. 

The project demonstrates an advanced approach by transforming traditional 1D physiological signals into **2D Spectrograms**, allowing Convolutional Neural Networks (CNNs) to extract rich time-frequency features. It also benchmarks this Deep Learning approach against 6 traditional Machine Learning models.

---

## 🚀 Key Features

* **Strict Patient-Wise Splitting:** Ensures the model is evaluated on a patient it has *never* seen during training (Train: Patients 100, 119, 200 | Test: Patient 214). This prevents data leakage and proves real-world generalization.
* **Time-Frequency Transformation:** Uses `scipy.signal.spectrogram` to convert 1D ECG arrays into 2D heatmap representations.
* **Class Imbalance Handling:** Implements dynamic class weighting in PyTorch's `CrossEntropyLoss` to handle the heavy imbalance between normal beats and arrhythmias in clinical data.
* **Advanced CNN Architecture:** Features Batch Normalization, Dropout (50%), Adaptive Average Pooling, and deep convolutional filters specifically tuned for spectrogram feature extraction.
* **Comprehensive Benchmarking:** Compares the custom PyTorch CNN against Random Forest, Logistic Regression, SVM, KNN, Naive Bayes, and Gradient Boosting.

---

## 📁 Dataset Overview & Link

**Dataset Name:** MIT-BIH Arrhythmia Database v1.0.0  
**Official Link:** https://physionet.org/content/mitdb/1.0.0/

*Note: You do not need to download this manually to run the code. The Python `wfdb` library included in the script will automatically connect to the PhysioNet server and download the required patient records into a local `mitdb/` folder during your first run.*

---

## 🛠️ Installation & Setup

**Prerequisites:** Ensure you have Python 3.8+ installed.

1. Clone the repository:
   ```bash
   git clone <your-repository-url>
   cd <repository-folder>
