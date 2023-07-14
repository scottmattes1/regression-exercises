
***
[[Project Description]]
[[Objectives]]
[[Project Planning]]
[[Key Findings]]
[[Recommendations]]
[[Next Steps]]
[[Steps to Reproduce]]
[[Data Exploration]]
[[Modeling]]
[[Conclusion]]
[[Data Dictionary]]
___



Project Description
-----------------
Follow the data science pipeline to find insights to present to the Zillow Data Science team on how to improve model performance to predict home values; identify the location of each transaction. Produce a GitHub repository and a final notebook from which to present findings.



Objectives
-----------------
For the Zillow Data Science team:
1. Provide recommendations on how to build a better model (things that do and don't work
2. Determine the states and counties where the fips are located



Key Findings
-----------------
1. The bedrooms relationship to home_value is extremely weak yet significant¶

2. The square_feet relationship to home_value is very strong and significant

3. Bedrooms and square_feet have some degree of multicolinearity, however there is high variance in the relationship so both features will still be taken to modeling



Recommendations
-----------------
1. Merging the bedrooms and bathrooms information into a ratio does not add value to a model because it increases feature variance when plotted against home_value. Do not combine these features in future models.

2. Eliminating outliers in the home value distribution will increase model performance. Only 10% of the transactions are above 1M, eliminating these from the data set reduces heteroskedasticity and improves model performance.

3. The dataframe I was able to create which matches state and county information to each transaction id may be added to the Zillow database server, possibly using transaction 'id' as the primary key and 'fips' as a foreign key.



Modeling
-----------------------
The best performing regression model on this data set was a LassoLars model with an alpha of .01 which performed on test data with an RMSE of $207,884




Next Steps
-----------------
To further improve model performance, feature selection methods may be used to determine other columns in the data that can add predictive power to future models.



Steps to Reproduce
-----------------------
env.py file with credentials to access the codeup database
clone this repository
copy the exact imports used in the final notebook and run the code

If you would like to reproduce the dataframe which matches transaction id's to county and state information, follow the hyperlink given in the 'State and County' data section of the notebook and save it to the directory where the final_notebook is stored, then, run the cell blocks below the 'State and County' markdown
        

Data Dictionary
------------------
Column Name                  Description
------------------------------------------------------------------------------
home_value                    The taxable value of each home. Given as a float.
square_feet                   The square footage of each home. Given as a float.
bedrooms                      The bedroom count of each home. Given as a float.







