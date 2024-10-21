# Deep Learning for Audio-Based Respiratory Disease Classification Using Clinical Sound Data

## Overview
This project aims to develop a machine learning model capable of classifying respiratory sounds into specific respiratory diseases, using the **Respiratory Sound Database** from Kaggle. The model will leverage pretrained models and commonly used audio libraries to detect conditions such as asthma, chronic obstructive pulmonary disease (COPD), pneumonia, and bronchiolitis from respiratory sound recordings. By harnessing the power of machine learning, this project hopes to contribute to advancements in medical diagnosis.

[**Dataset Link**](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database/data)

## Table of Contents
- [Project Motivation](#project-motivation)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Approach](#approach)
- [Results](#results)
- [Contributing](#contributing)

<a name="project-motivation"></a>
## 1. Project Motivation
Respiratory sounds are critical indicators of lung health, often reflecting the presence of respiratory disorders. Conditions like asthma and COPD can be identified by sounds like wheezes and crackles. Traditionally, diagnosing these diseases involves manual interpretation by healthcare professionals, but with the rise of machine learning, there is an opportunity to automate and potentially improve the accuracy and speed of these diagnoses. This project explores various pretrained models and audio analysis techniques to develop a reliable classification model for respiratory sound data.

<a name="dataset"></a>
## 2. Dataset
The dataset used in this project is the **Respiratory Sound Database**, containing over 900 recordings from 126 patients across all age groups. The key features of the dataset include:

- **920 .wav audio files** representing respiratory cycles
- **920 annotation files** with labels for crackles and wheezes
- **5.5 hours of recordings** with both clean and noisy audio samples simulating real-world conditions
- **Diagnosis file** listing the respiratory condition for each patient (COPD, LRTI, URTI, etc.)
- **Demographic information** (age, sex, BMI, weight, height)

### Key Audio Features:
- **6898 respiratory cycles** with:
  - 1864 cycles containing crackles
  - 886 cycles containing wheezes
  - 506 cycles containing both

### File Naming Convention:
Each audio file has a name structure: `PatientNumber_RecordingIndex_ChestLocation_AcquisitionMode_RecordingEquipment.wav`

Example: `101_1_Al_sc_Litt3200.wav`

The dataset provides detailed information on the chest location, acquisition mode, and the equipment used, which could be useful for advanced analysis.

For more details about the dataset, visit the [Kaggle Dataset Page](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database/data).

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

- `data/`: Contains the raw respiratory sound data from Kaggle and preprocessed data.
- `notebooks/`: Jupyter notebooks for data exploration, preprocessing, and model training.
- `src/`: Python scripts for data preprocessing, model building, and evaluation.
- `requirements.txt`: Lists all dependencies needed for the project.

<a name="approach"></a>
## 4. Approach

### 4.1 Data Preprocessing
- **Audio Preprocessing:** Convert the .wav files into a format suitable for model input, using techniques like short-time Fourier transform (STFT), Mel-spectrograms, and feature extraction (MFCCs).
- **Annotation Alignment:** Align audio files with their corresponding labels (crackles, wheezes).
- **Data Augmentation:** Apply techniques like noise addition, pitch shifting, and time stretching to increase the training data size.

### 4.2 Model Selection
- **Pretrained Models:** Explore audio classification models such as VGGish, YAMNet, and other deep learning architectures fine-tuned for medical sound classification.
- **Custom Model:** Develop a custom CNN or RNN-based model tailored to the characteristics of respiratory sounds.

### 4.3 Evaluation
- **Metrics:** Use accuracy, precision, recall, and F1-score to evaluate the model’s performance.
- **Cross-Validation:** Apply k-fold cross-validation to ensure robustness of the model across different subsets of the data.

<a name="result"></a>
## 5. Results

The model's performance on the test set will be evaluated based on its ability to classify respiratory sounds into categories like crackles, wheezes, and normal sounds. Results will include:
- Confusion matrices
- ROC curves
- Precision-recall curves
