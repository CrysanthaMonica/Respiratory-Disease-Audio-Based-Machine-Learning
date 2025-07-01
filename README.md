# Deep Learning for Audio-Based Respiratory Disease Classification

This project explores the use of hybrid deep learning models for classifying respiratory diseases using clinical sound data. It focuses on distinguishing between COPD and non-COPD cases (including healthy and six other diseases) through audio signal analysis, feature extraction, and model evaluation.

## 📁 Dataset

We used the [Respiratory Sound Database](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database) consisting of 5,539 audio recordings (.wav) from 126 patients. The original labels included:
- COPD
- URTI
- Bronchiectasis
- Bronchiolitis
- Pneumonia
- LRTI
- Asthma
- Healthy

For this study, the labels were simplified into **2 classes**:
- COPD
- non-COPD (includes healthy and other 6 diseases)

## 🎯 Objective

To classify respiratory audio into COPD vs. non-COPD using hybrid deep learning models:
- CNN + LSTM
- CNN + RNN
- CNN + SVM

and compare their performance against baseline models.

## ⚙️ Methods

### 1. **Preprocessing**
- **Noise reduction** using pre-emphasis
- **Normalization** and amplitude scaling
- **Padding** to standardize audio length (5 seconds)
- **Data augmentation**:
  - Gaussian noise injection
  - Time stretching

### 2. **Feature Extraction**
Extracted features:
- MFCC (13)
- Chromagram (12)
- RMS, Spectral Centroid, Bandwidth, Roll-Off
- Tonnetz (6), Polynomial Coefficients (1)
- Zero-Crossing Rate (ZCR)

Total: **37 features**

### 3. **Model Architecture**
Implemented and compared:
- **Hybrid Models**: CNN+LSTM, CNN+RNN, CNN+SVM
- **Baselines**: CNN, RNN, LSTM, SVM

Training configuration:
- Epochs: 300  
- Batch size: 64  
- Dropout: 0.2–0.4  
- Optimizer: Adam  
- No early stopping (to ensure fair comparison)

### 4. **Evaluation Metrics**
- Accuracy
- Precision
- Recall
- F1-Score
- ROC AUC
- 95% Confidence Interval
- p-values (to ensure statistical significance)

## 📊 Results

| Model        | Accuracy | F1-Score (COPD) | F1-Score (non-COPD) |
|--------------|----------|------------------|----------------------|
| CNN + LSTM   | 88%      | 0.92             | 0.87                 |
| CNN + SVM    | 83%      | 0.86             | 0.78                 |
| CNN + RNN    | 63%      | 0.62             | 0.65                 |
| LSTM         | 95%      | 0.96             | 0.94                 |
| CNN          | 89%      | 0.91             | 0.87                 |
| RNN          | 68%      | 0.66             | 0.70                 |

Best performing model: **CNN + LSTM**  
However, **LSTM alone** performed comparably or better in some metrics.

## 📌 Key Insights

- CNN+LSTM showed strong performance due to temporal learning
- CNN+SVM performed reliably with strong decision boundaries
- CNN+RNN struggled with temporal dependencies and overfitting
- Feature extraction and balanced augmentation improved generalizability
- All models remained robust across 4 different recording devices

## 🧪 Tools & Libraries

- Python, TensorFlow, Keras, Scikit-learn
- Librosa (feature extraction)
- NumPy, pandas, Matplotlib, Seaborn

## 🔐 Ethics & Privacy

- Dataset licensed for academic research use
- Recommendation: future improvements to include **federated learning** and privacy-preserving frameworks for sensitive medical data

## 👨‍💻 Authors

- **Crysantha Monica Lim** – Framework design, experiments  
- **Cherylene Callista Reksohartono** – Analysis, interpretation, manuscript  
- **Alexander Agung Santoso Gunawan** – Supervisor  
- **Jeffrey Junior Tedjasulaksana** – Supervisor

## 📂 License

This project is for academic and research purposes only.  
Dataset: [Respiratory Sound Database](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database)  
