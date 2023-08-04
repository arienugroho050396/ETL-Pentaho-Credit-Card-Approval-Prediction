# ETL-Pentaho-Credit-Card-Approval-Prediction
[*here you can download the cheatsheet*](https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction)  

## Introduction   
Credit score cards are a widely employed risk management approach in the financial industry. They leverage personal information and data provided by credit card applicants to assess the likelihood of potential defaults and credit card usage. By doing so, banks can make informed decisions on whether to grant credit cards to applicants. Credit scores provide an objective measure of risk magnitude, allowing for a more precise evaluation of creditworthiness.

## Objective 
- Perform ETL using PDI for both datasets.
- Create time dimension using PDI.
- Create fact table using PDI.

## Content 
This repository contains ETL file using Pentaho Data Integration (PDI).

## Data Field   
### Application Record :
| Variable Name | Description |
| --- | --- |
| `ID` | Customer's unique identifier |
| `Code_Gender` | Gender |
| `Flag_Own_Car` | Is there a car |
| `Flag_Own_Realty` | Is there a property |
| `CNT_Children` | Number of children |
| `AMT_Income_Total` | Annual income |
| `Name_Income_Type` | 	Income category |
| `Name_Education_Type` | Education level |
| `Name_Family_Status` | Marital status |
| `Name_Housing_Type` | Way of living  |
| `Days_Birth` | 	Birthday |
| `Days_Employed` | Start date of employment |
| `Flag_Mobil` | Is there a mobile phone |
| `Flag_Work_Phone` | Is there a work phone |
| `Flag_Phone` | Is there a phone |
| `Flag_Email` | Is there an email |
| `Occupation_Type` | Occupation |
| `Cnt_Family_Members` | Family Size |


### Credit Record :
| Variable Name | Description | Remarks |
| --- | --- | --- |
| `ID` | Client number |  |
| `MONTHS_BALANCE` | Record month | The month of the extracted data is the starting point, backwards, 0 is the current month, -1 is the previous month, and so on |
| `STATUS` | Status | 0: 1-29 days past due 1: 30-59 days past due 2: 60-89 days overdue 3: 90-119 days overdue 4: 120-149 days overdue 5: Overdue or bad debts, write-offs for more than 150 days C: paid off that month X: No loan for the month |

## ETL Process
![This is an image](https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/ETL%20Process.JPG)

## Application Record
### CSV File Input
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/CSV%20file%20input%20(app).JPG" alt="This is an image" width="500">
- importing data application record CSV

### Sort Rows
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Sort%20Row%20(app).JPG" alt="This is an image" width="500">
- Sort data based on ID (in ascending order)

### Unique Rows
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Unique%20Row%20(app).JPG" alt="This is an image" width="400">
- Filtering duplicate ID

### Replace in String
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Replace%20in%20String%20(app).JPG" alt="This is an image" width="500">
- Replacing 'Y' with 1, and 'N' with 0

### Add Constants
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Add%20Constrant%20(app).JPG" alt="This is an image" width="500">
- Adding 'Current_Date' column

### Calculator
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Calculator%20(app).JPG" alt="This is an image" width="600">
- Calculating applicant age and how long applicant have been working (in years)

### Filter Rows
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Filter%20Row%20(app).JPG" alt="This is an image" width="500">
- Filter the data applicant that is less than 21 years old
- Filter the data applicant with null/empty values

## Credit Record
### CSV File Input
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/CSV%20File%20Input%20(credit).JPG" alt="This is an image" width="500">
- Importing data credit record CSV

### Sort Rows 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Sort%20Row%20(credit).JPG" alt="This is an image" width="500">
- Sort data based on ID (in ascending order)

### Add Constants 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Add%20Constrant%202%20(credit).JPG" alt="This is an image" width="500">
- Adding 'Current_Date' column

### Calculator 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Calculator%20(credit).JPG" alt="This is an image" width="600">
- Calculating month loan payment
- Creating copy of 'status' column

### Replace in String 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Replace%20in%20String%202%20(credit).JPG" alt="This is an image" width="600">
- Replace C, X, 0 with 'Good Debt' (C: loan for that month is already paid; X: no loan for that month; 0: loan is 1 to 29 days overdue).
- Replace 1, 2, 3, 4, 5 with 'Bad Debt' (1: loan is 30 to 59 days overdue; 2: loan is 60 to 89 days overdue; 3: loan is 90 to 119 days overdue; 4: loan is 120 to 149 days overdue; 5: loan is more than 150 days overdue).

### Calculator 3
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Calculator%203%20(credit).JPG" alt="This is an image" width="600">
- Creating 2 copies of 'STATUS2' column (Good_Debt and Bad_Debt).

### Replace in String 3
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Replace%20in%20String%203%20(credit).JPG" alt="This is an image" width="600">
- Good_Debt: Good Debt will be change to 1, while Bad Debt will be change to 0.
- Bad_Debt: Good Debt will be change to 0, while Bad Debt will be change to 1.

### Filter Rows 3
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Filter%20Row%203%20(credit).JPG" alt="This is an image" width="500">


### Select Values 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Select%20Values%202%20(credit).JPG" alt="This is an image" width="500">

### Group By
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Group%20By%20(credit).JPG" alt="This is an image" width="500">
- Calculating total of Good Debt and Bad Debt from each applicant (similar to group by function in SQL).

### Modified Javascript Value
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Modified%20Javascript%20Value%20(credit).JPG" alt="This is an image" width="500">
- If the total of Good Debt is higher than Bad Debt, then an applicant status will be eligible (1).
- If the total of Bad Debt is higher than Good Debt, then an applicant status will be not eligible (0). 


## Output Join Application Record and Credit Record
### Stream Lookup
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Stream%20Lookup%20(app).JPG" alt="This is an image" width="500">
- Bad_Debt_CNT, Good_Debt_CNT, and STATUS will be merged based on applicant ID.

### Filter Rows 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Filter%20Row%202.JPG" alt="This is an image" width="500">
- Applicant with empty Bad_Debt_CNT, Good_Debt_CNT, and STATUS will be deleted.

### Select Values
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Select%20Values.JPG" alt="This is an image" width="500">
- Select columns that will extracted.

### Text File Output
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Text%20File%20Output.JPG" alt="This is an image" width="500">
- Exporting cleaned and transformed data set into CSV file.

## Output :
**Preview data from the output table**

<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/output1.JPG" alt="This is an image" width="700">
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/output%202.JPG" alt="This is an image" width="700">

