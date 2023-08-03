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

### Sort Rows
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Sort%20Row%20(app).JPG" alt="This is an image" width="500">

### Unique Rows
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Unique%20Row%20(app).JPG" alt="This is an image" width="400">

### Replace in String
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Replace%20in%20String%20(app).JPG" alt="This is an image" width="500">

### Add Constants
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Add%20Constrant%20(app).JPG" alt="This is an image" width="500">

### Calculator
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Calculator%20(app).JPG" alt="This is an image" width="600">

### Filter Rows
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Filter%20Row%20(app).JPG" alt="This is an image" width="500">

## Credit Record
### CSV File Input
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/CSV%20File%20Input%20(credit).JPG" alt="This is an image" width="500">

### Sort Rows 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Sort%20Row%20(credit).JPG" alt="This is an image" width="500">

### Add Constants 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Add%20Constrant%202%20(credit).JPG" alt="This is an image" width="500">

### Calculator 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Calculator%20(credit).JPG" alt="This is an image" width="600">

### Replace in String 2
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Replace%20in%20String%202%20(credit).JPG" alt="This is an image" width="600">

### Calculator 3
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Calculator%203%20(credit).JPG" alt="This is an image" width="600">

### Replace in String 3
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Replace%20in%20String%203%20(credit).JPG" alt="This is an image" width="600">

### Group By
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Group%20By%20(credit).JPG" alt="This is an image" width="500">

### Modified Javascript Value
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Modified%20Javascript%20Value%20(credit).JPG" alt="This is an image" width="500">

## Output Join Application Record and Credit Record
### Stream Lookup
<img src="https://github.com/arienugroho050396/ETL-Pentaho-Credit-Card-Approval-Prediction/blob/main/Pentaho%20SS/Stream%20Lookup%20(app).JPG" alt="This is an image" width="500">



