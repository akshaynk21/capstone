# Employee Performance and Retention Analysis  

## Introduction  
As a product manager leading a team of engineers, one of my key challenges is evaluating employee performance in a fair and objective manner. I aim to leverage key metrics to assess performance and eliminate subjective bias from the process. Another significant challenge is identifying employees who may be at risk of leaving the team or company. Being able to predict this risk based on specific metrics would allow me to take proactive measures to improve retention.  

## Objective  
Ensuring my team’s productivity and keeping employees motivated is a crucial responsibility. To support this, I am working on a capstone project using a Kaggle dataset focused on employee productivity and other key data points. My goal is to apply various modeling techniques to answer the following questions:  

### Key Research Questions  
- **Employee Resignation Prediction:** Use classification techniques to identify key factors influencing an employee’s decision to resign.  
- **Salary Prediction:** Determine the ideal monthly salary for an employee based on performance scores and other factors such as job title and years of experience.  

## Expected Outcomes  
Through this project, I hope to gain insights that can be applied in my workplace, using similar modeling techniques to enhance decision-making and achieve my goals as a manager.  


## Data Source
https://www.kaggle.com/datasets/mexwell/employee-performance-and-productivity-data?resource=download

The dataset provides data on employee demographics and performance. The key columns in this dataset are
- Years_At_Company: The number of years the employee has been working for the company.
- Job_Title: The role held by the employee (e.g., Manager, Analyst, Developer).
- Gender: Gender of the employee (Male, Female, Other).
- Department: The department in which the employee works (e.g., Sales, HR, IT).
- Performance_Score: Employee's performance rating (1 to 5 scale).
- Monthly_Salary: The employee's monthly salary in USD, correlated with job title and performance score.
- Work_Hours_Per_Week: Number of hours worked per week.
- Overtime_Hours: Total overtime hours worked in the last year.
- Remote_Work_Frequency - Percentage of time worked remotely (0%, 25%, 50%, 75%, 100%)
- Team_Size: Number of people in the employee's team.
- Training_Hours - Number of hours of training for the employee
- Promotions: Number of promotions received during their tenure.
- Employee_Satisfaction_Score: Employee satisfaction rating (1.0 to 5.0 scale).
- Resigned: Boolean value indicating if the employee has resigned.
<br/>
<br/>


## Techniques Used
- First the dataset was sanitized. Outliers were removed.
- Some basic plotting was done to determine the correlation of various columns. This helped gained some insights into the dataset

- To determine the resignation outcome, a few classification models are used like LogisticRegression, DecisionTree, KNN and RandomForest
- Accuracy score for each model and its training time is extracted. GridSearchCV is used to determine the best hyper-parameters for each model. 
- RandomForest had the highest score and was used for further analysis. Accuracy score is 0.9
- Factors that affect the classification the most are determined using Feature Importances. These are summarized in a report at the end of the notebook.

- To make the salary prediction, a few regression models are used like LinearRegression, DecisionTree, KNN and Ridge.
- GridSearchCV is used to determine the best hyper-parameters for each model.
- VotingRegressor is used at the end to combine the best of all models
- Root Mean Square error is calculated and a plot of predicted vs actual values for salary is plotted. RMSE is 124
- Factors affecting salary the most are derived from the votingRegressor model. These factors are summarized in a report at the end of the notebook

## Summary - Business report
# Summary Report: Employee Attrition and Salary Determination Analysis  

## Overview  
In this exercise, we had 2 goals:
- Determine factors affecting employees decision to resign
- Determine ideal salary for all employees
This report presents key findings from data analysis on employee attrition factors and salary determination. By leveraging predictive modeling, organizations can enhance employee retention, ensure fair compensation, and improve overall workforce productivity.  

## Key Findings
A curated dataset was used to model various machine learning techniques. The dataset was cleaned, refined and then analyzed to determine the most important factors in employee attrition and salary determination analysis.

### Employee Attrition Factors  
Analysis using a random forest classification model identified the following critical factors influencing employee resignation:  

- **Employee Satisfaction Score**  
- **Overtime Hours**  
- **Team Size**  
- **Education Level**  
- **Remote Work Frequency**  

### Salary Determination Factors  
A linear regression model was applied to analyze salary determinants, identifying:  

- **Performance Score**  
- **Job Title**  

The model predicted salary with a root mean squared error (RMSE) of **124**, ensuring a data-driven approach to fair compensation.  

## Recommendations  

### Reducing Employee Attrition  
To enhance employee retention, management should:  

1. **Monitor Employee Satisfaction Scores** – Conduct regular surveys and implement targeted retention strategies.  
2. **Manage Overtime Hours** – Distribute workloads effectively to prevent burnout.  
3. **Optimize Team Sizes** – Ensure team structures support productivity and employee well-being.  
4. **Evaluate Remote Work Policies** – Implement flexible work arrangements based on employee needs.  
5. **Use Predictive Modeling** – Identify at-risk employees and proactively address retention issues.  

### Ensuring Fair Compensation  
To maintain a competitive and equitable salary structure, HR should:  

1. **Use Data-Driven Salary Benchmarking** – Identify employees earning below the predicted range.  
2. **Adjust Compensation Accordingly** – Ensure fair and just rewards for all employees.  
3. **Enhance Employee Motivation** – Fair salaries improve morale, retention, and productivity.  
4. **Regularly Review Salary Structures** – Align compensation with market trends and performance metrics.  

## Conclusion  
By leveraging data-driven insights, organizations can reduce employee attrition, ensure fair compensation, and foster a motivated, productive workforce. Implementing these strategies will lead to long-term business success and employee satisfaction.  


