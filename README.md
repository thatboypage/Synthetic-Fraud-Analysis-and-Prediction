# Synthetic Fraud Analysis and Prediction

This project tackles the problem of **fraud detection** using a synthetic dataset, applying various machine learning techniques to identify fraudulent transactions. The goal is to build a robust model that can differentiate between legitimate and fraudulent activity — a crucial task in the financial and cybersecurity sectors.

---

## 🧠 Project Objectives

- Load and explore a synthetic fraud dataset
- Clean and preprocess the data
- Perform Exploratory Data Analysis (EDA)
- Handle class imbalance with **SMOTE**
- Train a machine learning model for prediction
- Identify key features influencing fraud detection
- Evaluate model performance

---

## 🧾 Workflow Overview

### 📥 1. Data Loading and Understanding
The dataset was loaded into a pandas DataFrame. Key statistics were reviewed to understand the distribution and structure of the data.

### 🧹 2. Data Wrangling
- Unnecessary or redundant columns were dropped.
- Columns were renamed and formatted for easier access.
- All features were converted to lowercase for consistency.
- Time-related features were split into components (e.g., hour, day)
  
### 📊 3. Exploratory Data Analysis (EDA)
Though basic, the EDA explored relationships between key variables like:
- Transaction type against Fraud Label
- Device type against Fraud Label
- Authentication methods
- Location against Fraud Label
- card type against Fraud Label

This step helped uncover patterns that informed feature engineering.

### 🧼 4. Data Preprocessing
- Categorical features were **encoded** using `OneHotEncoder`
- Numerical features were **scaled** using `StandardScaler`

### 🧪 5. Model Building
A **Decision Tree Classifier** was trained to predict fraudulent transactions. The classifier was selected for its interpretability and quick training time.

#### 🔍 Feature Importance
Feature importances were extracted from the decision tree model. It was found that only a few features (such as `failed_transaction_count_7d` and `risk_score`) significantly influenced the model's predictions — suggesting these metrics are critical indicators of fraud.

#### ⚖️ SMOTE (Synthetic Minority Oversampling Technique)
Due to class imbalance (far fewer fraud cases), SMOTE was used to generate synthetic examples of the minority class. This helped the model generalize better during training.

---

## 📈 Model Evaluation

- The model was evaluated using metrics such as:
  - Accuracy
  - Recall
  - F1 Score
  - ROC AUC Score
- Visualization of feature importances and tree structure provided insights into the model's decision-making process.

---

## 💡 Insights

- **Risk-based features** (like `risk_score` and `failed_transaction_count_7d`) were most predictive of fraud.
- **SMOTE** significantly improved recall, ensuring more fraud cases were correctly identified.
- Simpler models like Decision Trees can be highly effective with the right preprocessing and feature selection.

---

## 🧰 Tools & Libraries
- Python
- Pandas & NumPy
- Scikit-learn
- Matplotlib & Seaborn
- Imbalanced-learn (for SMOTE)

---

## 📁 Project Structure
- `synthetic_fraud_analysis.ipynb`: Jupyter notebook containing all code, plots, and results
- `README.md`: Project summary and documentation

---

## 🚀 How to Run
1. Clone the repository
2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn
