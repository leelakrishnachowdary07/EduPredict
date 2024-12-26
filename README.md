
# Edupredict Project

## Overview
**Edupredict** is a machine learning project aimed at predicting the academic year and placement status of students based on their historical academic performance and other relevant factors. The project consists of two primary tasks:

1. **Year Prediction**: Predicting the academic year a student belongs to.
2. **Placement Status Prediction**: Predicting whether a student will be placed in a company after graduation.

The primary goal of this project is to use machine learning algorithms to help educational institutions make better decisions related to student progress and placements. It also helps students gauge their placement readiness based on their performance.

## Problem Statement
1. **Year Prediction**:
   - Educational institutions often struggle with efficiently determining which academic year a student should be in based on their performance, attendance, and other factors.
   - By predicting a student's year, the system can better identify and assist students who might be lagging in their academic progress.
   
2. **Placement Status Prediction**:
   - Placement outcomes are crucial for students, and various factors impact whether a student will get placed, including academic performance, internships, extracurricular activities, etc.
   - Predicting placement status can provide students with early insights into their employability chances, allowing them to focus on areas for improvement.

## Features and Tasks

### Task 1: Year Prediction
In this task, the goal is to predict the academic year of a student (e.g., first year, second year, third year, etc.) based on features like historical grades, attendance, and performance in previous years.

#### Objective
- To predict the academic year of a student.

#### Features Used
- **Grades**: Performance in various subjects.
- **Attendance**: Number of classes attended.
- **Past performance**: Results from previous academic years.

#### Approach
- **Data Preprocessing**: Clean the data by handling missing values, normalizing numerical features, and encoding categorical variables.
- **Machine Learning Models**: Models such as Decision Trees, Random Forest, and Logistic Regression are used for the prediction task.
- **Evaluation Metrics**: Accuracy, Precision, Recall, and F1-Score are used to evaluate model performance.

#### Outcome
- A classifier that predicts a student's academic year based on the input features.

### Task 2: Placement Status Prediction
In this task, the goal is to predict whether a student will be placed in a company based on various factors like academic performance, extracurricular activities, and internship experience.

#### Objective
- To predict whether a student will get placed or not (binary classification: "Placed" or "Not Placed").

#### Features Used
- **Academic performance**: Marks in relevant subjects.
- **Extracurricular activities**: Participation in clubs, societies, or sports.
- **Internships**: Past internship experience, if any.
- **Previous placement records**: Placement history from earlier batches.

#### Approach
- **Data Preprocessing**: Handle missing data, normalize numerical values, and encode categorical variables like placement status.
- **Machine Learning Models**: Logistic Regression, Support Vector Machines (SVM), and Random Forest are experimented with for prediction.
- **Evaluation Metrics**: Accuracy, Precision, Recall, and F1-Score to evaluate how well the model predicts placement status.

#### Outcome
- A model that classifies a student as "Placed" or "Not Placed" with the given features.

## Technologies Used
- **Python**: Programming language used for implementing the project.
- **Libraries**:
  - **Pandas**: For data manipulation and cleaning.
  - **NumPy**: For numerical operations.
  - **Matplotlib/Seaborn**: For visualizing data.
  - **Scikit-learn**: For machine learning models and evaluation metrics.
  - **Jupyter Notebook**: For an interactive development environment.
  
## Dataset
The dataset used in this project includes various features related to students' academic performance and placement data.

### Dataset Information
The dataset contains the following columns:
- **Student_ID**: Unique identifier for each student.
- **Academic_Performance**: Marks scored in major subjects.
- **Attendance**: Percentage of classes attended by the student.
- **Extracurricular_Activity**: Participation in extracurricular activities (binary: Yes/No).
- **Internship_Experience**: Whether the student has an internship experience (binary: Yes/No).
- **Past_Placements**: Placement history (binary: Yes/No).
- **Year**: Academic year (1st, 2nd, etc.).
- **Placement_Status**: Whether the student was placed (binary: Yes/No).

### Data Preprocessing
1. **Missing Data**: Handle missing values by either filling them with appropriate statistics (mean, median) or by dropping rows with missing values.
2. **Normalization**: Standardize numerical features such as marks and attendance to a common scale.
3. **Encoding**: Convert categorical data like extracurricular activities and placement status into numerical representations using one-hot encoding or label encoding.

## Approach

1. **Data Preprocessing**: Clean the data, handle missing values, normalize numerical features, and encode categorical variables.
2. **Exploratory Data Analysis (EDA)**: 
   - Visualize the relationship between features and target variables.
   - Identify patterns, correlations, and outliers in the data.
3. **Model Selection**:
   - **Year Prediction**: Logistic Regression, Decision Trees, and Random Forest models are used for classification.
   - **Placement Status Prediction**: Logistic Regression, SVM, and Random Forest models are used.
4. **Model Training**: Split the data into training and testing sets, then train the models using cross-validation.
5. **Model Evaluation**: Evaluate the performance of models using classification metrics like Accuracy, Precision, Recall, and F1-Score.
6. **Prediction**: Use the trained models to make predictions on unseen data.

## Installation

### Prerequisites
Make sure you have Python 3.x installed on your machine. You can download it from [Python Official Website](https://www.python.org/downloads/).

### Clone the Repository
To get started, clone the repository to your local machine:
```bash
git clone https://github.com/yourusername/edupredict.git
cd edupredict
```

### Install Dependencies
Create a virtual environment and install the required dependencies:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows, use venv\Scripts\activate
pip install -r requirements.txt
```

### Run the Project
Once all dependencies are installed, you can run the project using Jupyter Notebook:
```bash
jupyter notebook
```

### Running the Model
Run the notebook containing the code for both tasks. You can modify the notebook to suit your needs or experiment with different algorithms.

## Results

### Year Prediction Task
- **Model**: Random Forest
- **Accuracy**: 85%
- **Precision**: 0.84
- **Recall**: 0.86
- **F1-Score**: 0.85

### Placement Status Prediction Task
- **Model**: Logistic Regression
- **Accuracy**: 90%
- **Precision**: 0.89
- **Recall**: 0.91
- **F1-Score**: 0.90

## Future Work
- **Incorporating Additional Features**: Future iterations of the project could incorporate more features such as social media activity, peer reviews, etc., to further improve predictions.
- **Deep Learning Models**: Explore the use of deep learning models, such as neural networks, for more accurate predictions.
- **Real-Time Prediction**: Implement a system that can predict the academic year and placement status for incoming students in real-time.


