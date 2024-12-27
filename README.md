Here’s a consolidated explanation of **Task-1** and **Task-2** of the Edupredict project:

---

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

**Objective**  
To develop a predictive model that accurately forecasts student placement outcomes using various factors.  

**Goal**  
- Build a robust, high-accuracy model to predict placement status.  
- Facilitate targeted support and informed decision-making for better educational strategies.  

**Dataset Overview**  
The dataset included:  
- **Demographics**: Name, email ID.  
- **Event Participation**: Ticket type, designation.  
- **Academic Performance**: CGPA.  
- **Skills**: Speaking skills, ML knowledge.  
- **Placement Status**: Historical outcomes.  

**Data Preprocessing**  
- Handled missing values and duplicates.  
- Addressed data inconsistencies.  
- Applied feature engineering.  
- Label-encoded categorical variables to prepare for modeling.  

**Model Selection and Training**  
Multiple classification models were evaluated, achieving the following accuracies:  
- **AdaBoost Classifier**: 74.12% (highest accuracy).  
- **Random Forest Classifier**: 63.07%.  
- **Logistic Regression**: 70% 
- **KNeighborsClassifier**: 67.09%.  
- **SVM**: 70.60%.  
- **Decision Tree Classifier**: 58.04%.  
- **Neural Networks (MLP Classifier)**: 70.85%.  
- **XGBoost Classifier**: 67.59%.  
- **GradientBoostingClassifier**: 69.10%.  
- **BaggingClassifier**: 62.81%.  
- **ExtraTreesClassifier**: 60.55%.  

**Results**  
- **AdaBoost Classifier** emerged as the best model with **74.12% accuracy**, demonstrating superior predictive capabilities.  
- Other models achieved varying accuracies, indicating the need for model-specific optimization.  

**Further Considerations**  
1. **Hyperparameter Tuning**: Fine-tune parameters to enhance model performance.  
2. **Feature Importance Analysis**: Identify the most influential factors affecting placement.  
3. **Model Explainability**: Improve transparency for better stakeholder understanding.  
4. **Error Analysis**: Analyze misclassifications to refine the model further.  

**Conclusion**  
By leveraging the placement prediction model and engagement scoring system, the Edupredict project provides comprehensive insights into student involvement and placement readiness, aiding institutions in fostering academic and career success.
