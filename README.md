# 🫁 Lung Cancer Survival Prediction

This project builds a machine learning pipeline to predict whether a lung cancer patient is likely to survive, based on a rich set of medical and demographic features. The dataset contains clinical and lifestyle information that is processed, encoded, and modeled using a classification algorithm.

---

## 📌 Objective

To predict the **survival outcome** of a patient diagnosed with lung cancer using their health and treatment data.

---

## 📊 Dataset

The dataset includes over 800,000 records with the following features:

- `id`: Unique patient identifier (dropped in preprocessing)
- `age`: Age at diagnosis
- `gender`: Male / Female
- `country`: Patient's country
- `diagnosis_date`: Date of diagnosis
- `cancer_stage`: Stage I-IV
- `family_history`: History of cancer in family
- `smoking_status`: Smoking habit (current, former, passive, etc.)
- `bmi`: Body Mass Index
- `cholesterol_level`: Cholesterol value
- `hypertension`, `asthma`, `cirrhosis`, `other_cancer`: Comorbidities (binary)
- `treatment_type`: Type of treatment (surgery, chemo, radiation, etc.)
- `end_treatment_date`: Date treatment ended or death occurred
- `survived`: Target variable — did the patient survive?

---

## 🧹 Preprocessing

- Dropped irrelevant columns like `id`.
- Converted date fields to datetime objects.
- Created a new feature: `treatment_duration` (days between diagnosis and end of treatment).
- Dropped original date fields.
- Filled missing values using **mode** imputation.
- Encoded categorical variables using **LabelEncoder**.
- Standardized numerical features with **StandardScaler**.
- Applied **SMOTE** to handle class imbalance.

---

## 🤖 Model

A **Random Forest Classifier** was trained with the following setup:

- Dataset split: 80% training / 20% testing
- Oversampling used: SMOTE
- No custom hyperparameters (vanilla RandomForest)
- Evaluation metrics:
  - **Accuracy**: 80.9%
  - **ROC-AUC**: 88.1%
  - **Classification Report**: Precision, Recall, F1-score all ≈ 0.81

---

## 📈 Feature Importance

The most influential features as per Random Forest:

- `treatment_duration`
- `cancer_stage`
- `cholesterol_level`
- `age`
- `bmi`

---

## 📦 Libraries Used

- `pandas`
- `numpy`
- `sklearn`
- `imblearn`
- `matplotlib`
- `seaborn`

---

## 📉 Visuals

- Confusion matrix heatmap
- Feature importance bar chart

---

## 🚀 Future Work

- Hyperparameter tuning (GridSearchCV or RandomizedSearchCV)
- Try alternate models (XGBoost, Logistic Regression, SVM)
- Build a web interface using Streamlit or Flask
- Deploy via Docker or cloud (Heroku, AWS, etc.)

---

## 👨‍⚕️ Use Case

Can assist medical practitioners in risk stratification of lung cancer patients and potentially aid in personalized treatment planning.

---

# Disclimer
This Project is Built with a Intent to Learn Not to Deploy in real world and it needs way more dataset to even scatch the real thing.......
