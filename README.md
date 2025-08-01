# Student-Evaluation
Intro Big Data Analytics 

|Name                             | ID   |
|---------------------------------|------|
|Nuyu Ikirezi Amathia Florentine  |27571 |

# 🎓 Student Evaluation Analysis – Turkiye Dataset

##  Sector
**Education**

---
## Problem Title:
Turkiye Student Performance Prediction Based on Course Evaluation Data

```
```
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
- Add advanced features like DAX, slicers, and AI visuals

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

-  Data cleaning (missing values, encoding)
-  Normalization (Q1–Q28)
-  Target variable created: `Repeat Count → target (0 or 1)`
-  Machine learning models: Logistic Regression, Decision Tree
-  Model evaluation: Accuracy, confusion matrix, classification report

---

##  Power BI Dashboard Highlights

-  Repeats by Instructor (Bar Chart)
-  Attendance vs Repeat Count (Column Chart)
-  Average Satisfaction by Class (Line Chart)
-  AI Visual: Key Influencers to explain `Repeat Count`
-  Slicers: Instructor, Class, Attendance
-  Tooltips for extra hover information
-  Cards: Class,Attendence, Instructor, Difficulty_encoded

---

##  Innovative Features Used
- `AvgSatisfaction` as a calculated DAX measure
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







