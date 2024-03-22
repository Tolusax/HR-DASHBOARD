# HR-DASHBOARD ANALYSIS

### Project Overview

This data analysis project is equipped with the task of recruiting, employing, compensating employees, developing policies, strategic planning and advice to the organization profit. HR make sure that there is a futuristic approach to every threat / failure that the organization would face. HR is the face of any organization, involved in the day to day running of the activities and ensuring that there’s a smooth running of activities with the thought of covering the loopholes to be faced. 
There are a lot of activities to be put into place but how can HR explain their multi-tasking approach in a simple form to the organization? This involves reasoning and careful deliberate actions presented in   simple form with the help of Power Bi.

### Data Source

The Dataset for this project was gotten from Kaggle.  The dataset consisted of two (2) CSV files containing information provided by the organization namely: HR data which contain all details of employees including employee’s number, age, education, job role and level etc., and a separate file which contain employee names.

### Tools

- Excel - Data Cleaning
- Power Bi - Creating Reports

### Data Cleaning

The first of the dataset is in CSV file in excel which was clustered up in one column
The file was loaded/imported as Text/CSV to Power BI and then Transform Data to load into power query for cleaning.
then Transform Data to load into power query for cleaning
the clustered column was split in power query by clicking split column by delimiter and specifying the delimiter that will be use to split the text column which is: “split at each occurrence of the delimiter” and clicking on the advance options and select columns.

### Analysis for Visualization

During the course of analysis and visualization, some columns were added based on the insights we wanted to get from the data such as: Employees due for promotion, employee due retirement/retrenchment, employee contract type. 
For employee that has not been promoted in the last 7 to 15 years are due for promotion. The existing “YearSinceLastPromotion” column was use to get the new column “Promotion”. This was achieved by selecting “YearSinceLastPromotion” column and then using the “Conditional Column” under the “Add Column” menu

### Data Analysis

Dax Measures 
In order to analysis the data and achieve the desired outcome, a number of Dax measures were created:
1.	Total Employee = DISTINCTCOUNT('HR Analytics Data'[EmployeeNumber]): use to count  the total   number of employee
2.	Male = CALCULATE([Total Employee],'HR Analytics Data'[Gender]= "male") : use to capture the number of male employees
3.	Female = CALCULATE([Total Employee],'HR Analytics Data'[Gender]= "female") : use to capture the number of female employees
4.	%Male = DIVIDE([Male],[Total Employee],0): to get the percentage of the male employee
5.	%Female = DIVIDE([Female],[Total Employee],0): to get the percentage of the female  employee
6.	Due for promotion = CALCULATE([Total Employee],'HR Analytics Data'[Promotion]="Due for promotion"): to capture the number of employee due for promotion
7.	%Due for promotion = DIVIDE([Due for promotion],[Total Employee],0): to get the percentage of the employee due for promotion
8.	Not Due = CALCULATE([Total Employee],'HR Analytics Data'[Promotion]="Not yet due") : to capture the number of employee not yet due for promotion
9.	Active Workers = CALCULATE([Total Employee],'HR Analytics Data'[Retirement Status]="Not due for retirement"): to capture the number of active employees
10.	AttritionYes = CALCULATE([Total Employee],'HR Analytics Data'[Attrition]="Yes"): to capture the number of employee that has left the company
11.	%AttritionYes = DIVIDE([AttritionYes],[Total Employee],0): to capture the number of employee that has left the company in percentage
12.	AttritionNo = CALCULATE([Total Employee],'HR Analytics Data'[Attrition]="No"): to capture the number of employee that are still active in the company 
13.	%AttritionNo = DIVIDE([AttritionNo],[Total Employee])*100: to capture the number of employee that are still active in the company in percentage
14.	Contract = CALCULATE([Total Employee],'HR Analytics Data'[Contract type]= "Contract"): to capture  the number  of employee on contract bases. 
15.	Permanent = CALCULATE([Total Employee],'HR Analytics Data'[Contract type]= "Permanent"): to capture  the number  of employee on permanent bases.

### Visulaization

This project visualization was done with Power BI. It is a five (5) page dashboard with each pages holding different insights and also a navigation buttons section to help navigate from one page to another. 

### Key Insights from the Analysis
1.	The number and name of employee due for promotion
2.	The number and names of employee due for retirement due to age or number of years in service 
3.	The attrition rate of the company
4.	The performing department in term of monthly income
5.	The performance rating and job satisfaction rating of each Job roles and departments.
6.	The contract type performance

### Recommendations
1.	Employee that has work or function in a single post/position for 5years and above should be promoted based on their performance rating 
2.	Incentives should be provided for the contract employees so as to boast their performance.
3.	The company should set retirement age and also number of maximum years an employee can use in service.
4.	The HR should work more with the employee to beat down the attrition rate of the company.




