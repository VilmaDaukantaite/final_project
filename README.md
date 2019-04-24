## Loan grade clasification and expected default rate prediction using ML
#### Based on LendingClub transactions

#### Vilma Daukantaite
###### Data Analytics Bootcamp / Ironhack Barcelona Campus / April 2019

### Overview

I was curious to see the differences between house ownership rate in countries and underlying reasons for it. Which led me to explore Household financial structure (savings/debt). And I ended up with curiosity on what elements influence your grade as a borrower of consumption loans. Due to limitations of getting data i chose to explore LendingClub transactions dataset that is openly available.

My questions are:

* What factors influence your grade as a borrower in the US?
* What are the most common purpose for the loan?
* Building ML model for classifying borrowers/loans (Decision Tree)

Success evaluated using Decision Tree Score value and confusion matrix.

Classification techniques are already widely used in order to speed up transactions and automatize certain processes. 


###### Extra topics

* Painting US household financial profile? (debt/savings balance) 


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

* Provide a schema of your tables.

### Data Wrangling and Cleaning

* Checking the shape, head, isna, dtypes

* Dropping columns that have majority of data missing
* Fixing dtypes where necesairy

Your full process of data wrangling and cleaning.
* Document your workflow and thinking process.

### Data Analysis


### Model Training and Evaluation

I have chose to use Decision tree classifier to predict the grade of the loan. 
To choose the optimal hyper parameters I ran crossvaligdation iterating over the depth of the tree coming up with depth of 10 for 2007-2011 and 5 for 2016-2018.

After printing and checking the decision tree image I realized that interest_rate parameter should be dropped before running the model as it is highly dependent on the Grade of Loan that gets assigned. 

Therefore I ran the models again without this parameter and accuracy significantly dropped.


### Conclusion
* Summarize your data analysis result.
* State your conclusion of your hypothesis testing.
* Interpret your findings in terms of the human-understandable question you try to answer.

### What are the next steps?
