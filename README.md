# Deep Learning for Audio-Based Respiratory Disease Classification Using Clinical Sound Data

## Overview
This project aims to classify respiratory sounds into "healthy" or "disease" categories, followed by further classification of detected diseases as "COPD" or "non-COPD." By implementing a two-step classification approach, we aim to improve diagnostic accuracy by first identifying potential respiratory abnormalities, then distinguishing specific conditions. The project will use custom models (CNN + RNN, CNN + LSTM, and CNN + SVM) and apply targeted data augmentation techniques to address the challenge of balancing class distributions, particularly for the "healthy" label.

[**Dataset Link**](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database/data)

## Table of Contents
- [Project Motivation](#project-motivation)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Approach](#approach)
- [Results](#results)

<a name="project-motivation"></a>
## 1. Project Motivation
Respiratory sounds reflect various respiratory conditions, such as asthma and COPD, which are often detected through distinct audio patterns like crackles and wheezes. Traditional diagnostic methods involve manual interpretation by medical professionals. This project leverages deep learning to automate and improve these diagnostic processes, using custom architectures to classify respiratory sound data for accurate disease detection.

<a name="dataset"></a>
## 2. Dataset
The **Respiratory Sound Database** from Kaggle includes over 900 recordings of respiratory cycles from 126 patients, capturing a variety of respiratory conditions across age groups. Key details:

- **920 .wav audio files** and **annotations** for respiratory sounds (crackles and wheezes)
- **5.5 hours of recordings** with diverse audio conditions
- **Diagnosis data** listing conditions for each patient (COPD, LRTI, URTI, etc.)
- **Demographic data** including age, sex, and BMI

**Key Audio Features:**
- **6898 respiratory cycles** annotated with:
  - 1864 cycles with crackles
  - 886 cycles with wheezes
  - 506 cycles with both

### Audio File Naming Convention
Files are named as follows: `PatientNumber_RecordingIndex_ChestLocation_AcquisitionMode_RecordingEquipment.wav`  
Example: `101_1_Al_sc_Litt3200.wav`

For more information, visit the [Kaggle Dataset Page](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database/data).

<a name="project-structure"></a>
## 3. Project Structure

```
.
├── data
│   ├── Respiratory_Sound_Database
│   ├── processed_data
├── notebooks
│   ├── 01_data_exploration.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_model_training.ipynb
├── src
│   ├── data_preprocessing.py
│   ├── model.py
│   ├── evaluation.py
├── requirements.txt
├── README.md
```

- `data/`: Contains the raw respiratory sound data and processed data.
- `notebooks/`: Jupyter notebooks for exploration, preprocessing, and training.
- `src/`: Scripts for data preprocessing, model building, and evaluation.
- `requirements.txt`: Lists all dependencies.

<a name="approach"></a>
## 4. Approach

### 4.1 Data Preprocessing
- **Audio Features:** The project uses audio features including Chromagram (CR), Root Mean Square (RMS), Spectral Centroid (SC), Bandwidth, Spectral Roll-Off (SR), Tonnetz (T), Mel-Frequency Cepstral Coefficient (MFCC), Zero Crossing Rate (ZCR), and Polynomial Coefficients (Poly).
- **Annotation Alignment:** Align audio files with their crackles and wheezes labels for accurate training.

### 4.2 Data Augmentation
Balancing the "healthy" class is a specific challenge in this project. We will use a range of audio augmentation techniques to increase the dataset size for this label while ensuring data quality remains high. Common augmentations applied to respiratory sound data include:

- **Noise Addition**: Adding white noise to simulate real-world recording environments and increase model robustness.
- **Pitch Shifting**: Adjusting the pitch without altering the speed to introduce slight variations in sound.
- **Time Stretching**: Slightly changing the speed of the audio without affecting pitch, useful for creating variance.
- **Equalization and Filtering**: Applying filters to emphasize certain frequencies and reduce background noise.
- **Reverberation**: Adding room-like echo effects to simulate different environments.

### 4.3 Model Selection
- **Custom Architectures**: Develop and compare CNN + RNN, CNN + LSTM, and CNN + SVM architectures to determine the optimal approach for respiratory sound classification.

### 4.4 Evaluation
- **Metrics**: Evaluate models using accuracy, precision, recall, and F1-score.
- **Cross-Validation**: Perform k-fold cross-validation to ensure model robustness.

<a name="results"></a>
## 5. Results
The project evaluates each model's performance on the test set, with results displayed through:
- Confusion matrices
- ROC and Precision-Recall curves
- Summary statistics for each model's accuracy, recall, and precision
