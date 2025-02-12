# Employee Performance and Retention Analysis  

## Introduction  
As a product manager leading a team of engineers, one of my key challenges is evaluating employee performance in a fair and objective manner. I aim to leverage key metrics to assess performance and eliminate subjective bias from the process. Another significant challenge is identifying employees who may be at risk of leaving the team or company. Being able to predict this risk based on specific metrics would allow me to take proactive measures to improve retention.  

## Objective  
Ensuring my team’s productivity and keeping employees motivated is a crucial responsibility. To support this, I am working on a capstone project using a Kaggle dataset focused on employee productivity and other key data points. My goal is to apply various modeling techniques to answer the following questions:  

### Key Research Questions  
- **Employee Resignation Prediction:** Use classification techniques to identify key factors influencing an employee’s decision to resign.  
- **Performance Evaluation:** Apply classification models to assess employee performance scores.  
- **Salary Prediction:** Determine the ideal monthly salary for an employee based on performance scores and other factors such as job title and years of experience.  

## Expected Outcomes  
Through this project, I hope to gain insights that can be applied in my workplace, using similar modeling techniques to enhance decision-making and achieve my goals as a manager.  

## Jupyter Notebook
The [notebook](employee.ipynb) contains the code and analysis for the [dataset](data/employee.csv)

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


## Goal 1 - What factors influence an employee's decision to resign

Four different classification techniques were used to determine this
- DecisionTreeClassifier
- KNN
- LogisticRegression
- SVC

Different hyperparameters were tried with each model. Best parameters for each model are as follows:
- {'knn__n_neighbors': 7}
- {'logisticregression__C': 0.1}
- {'svc__C': 0.1, 'svc__kernel': 'linear'}
- {'decisiontreeclassifier__criterion': 'entropy', 'decisiontreeclassifier__max_depth': 5, 'decisiontreeclassifier__max_features': 'sqrt'}

The accompanied jupyter notebook carries details of each model and their feature importance. For decisionTreeClassifier, following are the top factors that influence the resignation variable
- Overtime_Hours    0.195492
- Training_Hours    0.153816
- Age    0.124334
- Work_Hours_Per_Week    0.097065
- Sick_Days    0.076262
- Remote_Work_Frequency    0.061340
- Employee_Satisfaction_Score    0.058778

## Goal 2 - What factors influence the perfomance_score of employees

Classification technique was used to determine most important factors that determine employee performance data. Based on decision tree classification, following top factors were computed
- Employee_Satisfaction_Score    0.120872
- Training_Hours    0.118766
- Age    0.099242

Few others that were significant contributors are Projects_Handled and Team_Size. Focusing on these parameters will help managers in improving the performance of their employees


## Goal 3 - Calculate monthly salary for employees
In this exercise, parameters like performance_score and Job_Title were chosen to determine the ideal monthly salary for all employees. This allows a manager to determine employees that are underpaid. Improving monthly salary helps in retention of the employee as seen in result of Goal #1

Regression Models were used for this analysis. Linear regression had a high MSE and resulted in following coefficients

                       **feature        coef**
-              Performance_Score  405.627720
-                      Job_Title  951.119420
-    Performance_Score Job_Title  131.433613
-                    Job_Title^2  -73.737564
-  Performance_Score Job_Title^2  -23.535533
-                    Job_Title^3  -17.539578

## Summary

The Kaggle dataset utilized in this project offers valuable insights into various factors influencing employee productivity and retention likelihood. Furthermore, this data can be leveraged to ensure that employees receive fair compensation based on their performance and job responsibilities.  

The findings from this analysis are applicable across organizations with a substantial workforce, providing a data-driven approach to workforce management. As a manager, these techniques can be adapted to relevant data within my organization, enabling more effective team management and facilitating the achievement of organizational objectives.  

