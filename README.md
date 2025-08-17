# 🏦 Loan Prediction Project  

This project aims to **predict loan approval status** using different machine learning models.  
It involves **EDA (Exploratory Data Analysis)**, **data preprocessing**, **feature engineering**, and **model evaluation** on a real-world style dataset.  

---

## 📂 Project Structure
- `loan_pj.ipynb` → Main notebook with data analysis, preprocessing, modeling & evaluation  
- `README.md` → Project documentation  
- `requirements.txt` → Python dependencies  

---

## 📊 Dataset
The dataset contains information such as:
- Applicant Income  
- Coapplicant Income  
- Loan Amount & Loan Term  
- Credit History  
- Gender, Education, Marital Status, Employment  

**Target Variable:** `Loan_Status` (Approved = 1, Unapproved = 0)

---

## 🔎 Exploratory Data Analysis (EDA)
Before training models, a complete **EDA** was performed to understand the dataset:  

1. **Missing Values Analysis**
   - Found missing values in `LoanAmount`, `Loan_Amount_Term`, and `Credit_History`  
   - Used **KNNImputer** and **SimpleImputer** for handling missing data  

2. **Categorical Features**
   - Distribution of `Gender`, `Education`, `Self_Employed`, `Property_Area`  
   - Loan approval rates compared across categories (e.g., **Males had slightly higher approval rates**)  

3. **Numerical Features**
   - Histograms & KDE plots for `ApplicantIncome`, `CoapplicantIncome`, `LoanAmount`  
   - Boxplots showed skewness in `ApplicantIncome` and outliers in `LoanAmount`  

4. **Bivariate Analysis**
   - Loan approval vs. `Credit_History`: **Applicants with Credit_History=1 were much more likely to get approved**  
   - Loan approval vs. `Loan_Amount_Term` across genders  
   - Correlation heatmap of numerical variables  

5. **Key Insights**
   - `Credit_History` is the most important predictor  
   - High applicant income does not guarantee loan approval  
   - Certain property areas showed higher approval ratios  

---

## 🔧 Methodology
1. **Data Preprocessing**
   - Handling missing values (SimpleImputer, KNNImputer)  
   - Encoding categorical variables (OneHotEncoder)  
   - Scaling numerical features (StandardScaler)  

2. **Data Splitting**
   - Train (65%)  
   - Validation (15%)  
   - Test (20%)  

3. **Modeling**
   - Logistic Regression  
   - Random Forest  
   - XGBoost  
   - KNN  
   - Artificial Neural Network (ANN)  

4. **Hyperparameter Tuning**
   - Used **GridSearchCV** for Logistic Regression, Random Forest, XGBoost, and ANN.  

---

## 📈 Results Summary

| Model                  | Validation AUC | Test AUC | Accuracy | Key Insight |
|-------------------------|----------------|----------|----------|-------------|
| Logistic Regression     | 0.74           | 0.729    | 78%      | Strong baseline, interpretable |
| XGBoost                 | 0.74           | 0.710    | 71%      | Slightly weaker than LR/KNN |
| Random Forest           | 0.73           | 0.700    | 75%      | Balanced, moderate |
| KNN                     | 0.75           | 0.718    | **78%**  | Best accuracy, low false positives |
| ANN                     | 0.68           | 0.625    | 74%      | Weakest, possible overfitting |

---

## 📝 Overall Conclusion
- **KNN (Normalized)** achieved the best overall performance in terms of accuracy and reducing false positives.  
- **Logistic Regression** remained a strong baseline model with good interpretability.  
- **Tree-based models (RF, XGBoost)** performed moderately but were not superior.  
- **ANN** underperformed, likely due to dataset size and sensitivity to hyperparameters.  

---

## 🚀 How to Run
```bash
# Clone the repository
git clone https://github.com/your-username/loan-prediction.git
cd loan-prediction

# Install dependencies
pip install -r requirements.txt

# Run Jupyter Notebook
jupyter notebook loan_pj.ipynb
```
## Author

Name : [Alirezasmoradi](https://github.com/Alirezasmoradi)

LinkedIn : [Alireza Soltan Moradi](www.linkedin.com/in/alirezasoltanmoradi) 
