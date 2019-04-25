## Loan grade clasification and expected default rate prediction using ML
#### Based on LendingClub transactions

#### Vilma Daukantaite
###### Data Analytics Bootcamp / Ironhack Barcelona Campus / April 2019

### Overview

![alt text](https://github.com/VilmaDaukantaite/final_project/blob/master/Images/Idea_flow.png) 


My questions were:

* What factors influence the grade as a borrower in the US?
* What are the most common purpose for the loan?
* Building ML model for classifying borrowers/loans (Decision Tree, Random Forest)

Success evaluated using Score value and confusion matrix.

Classification techniques are already widely used in order to speed up transactions and automatize certain processes. 


###### Extra topics

* Painting US household financial profile (debt/savings balance) 


I believe there is enough of data available. However limitation might come from the fact that there is less data points for the earlier periods as compared to 2018



### Data Preparation

Overview:
* My dataset contains information on loans funded via lending club, each row represents one row with 151 features describing the borrower.

* Origin of the dataset is:
https://www.lendingclub.com/info/download-data.action
* I am using an aggregated dataset for the same data from:
https://www.kaggle.com/wordsforthewise/lending-club

Data set is 618MB (compressed size), 151 columns and over 2.2M entries. Due to NaN values some numeric and datetime columns have been imported as objects and will need to be changed. For machine learning some of the categorical columns (that I believe are significant) might need to be one-hot encoded.


### Data Ingestion & Database


I have used read_csv to load and explore data in my local repository. I could not upload my datasets to GitHub as there is a limit for file size. I have uploaded a sample data base (1000 entry sample to demonstrate how it could be modeled)

Schema of db tables:

![alt text](https://github.com/VilmaDaukantaite/final_project/blob/master/Images/DB_schema.png)

### Data Wrangling and Cleaning

![alt text](https://github.com/VilmaDaukantaite/final_project/blob/master/Images/Data_cleaning.png)

* Checking the shape, head, isna, dtypes
* Fixing dtypes where necesairy
* Dropping columns related to post loan measurements 



### Data Analysis

Comparing two periods 2007-2011 and 2016-2018

* Checked the structure of loans by purpose
* Checked loan distribution by grade
* Checked loan distribution by term length
* Loan distribution by property ownership
* Loan distribution by employment length
* Relationship between fico score (credit rating) and interest rate
* Evolution of interest rate as well as mean asking loan amount
* Relationship between loan grade and interest rate/fico rate/term

For ML model removed all features that had low variability, were related to post loan activities, were categorical variables with too many categories.


### Model Training and Evaluation

First I have chosen to use Decision tree classifier to predict the grade of the loan. 
To choose the optimal hyper parameters I ran cross-validation, iterating over the depth of the tree coming up with depth of 10 for 2007-2011 and 5 for 2016-2018 as the line at which tree accuracy stoped improving.

After printing and checking the decision tree image I realized that interest_rate parameter should be dropped before running the model as after some research I found out is highly dependent on the Grade of Loan that gets assigned. 

Therefore I ran the models again without this parameter and accuracy significantly dropped.

I also tried Random forest and KNN models but their results were coming back even worse and would have needed a lot more hyper parameter and feature tweaking in order for them to be reliable.


### Conclusion

* The LoanClub business is booming as Americans have high personal debts and need debt consolidation
* Highest influence on your Loan grade as well as interest rate among others comes from:
1) Credit Score
2) Term for which you want the loan
3) Annual income
4) Debt to income ratio
5) Amount of credit inquiries in the last 12 months

* ML models can seem deceivingly accurate so always checking needs to be done from all angles

### What are the next steps? 

As further steps I would like to:
* improve current models, or find more accurate models for prediction
* obtain information for European market to be able to compare the profiles

