# Spectro-Temporal ECG Arrhythmia Classification 🫀📊

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Advanced_CNN-EE4C2C)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Traditional_ML-F7931E)
![Dataset](https://img.shields.io/badge/Dataset-MIT--BIH-green)

This repository contains the complete code and methodology for a highly robust Electrocardiogram (ECG) classification system. The project focuses on distinguishing **Normal beats (N)** from **Premature Ventricular Contractions (PVC / V)** using the benchmark MIT-BIH Arrhythmia Database.

The core innovation of this pipeline is the transformation of raw 1D time-series ECG signals into **2D Time-Frequency Spectrograms** via the Short-Time Fourier Transform (STFT). This allows us to classify arrhythmias using an **Advanced 2D Convolutional Neural Network (CNN)** engineered to handle severe clinical class imbalance.

---

## 📂 Dataset Overview & Link

**Dataset Name:** MIT-BIH Arrhythmia Database v1.0.0  
**Official Link:** [https://physionet.org/content/mitdb/1.0.0/](https://physionet.org/content/mitdb/1.0.0/)

*Note: You do not need to download this manually to run the code. The Python `wfdb` library included in the script will automatically connect to the PhysioNet server and download the required patient records into a local `mitdb/` folder during your first run.*

---

## 🛠️ Installation & Setup

**Prerequisites:** Ensure you have Python 3.8+ installed. It is highly recommended to use a virtual environment or run this inside a Google Colab / Jupyter Notebook.

1. **Clone the repository** (or download the script directly):
   ```bash
   git clone <your-repository-url>
   cd <repository-folder>
