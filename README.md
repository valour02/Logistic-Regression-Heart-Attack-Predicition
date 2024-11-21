# **Code Documentation for Heart Disease Prediction - EDA and Logistic Regression**

This Python script performs **Exploratory Data Analysis (EDA)** and builds a **Logistic Regression Model** to predict the likelihood of heart disease based on a dataset containing health metrics. Below is an explanation of the code's functionality, organized by sections:

---

### **1. Importing Libraries**
The script imports essential libraries:
- `pandas` and `numpy`: For data manipulation and numerical operations.
- `seaborn` and `matplotlib.pyplot`: For visualizations.
- `pandas_profiling`: For automated data profiling.
- `sklearn`: For machine learning operations.

---

### **2. Data Loading and Initial Exploration**
- **Load Dataset**: Reads the CSV file containing heart disease data into a pandas DataFrame.
- **View Data**: Displays the first (`head`) and last (`tail`) 5 rows to understand the dataset structure.
- **Dataset Info**:
  - `info()`: Provides details like column names, data types, and missing values.
  - `describe()`: Summarizes numerical columns with statistics (mean, median, min, max, etc.).
  - `isnull().sum()`: Counts missing values in each column.
  
---

### **3. Visualization of Missing Values**
- **Heatmap**: Uses `seaborn.heatmap` to visualize the presence of missing values, confirming no missing data.

---

### **4. Automated Profiling**
- **`pandas_profiling`**: Generates a detailed HTML report summarizing data distributions, correlations, and potential data issues.

---

### **5. Feature Selection**
- **Chi-Squared Test**:
  - Uses `SelectKBest` to identify the 10 most important features.
  - Visualizes feature scores.
- **Tree-based Feature Importance**:
  - Utilizes `ExtraTreesClassifier` to calculate and visualize feature importance using a bar chart.

---

### **6. Data Visualizations**
- **Correlation Heatmap**:
  - Displays relationships between numerical features using a `seaborn.heatmap`.
- **Unique Values**:
  - Prints the count of unique values in each column to identify categorical data.
- **Count Plots**:
  - Visualizes distributions of `sex`, `chest_pain_type`, and `st_slope` against `target` using `sns.countplot`.
- **Histograms**:
  - Depicts distributions of `age` and `cholesterol` for patients with heart disease.
- **Joint Plots**:
  - Explores relationships between pairs of features like `age` vs. `resting_bp_s`.
- **Box Plots and Violin Plots**:
  - Compare feature distributions such as `age` or `oldpeak` for different `target` values.

---

### **7. Data Transformation**
- **Target Variable Mapping**:
  - Converts `sex` and `target` columns into readable labels (`male/female` and `Heart Disease/No Heart Disease`) for better visualization.

---

### **8. Logistic Regression Model**
- **Data Preparation**:
  - Splits data into features (`X`) and target (`y`), then performs an 80-20 train-test split.
- **Model Training**:
  - Fits a logistic regression model using the training data.
- **Model Evaluation**:
  - Predicts target values for the test set.
  - Calculates and prints:
    - **Accuracy**: Proportion of correctly predicted outcomes.
    - **Confusion Matrix**: Displays true positives, true negatives, false positives, and false negatives.
    - **Classification Report**: Details precision, recall, and F1-score for each class.

---

### **9. Key Results**
- The Logistic Regression model achieves an **accuracy of 84.45%**.
- The confusion matrix indicates balanced performance across classes.
- The classification report highlights the model's reliability in identifying both heart disease presence and absence.

---

### **10. Notes and Warnings**
- **Deprecated Functions**:
  - The script uses `sns.distplot`, which is deprecated in `seaborn`. It recommends switching to `sns.displot` or `sns.histplot` for future compatibility.
- **Data Cleaning**:
  - The `X.abs()` operation is used to ensure non-negative values for the chi-squared test.

---

This script demonstrates a comprehensive approach to analyzing and predicting heart disease, integrating robust EDA, feature selection, and machine learning practices.
