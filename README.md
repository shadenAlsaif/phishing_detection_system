# phishing_detection_system
# 🔐 AI-Powered Phishing & Intrusion Detection System

This project focuses on building intelligent models for detecting **phishing attacks** and **network intrusions** using machine learning and neural networks. It combines two cybersecurity domains into a unified approach that enhances the reliability of online safety systems.

---

## 🧠 Project Overview
Cyberattacks such as phishing and network intrusions are among the most common threats in modern digital environments.  
This project aims to:
- Detect **malicious or phishing URLs** using statistical and structural features.
- Classify **network activity** as normal or intrusive using machine learning.
- Compare the performance of classical algorithms with a neural network model.
- Visualize model accuracy, feature importance, and ROC curves.

---

## 📂 Datasets
1. **Phishing Detection Dataset**
   - Source: [Kaggle - Web Page Phishing Detection Dataset](https://www.kaggle.com/datasets/shashwatwork/web-page-phishing-detection-dataset)
   - Description: Contains 11,430 records with 89 extracted URL features.
   - Labels:  
     - `legitimate` (0)  
     - `phishing` (1)
   - Example features:
     - `length_url`, `ip`, `nb_dots`, `ratio_digits_url`, `char_repeat`

2. **Intrusion Detection Dataset** *(if included in your second notebook)*  
   - Example sources: NSL-KDD / CICIDS2017 datasets.
   - Features: Network traffic parameters (protocol, bytes, duration, etc.).
   - Goal: Detect abnormal packets and potential intrusions.

---

## ⚙️ Preprocessing & Feature Engineering
- Removal of non-numeric / irrelevant columns (e.g., URL text).
- Label encoding (`legitimate → 0`, `phishing → 1`).
- Standardization using `StandardScaler`.
- Feature selection with **SelectKBest + mutual_info_classif** to retain top 30 features.

---

## 🧩 Models Implemented
1. **Decision Tree Classifier**
2. **Random Forest Classifier**
3. **Support Vector Machine (RBF Kernel)**
4. **Neural Network (Keras Sequential Model)**  
   - Layers:
     - Dense(64, relu) → Dropout(0.3)
     - Dense(32, relu)
     - Dense(1, sigmoid)

---

## 🧮 Evaluation Metrics
- Accuracy  
- Precision  
- Recall  
- F1-Score  
- ROC Curve & AUC  
- Confusion Matrix Visualization

---

## 📊 Results Summary

| Model          | Accuracy | Precision | Recall | F1 Score |
|----------------|-----------|------------|---------|-----------|
| Random Forest  | **0.9567** | 0.9531 | 0.9606 | **0.9569** |
| Neural Network | 0.9501 | 0.9517 | 0.9484 | 0.9500 |
| SVM (RBF)      | 0.9436 | 0.9416 | 0.9458 | 0.9437 |
| Decision Tree  | 0.9326 | 0.9318 | 0.9335 | 0.9327 |

✅ **Random Forest** achieved the best overall performance with high F1 and AUC scores.

---

## 📈 Visualizations
- Class distribution (Legitimate vs Phishing)
- URL feature distributions (`length_url`, `nb_dots`, etc.)
- Confusion matrices for all models
- ROC curves comparison
- Top 10 most important features (for tree models)

---

## 🚀 How to Run
```bash
# 1. Clone this repository
git clone https://github.com/shadenAlsaif/phishing_detection_and_intrusion_system.git
cd phishing_detection_and_intrusion_system

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
jupyter notebook AI_for_CS_Assignment4.ipynb
