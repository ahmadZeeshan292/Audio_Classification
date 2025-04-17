# 🎧 Audio Classification using Deep Learning

![Python](https://img.shields.io/badge/Language-Python-blue)
![Deep Learning](https://img.shields.io/badge/Model-CNN-green)
![Dataset](https://img.shields.io/badge/Dataset-UrbanSound8K-orange)
![Status](https://img.shields.io/badge/Project-Audio_Classifier-brightgreen)

---

## 📌 Project Overview

This project aims to classify audio signals into three primary categories: **Speech**, **Music**, and **Noise**, using a combination of **signal processing techniques** and **deep learning**. The classification system is trained on the **UrbanSound8K dataset** and leverages **Mel-Frequency Cepstral Coefficients (MFCCs)**, **spectrograms**, and **Convolutional Neural Networks (CNNs)** to achieve robust classification.

---

## 🎯 Objectives

- **Understand audio signals** and their classification needs.
- **Preprocess** audio using resampling and filtering.
- **Extract features** such as MFCCs, Zero Crossing Rate (ZCR), and Root Mean Square (RMS).
- **Generate spectrograms** for visual frequency representation.
- **Train and evaluate** a CNN model for multi-label audio classification.

---

## 📁 Dataset

- **UrbanSound8K**: A real-world dataset containing 8,732 labeled audio clips from 10 categories (siren, dog bark, street music, engine idling, etc.).
- Each clip is annotated with timestamps, classes, and metadata.
- Data is split into 70% training and 30% testing.

---

## 🧪 Signal Processing Pipeline

1. **.wav File Handling**: File paths and corresponding labels stored in a hashmap.
2. **File Validation**: Corrupted files are automatically skipped.
3. **One-Hot Encoding**: Labels are encoded into vectors for multi-label compatibility.
4. **Audio Decoding & Resampling**:
   - Resampled to **16 kHz**.
   - Converted to **mono channel**.
   - Standardized to **3 seconds** (padded or truncated).

---

## 📊 Feature Extraction

- **MFCCs**: Extracted to represent short-term power spectrum of sounds.
- **Spectrograms**: Time-frequency domain visualizations generated from audio clips.
- Each spectrogram acts as an input image to the CNN model.

---

## 🧠 Model Architecture

### Convolutional Neural Network (CNN)

- Inputs: Spectrograms (standardized in shape)
- Output: A multi-label prediction vector
- Loss Function: Categorical cross-entropy (multi-label)
- Optimized with: Adam optimizer
- Training strategy includes **batching**, **prefetching**, and **caching** for speed.

---

## ✅ Confidence Thresholding

After prediction:

- Outputs **> 70% confidence** are marked as **positive (1)**.
- Outputs **< 30% confidence** are marked as **negative (0)**.
- Values in between are **conservatively handled** to avoid false positives.

---

## 📈 Evaluation

- Accuracy was tested using a dedicated testing function.
- Metrics like **precision**, **recall**, and **F1-score** were used to evaluate model performance.
- Spectrogram visualization and prediction outputs help verify classification decisions.

---

## 🧰 Libraries & Tools Used

- `tensorflow`, `tensorflow_io`: For neural network training and audio decoding.
- `numpy`, `pandas`: For data manipulation.
- `sklearn`: For label encoding and evaluation.
- `matplotlib`: For visualization.
- `pickle`: For saving/loading models.
- `os`, `wave`: For file and audio handling.

---

## 🧠 Learning Outcomes

- Integrated **signal processing** with **deep learning** for real-world classification.
- Demonstrated robust model performance even under noisy, urban conditions.
- Highlighted the usefulness of MFCCs and spectrograms in audio classification tasks.

