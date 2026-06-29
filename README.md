# ❤️ Heart Disease Prediction App

A Streamlit web app that predicts the risk of heart disease based on a patient's clinical and demographic data, using a trained Logistic Regression model.

## 🔍 Overview

This app takes in basic health parameters through an interactive UI and predicts whether a person is at **high risk** or **low risk** of heart disease, using a model trained on the UCI Heart Failure Prediction dataset.

## 📁 Project Structure

```
.
├── app.py              # Streamlit application
├── heart.csv           # Training dataset (918 patient records)
├── logic_heart.pkl     # Trained Logistic Regression model
├── scaler.pkl          # StandardScaler used for feature scaling
└── columns.pkl         # Expected feature columns (post one-hot encoding)
```

## 🧠 Model Details

- **Algorithm:** Logistic Regression (scikit-learn)
- **Preprocessing:** StandardScaler for numerical features, one-hot encoding for categorical features
- **Dataset:** 918 patient records with 11 clinical features + target (`HeartDisease`)

### Features used
| Feature | Description |
|---|---|
| Age | Patient's age |
| Sex | Male / Female |
| ChestPainType | ATA, NAP, TA, ASY |
| RestingBP | Resting blood pressure (mm Hg) |
| Cholesterol | Serum cholesterol (mg/dL) |
| FastingBS | Fasting blood sugar > 120 mg/dL (1 = true, 0 = false) |
| RestingECG | Normal, ST, LVH |
| MaxHR | Maximum heart rate achieved |
| ExerciseAngina | Exercise-induced angina (Y/N) |
| Oldpeak | ST depression induced by exercise |
| ST_Slope | Slope of the peak exercise ST segment (Up, Flat, Down) |

## 🚀 Running the App

### 1. Install dependencies
```bash
pip install streamlit pandas scikit-learn joblib
```

### 2. Run the app
```bash
streamlit run app.py
```

### 3. Use the app
Fill in the patient details in the form and click **Predict** to see the result:
- 🚨 **High Risk of Heart Disease**
- ✅ **Low Risk of Heart Disease**

## ⚙️ How It Works

1. User inputs are collected via Streamlit widgets (sliders, dropdowns, number inputs)
2. Categorical inputs are manually one-hot encoded to match the training format
3. Missing expected columns (from `columns.pkl`) are filled with 0 to align with the model's training schema
4. Input is scaled using the saved `scaler.pkl`
5. The scaled input is passed to the trained model (`logic_heart.pkl`) for prediction

## ⚠️ Disclaimer

This app is built for **educational/demonstration purposes only** and should **not** be used as a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider for medical concerns.

## 🛠️ Tech Stack

- Python
- Streamlit
- scikit-learn
- Pandas
- Joblib

## 📄 License

This project is open source and available for educational use.
