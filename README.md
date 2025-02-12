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


## Question 1 - What factors influence an employee's decision to resign

Four different classification techniques were used to determine this
- DecisionTreeClassifier
- KNN
- LogisticRegression
- SVC

Different hyperparameters were tried with each model. Best parameters for each model are as follows:
{'knn__n_neighbors': 7}
{'logisticregression__C': 0.1}
{'svc__C': 0.1, 'svc__kernel': 'linear'}
{'decisiontreeclassifier__criterion': 'entropy', 'decisiontreeclassifier__max_depth': 5, 'decisiontreeclassifier__max_features': 'log2'}

The accompanied jupyter notebook carries details of each model and their feature importance. For decisionTreeClassifier, following are the top factors that influence the resignation variable
Training_Hours    0.240436
Age    0.122104
Monthly_Salary    0.075800
Years_At_Company    0.075114
Performance_Score    0.071691
Overtime_Hours    0.071341


