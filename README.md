# Student-Evaluation
Intro Big Data Analytics 

|Name                             | ID   |
|---------------------------------|------|
|Nuyu Ikirezi Amathia Florentine  |27571 |

# Student Evaluation Analysis – Turkiye Dataset

##  Sector
**Education**

---
## Problem Title:
Turkiye Student Performance Prediction Based on Course Evaluation Data

---
##  Problem Statement
> How can we predict course satisfaction and identify patterns related to students repeating courses based on their feedback and demographics?

This project analyzes a dataset from a university in Turkiye. It uses 28 question-based evaluation responses, plus metadata such as attendance, course difficulty, and instructor.


Understanding the factors that influence student academic success is crucial for improving learning outcomes. In this project, we analyze a dataset of student evaluations from a university in Turkey. The dataset includes attributes such as attendance, difficulty level, number of classes, and various course-related ratings. The goal is to predict the success or failure of a student in a course and identify the most significant factors affecting their performance.


---



##  Objectives
- Clean and preprocess a structured dataset
- Predict student course repetition using ML models
- Visualize trends in satisfaction and performance
- Enable interactivity with Power BI dashboards

---

##  Dataset Details

- **Title**: Turkiye Student Evaluation
- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Turkiye+Student+Evaluation)
- **Rows**: 5820
- **Columns**: 33
- **Format**: CSV
- **Preprocessing**: Yes (normalization, encoding, missing values)

---

##  Python Analysis (Visual Studio Code)

 # Data cleaning (missing values, encoding)

  - Setup and Load Dataset
   ```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv('Turkiye_Student_Evaluation.csv')  # or .xlsx if it's an Excel file

# Check the first few rows
df.head()
```
  - Basic Inspection
  ```

df.info()
df.describe()
df.isnull().sum()
```
  # Data Cleaning
  - Handle Missing Values
  ```
df = df.dropna()  # or use df.fillna(method='ffill') if necessary
```
 -  Encode Categorical Variables
  ```
df['instructor_encoded'] = df['instructor'].astype('category').cat.codes
df['class_encoded'] = df['class'].astype('category').cat.codes
```
 



  # Normalization (Q1–Q28)
  ```
from sklearn.preprocessing import StandardScaler

numerical_cols = df.select_dtypes(include=['int64', 'float64']).columns
scaler = StandardScaler()
df[numerical_cols] = scaler.fit_transform(df[numerical_cols])
```
  # Exploratory Data Analysis (EDA)
 -  Correlation Matrix
```
  plt.figure(figsize=(12, 8))
sns.heatmap(df.corr(), annot=False, cmap='coolwarm')
plt.title("Correlation Matrix")
plt.show()
```
![4a](https://github.com/user-attachments/assets/3348cfd9-59da-4003-b930-c9c7e357ec29)
  - Distribution of Performance
  ```
sns.histplot(df['nb.repeat'], kde=False, bins=5)
plt.title("Number of Times Students Repeated Course")
plt.show()
```
![4b](https://github.com/user-attachments/assets/c748eee2-3972-425f-8e1c-95660f78cfc3)
  - Boxplot
  ```
sns.boxplot(x='attendance', y='nb.repeat', data=df)
plt.title("Attendance vs Repeats")
plt.show()
```
![4c](https://github.com/user-attachments/assets/3c463141-8f8e-4c4a-aa35-a1ee4ab3064c)
- Define Target and Features
 ```
df['target'] = df['nb.repeat'].apply(lambda x: 1 if x > 0 else 0)

X = df.drop(['nb.repeat', 'target'], axis=1)
y = df['target']
```
-  Train/Test Split
```
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
-  Train Model (Logistic Regression or Decision Tree)
```
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier

lr = LogisticRegression()
lr.fit(X_train, y_train)

dt = DecisionTreeClassifier()
dt.fit(X_train, y_train)

```
-  Evaluate the Model
```
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Predict
y_pred = lr.predict(X_test)

# Accuracy and Report
print("Accuracy:", accuracy_score(y_test, y_pred))
print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))
```
  # Save Cleaned Dataset
  ```
df.to_csv('cleaned_student_evaluation.csv', index=False)

```

---

##  Power BI Dashboard Highlights
 - Rename only the ones used in visuals


instr_encoded → Instructor

class_encoded → Class

difficulty_encoded → Difficulty

nb.repeat → Repeat Count

-  Repeats by Instructor	Bar Chart
![p1](https://github.com/user-attachments/assets/258c945a-9252-4bfa-8841-79536f2641f0)

-  Attendance vs Repeats	Column Chart
  ![p2](https://github.com/user-attachments/assets/97e9e7ca-4d85-45f0-9446-40d8fc69fa2b)

-  Average Satisfaction per Class	Line Chart
  ![p3](https://github.com/user-attachments/assets/c9d905a6-2f98-433c-8b38-e08eaec56404)

  
-  Class Distribution	Pie Chart
  ![p4](https://github.com/user-attachments/assets/a55e7d61-9237-4e85-9d76-e2e5291d6cf7)

-  Slicers: Instructor, Class, Attendance
  ![p6](https://github.com/user-attachments/assets/b29f7a12-b05d-47e0-8213-6e42854853c9)

-  Question-wise Rating (Q1–Q5)	Stacked Bar
  ![p5](https://github.com/user-attachments/assets/5eed6291-46f5-4f22-afb7-5c09791b5759)

-  Tooltips for zoom slider
  ![too](https://github.com/user-attachments/assets/b8903667-4fe6-4efb-ae1d-283a350420e3)

-  Cards: Class,Attendence, Instructor, Difficulty_encoded
  ![car](https://github.com/user-attachments/assets/deaf1cc0-baf4-4752-8ea9-3a613ae89571)
-  Key influencers
  ![p7](https://github.com/user-attachments/assets/e680f642-5f99-45ce-9ff5-5f98ba68402a)


---

##  Innovative Features Used

- `AvgSatisfaction` as a calculated DAX measure
```
AvgSatisfaction = 
(
    [Q1] + [Q2] + [Q3] + [Q4] + [Q5] + [Q6] + [Q7] + [Q8] + [Q9] + [Q10] +
    [Q11] + [Q12] + [Q13] + [Q14] + [Q15] + [Q16] + [Q17] + [Q18] + [Q19] + [Q20] +
    [Q21] + [Q22] + [Q23] + [Q24] + [Q25] + [Q26] + [Q27] + [Q28]
) / 28

```
and (Modeling → New Measure)
```
TotalStudents = COUNTROWS(cleaned_student_evaluation)

```
- 
- Custom **Tooltips** to show zoom slider
- Slicers for interactive analysis

---

##  Files in this Repository

| File Name | Description |
|-----------|-------------|
| `exam.ipynb` | Python analysis and modeling |
| `cleaned_student_evaluation.csv`   | Preprocessed dataset |
| `Student_Evaluation.pbix`| Power BI dashboard file |
| `screenshots/`                     | Dashboard image exports |
| `presentation.pptx`                | Final PowerPoint presentation |
| `README.md`                        | Project summary and instructions |

---







