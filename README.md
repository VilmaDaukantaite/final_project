## Loan grade clasification and expected default rate prediction using ML
#### Based on LendingClub transactions

#### Vilma Daukantaite
###### Data Analytics Bootcamp / Ironhack Barcelona Campus / April 2019

### Overview

* What factors influence your grade as a borrower?
* Was there a significant difference in default on loans during 2007-2011 as compared to now?
* Building ML model for classifying borrowers/loans 
* Building ML model for estimating expected default rate

I am sure these techniques are already widely used in order to speed up transactions and automatize certain processes. 

* Hypothesis testing:

H0 - there was no difference between default rate during 2007-2011 and 2013-2018

H1 - there was a significant difference between default rate during 2007-2011 and 2013-2018

I believe there is enough of data available. However limitation might come from the fact that there is less data points for the earlier periods as compared to 2018

* How will you test your hypothesis? 

Two sample t test for difference of means

* How will you test your success?




### Data Preparation
Overview:
* My dataset contains information on loans funded via lending club, each row represents one row with 151 features describing the borrower.

* Origin of the dataset is:
https://www.lendingclub.com/info/download-data.action
* I am using an aggregated dataset for the same data from:
https://www.kaggle.com/wordsforthewise/lending-club

Data set is 618MB (compressed size), 151 columns and over 2.2M entries. Due to NaN values some numeric and datetime columns have been imported as objects and will need to be changed. For machine learning some of the categorical columns (that I believe are significant) might need to be one-hot encoded.

### Data Ingestion & Database

For now using read_csv to load and explore data before migrating data to a database

* If you downloaded a dataset (either public or private), describe where you downloaded it and include the command to load the dataset.
* Provide a schema of your tables.

### Data Wrangling and Cleaning

* Checking the shape, head, isna, dtypes
* Dropping columns that have majority of data missing
* Fixing dtypes where necessairy

Your full process of data wrangling and cleaning.
* Document your workflow and thinking process.

### Data Analysis
* Overview the general steps you will go through to analyze your data in order to test your hypothesis.
* Document each step of your data exploration and analysis.
* Print charts to demonstrate the effect of your work. Charts make your presentation look good too.
* If you use ML in your final project, also describe your feature selection process.

### Model Training and Evaluation
* Train your ML model, produce results, and evaluate.
* This is an iterative process. Try your best to improve your model performance by:
  * Try different models and select one that is the simplest yet produce the best result.
  * Try advanced techniques and see if they improve the result.

### Conclusion
* Summarize your data analysis result.
* State your conclusion of your hypothesis testing.
* Interpret your findings in terms of the human-understandable question you try to answer.

### What are the next steps?
