# 🚢 Titanic Survival Classification

## 📌 Project Objective
The goal of this project is to predict whether a passenger survived the Titanic disaster based on features like **Pclass, Sex, Age, SibSp, Parch, Fare, and Embarked**.  
This is a **binary classification** problem, where the target variable `Survived` takes values 0 (did not survive) or 1 (survived).

---

## Approach

1. **Data Loading & Exploration**
   - Loaded `train.csv` and `test.csv` datasets.
   - Checked dataset shape, columns, data types, missing values, and target distribution.
   - Observed slight class imbalance (62% did not survive, 38% survived) and missing values in `Age`, `Cabin`, and `Embarked`.

2. **Data Cleaning**
   - Filled missing `Age` values with median and `Embarked` with mode.
   - Dropped `Cabin` due to excessive missing values (~77% missing).
   - Removed irrelevant columns: `Name` and `Ticket`.
   - Resulting dataset had no missing values.

3. **Feature Engineering**
   - Created new features to capture hidden patterns:
     - `FamilySize` = `SibSp + Parch + 1`
     - `IsAlone` → 1 if traveling alone, 0 otherwise
     - `AgeGroup` → categorical bins (Child, Teen, YoungAdult, Adult, Senior)
     - `FareBand` → quartile-based fare categories
   - These features reflect family presence, social status, and economic factors influencing survival.

4. **Encoding & Scaling**
   - Converted categorical variables (`Sex`, `Embarked`, `AgeGroup`, `FareBand`) to numeric format.
   - Scaled numeric features (`Age`, `Fare`) using StandardScaler for model compatibility.

5. **Model Training & Evaluation**
   - Split data into training and validation sets.
   - Trained multiple models:
     - Logistic Regression
     - Decision Tree
     - Random Forest
   - Evaluated models using **accuracy, precision, recall, and F1-score**.

---

## 📊 Key Insights

- **Data Insights**
  - Average passenger age: ~30 years; skewed Fare distribution.
  - Family size affects survival probability; passengers alone had slightly lower survival chances.
  
- **Model Insights**
  - Logistic Regression Accuracy: ~80%
  - Decision Tree Accuracy: ~78%
  - Random Forest Accuracy: ~81% (best performance)
  - Random Forest balanced performance across both survived and non-survived classes.

- **Conclusions**
  - Gender, age, passenger class, family size, and fare are significant predictors of survival.
  - Feature engineering improved model understanding and performance.
  - Random Forest is the recommended model for final predictions.
  - The project demonstrates a complete ML workflow: data exploration → cleaning → feature engineering → encoding → modeling → evaluation.

---

## Author
- Rimsha Iram
- [Check Portfolio](https://www.datascienceportfol.io/rimshairamanalytics)
- Let’s connect on [LinkedIn](https://www.linkedin.com/in/rimsha-iram-analytics)
