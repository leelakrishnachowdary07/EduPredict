# *Reference*
Task-1: https://colab.research.google.com/drive/1_DGnIYnGUIZ1cq2JlOcv0DJrXTwwoQKo?usp=sharing

Task-2: https://colab.research.google.com/drive/1lr4jDFC9gngFhz55LOoVd3bSYyu9RKiL?usp=sharing
### **Edupredict Project**

---

### **Task 1: Predicting Year of Graduation**
**Objective**:  
The goal of this task was to predict the graduation year of students using data parameters like academic year, creation date, and other relevant factors. 

---

### **Overview of Dataset**:  
- **Total Rows**: 2808 unique entries after removing duplicates.  
- **Key Features**:  
  - **Email**: Identifier for deduplication.  
  - **Colleges & New College Name**: Merged to create a consolidated "College" field.  
  - **Branch/ Specialization & Other Branch**: Combined into a single "Branch" column.  
  - **Gender, City**: Used for demographic analysis.  
  - **Academic Year** and **What is your current academic year?**: Used to derive the year of graduation.  
  - **Created**: Timestamp of data entry, used for extracting the year and month of creation.  

---

### **Data Preprocessing**:
1. Removed duplicates using the `Email` field.  
2. Merged related columns (`Branch`, `College`).  
3. Replaced missing values with 0 or blanks where necessary.  
4. Extracted useful time-based features (Month, Year) from the `Created` column.  
5. Harmonized data types and values in the `Academic Year` column to ensure uniformity.

---

### **Approach**:  
The task utilized logic-based transformations to predict the year of graduation:
1. Mapped academic years (1st to 4th year) to calculate the number of years left to graduation.  
2. Added these to the creation year (`Created.Year`) to derive the final graduation year.  
3. For entries missing academic year data, placeholders (0 or blank) were used.

---

### **Data Analysis & Visualization**:  
- **Gender Distribution**: Analyzed the attendee gender demographics.  
- **City Representation**: Evaluated attendance based on city.  
- **Branch Analysis**: Visualized participation based on engineering branches.  
- **Interest in Programs and Events**: Gauged interest in Cloud Counselage programs and events.  
- **Recommendation Trends**: Assessed whether participants recommended Cloud Counselage to others.  
- **Event Awareness Platforms**: Investigated how participants learned about the event.

These analyses were performed using libraries like **Plotly**, **Seaborn**, and **Matplotlib**.

---

### **Results**:  
- A new column, **Year of Graduation**, was added to the dataset.  
- The data was exported to Excel (`Predicted Year of Graduation.xlsx`) and CSV formats for further use.  
- **No machine learning models were used** in this task as it was rule-based and heavily dependent on logic derived from the data.

---

#### **Task-2: Placement Prediction Model**


#### **Steps Involved in the Code**
1. **Data Preprocessing**:
   - Loaded the dataset and inspected it for missing values, outliers, and inconsistencies.
   - Categorical variables were encoded using techniques like one-hot encoding or label encoding.
   - The dataset was split into training and validation sets (e.g., 80-20 split).
   - Applied feature scaling (standardization or normalization) for models sensitive to scaling (e.g., Logistic Regression, SVM, MLP).

2. **Model Selection**:
   - Implemented various classification and regression models using popular libraries like `scikit-learn` and `xgboost`.
   - For classification, the target variable was treated as categorical, while for regression, it was treated as continuous.

3. **Training the Models**:
   - Each model was trained using the training dataset.
   - Default hyperparameters were used initially to evaluate baseline performance.

4. **Evaluation**:
   - For classification, used metrics like **accuracy**, **precision**, **recall**, and **F1-score** for performance evaluation.
   - For regression, used **Mean Squared Error (MSE)** and **R² Score**.

5. **Performance Comparison**:
   - Consolidated results of all models to identify the best-performing ones for both classification and regression tasks.

6. **Hyperparameter Tuning**:
   - Identified key hyperparameters for top-performing models and performed tuning using **GridSearchCV** or **RandomizedSearchCV**.

---

### **Classification Models Performance**
| **Model**                 | **Validation Accuracy (%)** | **Performance Summary**                                                                                   |
|---------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------|
| **RandomForestClassifier** | 63.07                      | Moderate performance with balanced precision and recall (~60%).                                           |
| **LogisticRegression**     | 69.85                      | High recall for class 2 but struggles with class 1. Convergence warnings observed.                        |
| **KNeighborsClassifier**   | 67.08                      | Performs well on class 2 but poor for class 1. Performance depends on `n_neighbors`.                      |
| **SVC (SVM)**              | 70.60                      | Good overall performance, especially for class 2. Requires scaled features for better results.            |
| **DecisionTreeClassifier** | 58.04                      | Poor performance, likely due to overfitting.                                                             |
| **MLPClassifier**          | 70.85                      | Performs well overall but struggles with class 1 predictions. Scaling and tuning may improve results.     |
| **XGBoostClassifier**      | 67.59                      | Shows potential, but struggles with class 1. Hyperparameter tuning required.                              |
| **GradientBoostingClassifier** | 69.10                  | Balanced accuracy but struggles with class 1. Needs fine-tuning for better performance.                   |
| **AdaBoostClassifier**     | 74.12                      | **Best-performing model**; good accuracy for classes 0 and 2, but recall for class 1 remains an issue.     |
| **BaggingClassifier**      | 62.81                      | Comparable to RandomForest but with slightly lower performance.                                           |
| **ExtraTreesClassifier**   | 60.55                      | Underperformed compared to RandomForest.                                                                 |

---

### **Regression Models Performance**
| **Model**                 | **MSE** | **R² Score** | **Performance Summary**                                                                                    |
|---------------------------|---------|--------------|------------------------------------------------------------------------------------------------------------|
| **LinearRegression**      | 0.585   | 0.185        | Poor performance; linear assumptions do not hold well for the dataset.                                     |
| **Ridge Regression**       | 0.585   | 0.185        | Similar to LinearRegression; slightly better handling of multicollinearity.                                |
| **Lasso Regression**       | 0.596   | 0.170        | Slightly worse than Ridge due to higher regularization, reducing model complexity too aggressively.         |
| **DecisionTreeRegressor**  | 1.136   | -0.582       | Overfits the data, resulting in poor generalization to the validation set.                                 |

---

### **Key Observations**
1. **Best Classification Model**:
   - **AdaBoostClassifier** with a validation accuracy of 74.12%.  
   - Struggles with recall for class 1, indicating room for improvement via class balancing or further tuning.  

2. **Regression Models**:
   - None of the regression models performed satisfactorily, with the highest R² score being 0.185 (Linear/Ridge Regression).  
   - The DecisionTreeRegressor performed the worst, likely due to overfitting.

---
