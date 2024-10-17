# Harnessing Machine Learning for Audio-Based Respiratory Disease Classification Using Clinical Sound Data 

## Overview
This project aims to develop a machine learning model capable of classifying respiratory sounds into specific respiratory diseases, using the **Respiratory Sound Database** from Kaggle. The model will leverage pretrained models and commonly used audio libraries to detect conditions such as asthma, chronic obstructive pulmonary disease (COPD), pneumonia, and bronchiolitis from respiratory sound recordings. By harnessing the power of machine learning, this project hopes to contribute to advancements in medical diagnostics through automated sound analysis.

[**Dataset Link**](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database/data)

## Table of Contents
1. [Project Motivation](#motivation)
2. [Dataset](#dataset)
3. [Installation](#installation)
4. [Project Structure](#structure)
5. [Approach](#approach)
6. [Results](#results)
7. [Contributing](#contributing)
8. [License](#license)

## 1. Project Motivation
Respiratory sounds are critical indicators of lung health, often reflecting the presence of respiratory disorders. Conditions like asthma and COPD can be identified by sounds like wheezes and crackles. Traditionally, diagnosing these diseases involves manual interpretation by healthcare professionals, but with the rise of machine learning, there is an opportunity to automate and potentially improve the accuracy and speed of these diagnoses. This project explores various pretrained models and audio analysis libraries to classify respiratory diseases based on sound recordings.

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
