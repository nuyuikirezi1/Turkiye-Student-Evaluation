# Student-Evaluation
Intro Big Data Analytics 

|Name                             | ID   |
|---------------------------------|------|
|Nuyu Ikirezi Amathia Florentine  |27571 |

# 🎓 Student Evaluation Analysis – Turkiye Dataset

## 📁 Project Overview
This capstone project was developed for the course **INSY 8413: Introduction to Big Data Analytics** (2024–2025, Sem III) under the guidance of **Lecturer Eric Maniraguha**.

The goal is to use **Big Data Analytics** techniques to analyze student evaluation data, uncover insights, and predict outcomes related to **student satisfaction and course repeat rates** using Python and Power BI.

---

## 📊 Sector
**Education**

---

## 🎯 Problem Statement
> How can we predict course satisfaction and identify patterns related to students repeating courses based on their feedback and demographics?

This project analyzes a dataset from a university in Turkiye. It uses 28 question-based evaluation responses, plus metadata such as attendance, course difficulty, and instructor.

---

## 🧠 Objectives
- Clean and preprocess a structured dataset
- Predict student course repetition using ML models
- Visualize trends in satisfaction and performance
- Enable interactivity with Power BI dashboards
- Add advanced features like DAX, slicers, and AI visuals

---

## 📂 Dataset Details

- **Title**: Turkiye Student Evaluation
- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Turkiye+Student+Evaluation)
- **Rows**: 5820
- **Columns**: 33
- **Format**: CSV
- **Preprocessing**: Yes (normalization, encoding, missing values)

---

## 🔍 Python Analysis (Visual Studio Code)

- ✅ Data cleaning (missing values, encoding)
- ✅ Normalization (Q1–Q28)
- ✅ Target variable created: `Repeat Count → target (0 or 1)`
- ✅ Machine learning models: Logistic Regression, Decision Tree
- ✅ Model evaluation: Accuracy, confusion matrix, classification report

---

## 📈 Power BI Dashboard Highlights

- 🎯 Repeats by Instructor (Bar Chart)
- 📊 Attendance vs Repeat Count (Column Chart)
- 📈 Average Satisfaction by Class (Line Chart)
- 🧠 AI Visual: Key Influencers to explain `Repeat Count`
- 🎛️ Slicers: Instructor, Class, Attendance, Difficulty
- 💬 Tooltips for extra hover information
- 📦 Cards: Total Students, Avg Satisfaction, Total Repeats

---

## ✨ Innovative Features Used
- `AvgSatisfaction` as a calculated DAX measure
- AI Visual: **Key Influencers**
- Custom **Tooltips** to show dynamic info
- Slicers for interactive analysis

---

## 📎 Files in this Repository

| File Name | Description |
|-----------|-------------|
| `exam.ipynb` | Python analysis and modeling |
| `cleaned_student_evaluation.csv`   | Preprocessed dataset |
| `Student_Evaluation.pbix`| Power BI dashboard file |
| `screenshots/`                     | Dashboard image exports |
| `presentation.pptx`                | Final PowerPoint presentation |
| `README.md`                        | Project summary and instructions |

---







