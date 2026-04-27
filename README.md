🫀 ECG Arrhythmia Classification using ML & Deep Learning

This project focuses on detecting cardiac arrhythmias (PVC vs Normal beats) using both traditional machine learning models and an advanced 2D CNN, trained on ECG signals transformed into spectrogram images.

📌 Overview

Electrocardiogram (ECG) signals are time-series data representing heart activity. This project:

Extracts heartbeat segments from ECG signals
Converts them into 2D spectrogram images
Compares 6 ML models + 1 Deep Learning model
Uses strict patient-wise splitting (real-world scenario)
📂 Dataset

We use the MIT-BIH Arrhythmia Dataset.

📎 Source: https://physionet.org/content/mitdb/1.0.0/
📦 Access via wfdb Python package
Records Used
Training Patients: 100, 119, 200
Testing Patient (Unseen): 214

⚠️ This ensures no data leakage — model is tested on a completely unseen patient.

⚙️ Installation
pip install torch numpy wfdb matplotlib seaborn scipy scikit-learn
🚀 Pipeline
1. Data Extraction
Extract ECG signals using wfdb
Use annotations to locate heartbeats
Window each beat:
window_size = 150
Total beat length = 300 samples
2. Label Mapping
Symbol	Class
N	0 (Normal)
V	1 (Arrhythmia - PVC)
3. 1D → 2D Conversion

Each heartbeat is converted into a spectrogram:

signal.spectrogram(beat, fs=360, nperseg=32, noverlap=30)

This transforms time-series ECG into an image-like representation.

4. Models Used
🧠 Traditional ML Models
Random Forest
Logistic Regression
Support Vector Machine (RBF)
K-Nearest Neighbors
Naive Bayes
Gradient Boosting
🤖 Deep Learning Model
Advanced 2D CNN
🧱 CNN Architecture
Input (1 × H × W Spectrogram)

→ Conv2D (32) + BatchNorm + ReLU + MaxPool
→ Conv2D (64) + BatchNorm + ReLU + MaxPool
→ Conv2D (128) + BatchNorm + ReLU
→ AdaptiveAvgPool (4×8)

→ Flatten
→ Dense (128) + Dropout (0.5)
→ Output (2 classes)
⚖️ Handling Class Imbalance

MIT-BIH dataset is highly imbalanced.

We fix this using:

class_weights = [1.0, imbalance_ratio]
CrossEntropyLoss(weight=class_weights)

This ensures the model pays more attention to arrhythmia beats.

🏋️ Training Details
Optimizer: Adam
Learning Rate: 0.0005
Epochs: 15
Batch Size: 32
📊 Evaluation
Metric: Accuracy
Tested on completely unseen patient (Record 214)
📈 Output

The project generates:

✅ Signal Visualization
1D ECG signals (Normal vs PVC)
2D Spectrogram images
✅ Model Comparison Chart
Barplot comparing all models
