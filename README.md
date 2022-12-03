# Job-Salaries-Estimator-for-Different-Data-Science-Positions-
Data Science positions are unique across the country so we can try and predict the salary of data science positions based on Job Title, Company, and Geography, etc. This project estimates salaries for different data science positions, so if anyone is trying to negotiate then this is a pretty cool tool for them to use.


## Web Scraping
Scraped the job descriptions from glassdoor.com using python and selenium. With each job, we obatin the following:

1. Job Title
2. Salary Estimate
3. Job Description
4. Rating
5. Company Name
6. Location
7. Headquarters
8. Size
9. Founded
10. Type of Ownernship
11. Industry
12. Sector
13. Revenue
14. Competitors

## Data Cleaning
After scraping the data I needed to clean it so that it can be usable for our model. I made the following modifications and created the following variables:

* Parsed only the numeric data out of Salary
* Made seperate columns for employer provided salary and hourly wages
* Salary column contained few empty values so removed the rows without Salary
* Parsed rating out of company text
* Made a seperate column for the Company State
* Made a new column to check if the job is at the company’s headquarters
* Added a new column age of company by using the founded date
* Added columns to check if the different skills were listed in the job description:
* Made a new column for simplified job title and Seniority
* Made a new column for description length

## Exploratory Data Analysis
EDA plays a very important role at this stage as the summarization of clean data helps in identifying the structure, outliers, anomalies, and patterns in data. I looked at the distributions of the data and the value counts for the various categorical variables. Have done the univariate, bivariate analysis, and plotted histograms,boxplots,bar graphs,pivot tables etc. to represent the data.

## Model Building
First, I modified all the categorical variables into dummy variables. Then I splited the data into training and test sets with a test size of 20%. I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is kind off easy to interpret and outliers aren’t particularly bad in for this type of model.

* Multiple Linear Regression: Base Model
* Lasso Regression: As there are any 0s and 1s(because of the sparse data from the many categorical variables), I have chosen a normalized regression like Lasso and thought it would be effective.
* Random Forest Regression – With the sparsity associated with the data, I thought that this would be a good fit for our data.

## Model Performance
The Random Forest model perfored better than the other models on the test set.

* Linear Regression MAE: 18.885
* Lasso Regression MAE: 19.665
* Random Forest Regression MAE: 11.142


