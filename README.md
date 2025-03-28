## 🧠 Candidemia Mortality Prediction

### 📌 Project Overview

This project was developed as part of the **Artificial Intelligence course at NYCU (Spring 2024)**.  
The goal was to predict **14-day mortality** in patients diagnosed with candidemia using various **machine learning algorithms**.

### 📊 Dataset

- **409 patient records**
- **77 clinical features**
- **Binary target:** `Dead_in_14` (whether the patient died within 14 days)

The dataset had a **class imbalance** (approx. 30% positive class), and preprocessing was essential to ensure valid model training.

### ⚙️ Methodology

1. **Exploratory Data Analysis (EDA):**
   - Identified feature distributions, class imbalance, correlations
2. **Preprocessing:**
   - Outlier capping using IQR
   - Missing value imputation (mean for numerics, mode for booleans)
   - Feature selection using Random Forest importance + `SelectKBest`
   - Scaling for sensitive models (e.g., SVM, KNN)
3. **Model Training:**
   - Implemented and evaluated:
     - Random Forest
     - AdaBoost
     - K-Nearest Neighbors
     - Support Vector Machine (SVM)
4. **Optimization:**
   - Used `RandomizedSearchCV` to tune hyperparameters
   - Created full pipelines with preprocessing, feature selection, and modeling
   - Threshold tuning for better precision-recall balance

### 🏆 Results

| Model         | F1 Score | AUC-ROC |
|---------------|----------|---------|
| Random Forest | 0.57     | 0.69    |
| AdaBoost      | 0.65     | 0.76    |
| **SVM**       | **0.68** | **0.78** |

**SVM** was selected as the final model for its strong performance and better generalization.
