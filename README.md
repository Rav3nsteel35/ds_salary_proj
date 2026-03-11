# ds_salary_proj

📊 Data Science Job Market Analysis & Salary Prediction

This project analyzes the data science job market using real job listing data and applies machine learning techniques to predict salaries based on job characteristics, required skills, and company attributes.

The goal of the project is to explore how factors such as skills, company size, industry, and job seniority influence compensation in data-related roles.

🚀 Project Overview

The project follows a typical end-to-end data science workflow:

Data Cleaning & Feature Engineering

Exploratory Data Analysis (EDA)

Skill Extraction from Job Descriptions

Job Role Categorization

Salary Feature Parsing

Statistical Analysis & Visualization

Preparation for Machine Learning Salary Prediction

The dataset contains 742 job postings with information about:

Job titles

Salary estimates

Job descriptions

Company attributes

Required technical skills

Location and industry information

📂 Dataset

The dataset contains job postings with fields such as:

Job Title

Salary Estimate

Company Name

Location

Industry

Sector

Company Size

Revenue

Rating

Job Description

From this raw information, additional features were engineered such as:

Minimum salary

Maximum salary

Average salary

Company age

Job seniority

Simplified job titles

Skill indicators extracted from job descriptions

Example of extracted features:

Feature	Description
python_yn	Whether Python is mentioned
spark_yn	Spark requirement
aws_yn	AWS/cloud requirement
excel_yn	Excel requirement
job_simp	Simplified job role
seniority	Junior / Senior / NA
🧹 Data Cleaning

The salary data required significant preprocessing:

Salary Parsing

Raw salary strings like:

"$91K-$143K (Glassdoor est.)"

Were converted into structured numerical fields:

min_salary

max_salary

avg_salary

Hourly wages were also normalized into annual equivalents.

⚙️ Feature Engineering

Several useful features were derived from the dataset.

Job Title Simplification

Job titles were grouped into broader categories:

Data Scientist

Data Engineer

Machine Learning Engineer

Analyst

Manager

Director

This helps reduce noise in modeling.

Seniority Detection

Titles were categorized into:

Junior

Senior

Not specified

Based on keywords like:

Senior
Lead
Principal
Junior
Intern
Skill Extraction

Skills were automatically detected from job descriptions using keyword matching.

Skills extracted include:

Python

R / RStudio

Spark

AWS

Excel

Example:

df['python_yn'] = df['Job Description'].apply(lambda x: 1 if 'python' in x.lower() else 0)
📊 Exploratory Data Analysis

EDA was performed to understand trends across the job market.

Key insights include:

Average Salary by Job Role
Role	Avg Salary
Analyst	~$66K
Data Engineer	~$105K
Data Scientist	~$117K
Machine Learning Engineer	~$126K
Director	~$168K
Salary by Seniority
Seniority	Avg Salary
Junior	~$67K
Mid-level	~$93K
Senior	~$121K
Skills vs Salary

Some notable trends:

Python appears in ~53% of job postings

Spark and AWS correlate with higher-paying roles

Excel is common in analyst roles

📈 Visualizations

The project includes several visualizations using:

Matplotlib

Seaborn

Examples include:

Job distribution by location

Industry frequency

Company size distribution

Skill demand analysis

🤖 Machine Learning Preparation

The processed dataset (data_cleaned_2021_final.csv) is structured for training salary prediction models.

Possible models include:

Linear Regression

Random Forest Regressor

Gradient Boosting

XGBoost

Target variable:

avg_salary

Predictor features include:

Skills (Python, Spark, AWS, etc.)

Job role

Seniority

Industry

Company size

Company age

Location

🛠 Tech Stack

Python libraries used:

Pandas – Data manipulation

NumPy – Numerical processing

Matplotlib – Visualization

Seaborn – Statistical plots

Scikit-learn – Machine learning (future modeling)

📁 Project Structure
data-science-salary-analysis/

│
├── data_cleaned_2021.csv
├── data_cleaned_2021_final.csv
│
├── salary_analysis.ipynb
│
├── README.md
🎯 Key Takeaways

Data Science and ML roles command significantly higher salaries than analyst roles.

Seniority strongly impacts salary expectations.

Skills like Python, Spark, and AWS are commonly associated with higher compensation.

The dataset can be used to build predictive models for salary estimation.

🔮 Future Improvements

Possible next steps:

Train multiple regression models

Feature importance analysis

Model evaluation (MAE / RMSE)

Interactive dashboards (Streamlit / Tableau)

Job market trend analysis over time

📌 Motivation

This project was built to practice real-world data science workflows, including:

messy data cleaning

feature engineering

exploratory analysis

preparing data for machine learning models
