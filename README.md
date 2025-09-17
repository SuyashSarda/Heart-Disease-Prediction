# ❤️ Heart Disease Prediction

This project predicts the likelihood of **heart disease** based on patient health parameters. It includes **EDA, preprocessing, model building, and a Streamlit web app** for real-time predictions.

---

---

## 📊 Dataset

- **Source**: Kaggle Heart Disease Dataset  
- **Rows**: 918  
- **Columns**: 12  
- **Target Variable**: `HeartDisease` (0 = No, 1 = Yes)  

### Features:
`Age, Sex, ChestPainType, RestingBP, Cholesterol, FastingBS, RestingECG, MaxHR, ExerciseAngina, Oldpeak, ST_Slope`

---

## 🔍 Exploratory Data Analysis (EDA)

1. Checked for **missing values** → none found.  
2. Replaced **0 values** in `Cholesterol` & `RestingBP` with **mean values**.  
3. Visualized relationships using **Seaborn plots** (countplot, boxplot, violinplot, heatmap).  
4. Converted categorical variables into numerical using **One-Hot Encoding**.

---

## ⚙️ Data Preprocessing

- Handled outliers (0 values in health metrics).  
- One-hot encoded categorical columns.  
- Converted all values to integers.  
- Standardized features using **StandardScaler**.

---

## 🤖 Models Used

| Model                  | Accuracy | F1 Score |
|-------------------------|----------|----------|
| Logistic Regression     | 0.875    | 0.8878   |
| KNN                     | 0.8859   | 0.8986   |
| Naive Bayes             | 0.8696   | 0.8788   |
| Decision Tree           | 0.75   | 0.7653   |
| SVM (RBF Kernel)        | 0.8641   | 0.8804   |

✅ **Best Model: KNN** (Accuracy = 88.6%, F1 Score = 89.9%)

---

## 💾 Model Saving

```python
import joblib

# Save model, scaler, and columns
joblib.dump(models['KNN'], 'KNN_heart.pkl')
joblib.dump(scaler, 'scaler.pkl')
joblib.dump(X.columns.tolist(), 'columns.pkl')


