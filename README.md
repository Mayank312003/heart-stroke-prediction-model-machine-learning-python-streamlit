# 🫀 Heart Stroke Risk Prediction

A machine learning-powered web application that predicts a user's risk of heart stroke based on clinical health parameters.

---

## 📌 Project Overview

Heart disease is one of the leading causes of death worldwide. Early detection of stroke risk can save lives. This project builds an end-to-end ML pipeline - from raw data analysis to a deployed interactive web application - that allows individuals to input their health details and instantly receive a risk assessment.

---

## 🖥️ Application Preview

The app provides an intuitive form where users input their health details and click **Predict** to receive either a **Low Risk** ✅ or **High Risk** ⚠️ result.

**Input Parameters:**
- Age (slider: 18–100)
- Sex
- Chest Pain Type (ATA, NAP, ASY, TA)
- Resting Blood Pressure (mm Hg)
- Cholesterol (mg/dL)
- Fasting Blood Sugar > 120 mg/dL
- Resting ECG (Normal, LVH, ST)
- Max Heart Rate (slider)
- Exercise-Induced Angina
- Oldpeak / ST Depression (slider: 0.00–6.00)
- ST Slope (Up, Flat, Down)

---

## 🔬 Project Workflow

### 1. Exploratory Data Analysis (EDA)
- Explored distributions, correlations, and class imbalance
- Identified key features influencing stroke risk

### 2. Data Visualization
- Plotted feature distributions, heatmaps, and pair plots
- Visualized relationships between clinical features and target variable

### 3. Data Preprocessing & Feature Scaling
- Handled missing/null values
- Encoded categorical variables
- Applied feature scaling using `StandardScaler`

### 4. Train-Test Split
- Split dataset into training and testing sets (typically 80/20)

### 5. Model Training & Evaluation

Trained and compared multiple classification models:

| Model | Notes |
|---|---|
| Logistic Regression | Baseline model |
| K-Nearest Neighbors (KNN) | ✅ Best performer |
| Support Vector Machine (SVM) | |
| Naive Bayes | |
| Decision Tree Classifier | |

**Best Model: K-Nearest Neighbors (KNN)**

| Metric | Score |
|---|---|
| Accuracy | **86%** |
| F1 Score | **88%** |

### 6. Model Serialization
- Saved the trained KNN model, scaler, and feature columns using `joblib`

```python
import joblib
joblib.dump(knn_model, 'knn_model.pkl')
joblib.dump(scaler, 'scaler.pkl')
joblib.dump(columns, 'columns.pkl')
```

### 7. Web Application
- Loaded serialized artifacts in VS Code
- Built an interactive frontend with input widgets (sliders, dropdowns, number inputs)
- Displays prediction result with color-coded risk alerts

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Data Analysis | Python, Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| ML Modeling | Scikit-learn |
| Model Serialization | Joblib |
| Web App | Streamlit |
| IDE | Jupyter Notebook, VS Code |

---

## 📁 Project Structure

```
heart-stroke-prediction/
│
├── notebook/
│   └── heart_stroke_prediction.ipynb   # EDA, preprocessing, model training
│
├── models/
│   ├── knn_model.pkl                   # Trained KNN model
│   ├── scaler.pkl                      # Fitted StandardScaler
│   └── columns.pkl                     # Feature column names
│
├── app.py                              # Streamlit web application
├── requirements.txt
└── README.md
```

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/heart-stroke-prediction.git
   cd heart-stroke-prediction
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**
   ```bash
   streamlit run app.py
   ```

4. **Open in browser**
   ```
   http://localhost:8501
   ```

---

## 📊 Results

- The **KNN classifier** outperformed all other tested models.
- Achieved **86% accuracy** and **88% F1 score** on the test set.
- The F1 score being higher than accuracy indicates good performance on both precision and recall — important in a medical context where false negatives are costly.

---

## 📋 Requirements

```
pandas
numpy
scikit-learn
joblib
streamlit
matplotlib
seaborn
```

---

## ⚠️ Disclaimer

This application is intended for **educational purposes only** and should not be used as a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider for medical concerns.

---

## 👤 Author

**Mayank Yadav**  
**Aspiring Data Scientist | Machine Learning Engineer | Data Analyst**
[GitHub](https://github.com/Mayank312003) | [LinkedIn](https://linkedin.com/in/mayankyadav1001/)
