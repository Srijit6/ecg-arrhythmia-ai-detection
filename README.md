# ECG Arrhythmia Classification 

This repository provides a complete end-to-end pipeline to classify cardiac arrhythmias using two-lead ECG signal features extracted from the MIT-BIH Arrhythmia and other related PhysioNet datasets. It implements preprocessing, visualization, feature selection, and various classification models including XGBoost and MLP.

---

## 📊 About the Dataset

We use feature-extracted ECG data from four well-known PhysioNet sources:

- **MIT-BIH Arrhythmia Database**
- **MIT-BIH Supraventricular Arrhythmia Database**
- **St. Petersburg INCART 12-lead Arrhythmia Database**
- **Sudden Cardiac Death Holter Database**

Each dataset includes 2-lead ECG features (lead II and V), and five heartbeat classes:
- `N`: Normal
- `S`: Supraventricular ectopic beat
- `V`: Ventricular ectopic beat
- `F`: Fusion beat
- `Q`: Unknown beat

Each record contains:
- **1 column** for patient ID (`record`)
- **1 column** for class label (`type`)
- **34 features** → 17 features per lead:
  - RR Intervals: `pre-RR`, `post-RR`, `Average RR`
  - Time-based intervals: `PQ Interval`, `QT Interval`, `ST Interval`, `QRS Duration`
  - Amplitude-based features: `P Peak`, `Q Peak`, `R Peak`, `S Peak`, `T Peak`
  - Morphological features: `QRS Morph feature 0` through `4`

📎 Dataset Source: [PhysioNet](https://physionet.org/)

---

## 🚀 Project Pipeline

### 🔹 1. Data Preprocessing
- Load and clean MIT-BIH dataset
- Inspect missing/null values
- Visualize class distribution and feature histograms

### 🔹 2. Feature Analysis
- Correlation heatmaps
- Class-wise boxplots
- PCA (Principal Component Analysis)
- t-SNE Visualization

### 🔹 3. Feature Selection
- `SelectKBest` with ANOVA F-statistic
- Recursive Feature Elimination (RFE) with Random Forest

### 🔹 4. Modeling
- Baseline: Random Forest
- Advanced ML: XGBoost
- Deep Learning: MLP using TensorFlow/Keras

### 🔹 5. Evaluation
- Accuracy, Precision, Recall, F1-score
- Confusion Matrix
- ROC Curve (Multiclass)
- Training curves (Loss vs Epoch)

---

## 📁 Repository Structure
```
    ecg-arrhythmia-classification-ml/
    ├── ECG_Arrhythmia_Classification_MITBIH.ipynb # Main notebook
    ├── README.md
    ├── requirements.txt (optional)
    └── /data
    ├── MIT-BIH Arrhythmia Database.csv
    ├── MIT-BIH Supraventricular Arrhythmia Database.csv
    ├── INCART 2-lead Arrhythmia Database.csv
    └── Sudden Cardiac Death Holter Database.csv
```


---

## 🧪 Results

| Model         | Accuracy | Precision | Recall | F1 Score |
|---------------|----------|-----------|--------|----------|
| Random Forest | ~96%     | High      | High   | High     |
| XGBoost       | ~97%     | High      | High   | High     |
| MLP           | ~98%     | High      | High   | High     |

*Note: Final metrics vary slightly depending on selected features and train/test splits.*

---

## 🛠️ How to Run

### ▶️ Option 1: Run on Kaggle
Upload the dataset and notebook in a Kaggle kernel and execute.

### ▶️ Option 2: Run Locally

```bash
git clone https://github.com/yourusername/ecg-arrhythmia-classification-ml.git
cd ecg-arrhythmia-classification-ml
pip install -r requirements.txt  # if you include one
jupyter notebook
```
📚 References
Dataset Source: PhysioNet - MIT-BIH Arrhythmia

Feature extraction method:

"Harnessing Artificial Intelligence for Secure ECG Analytics at the Edge for Cardiac Arrhythmia Classification"


⚠️ Disclaimer
``` This project is intended for educational and research purposes only. It is based on publicly available ECG datasets and is not validated for clinical or production use in hospitals.```

📌 Inspiration
This project was inspired by the need to develop a proof-of-concept AI pipeline for heartbeat classification using machine learning (ML) techniques. It can serve as a foundation for clinical research or student projects in biomedical signal processing and healthcare AI.

---
#### uwu
---
  
