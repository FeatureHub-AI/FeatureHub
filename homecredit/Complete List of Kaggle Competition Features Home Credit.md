
# From Kaggler: https://www.kaggle.com/code/tunguz/xgb-simple-features

### Pre-processed

1. **`NEW_CREDIT_TO_ANNUITY_RATIO`**: The ratio of the amount of credit taken to the amount of annuity to be paid by the borrower
2. **`NEW_CREDIT_TO_GOODS_RATIO`**: The ratio of the amount of credit taken to the value of the goods or property being purchased.
3. **`NEW_DOC_IND_KURT`**: Kurtosis of document-related features.
4. **`NEW_LIVE_IND_SUM`**: The sum of binary indicators for whether the borrower has a permanent or temporary residence.
5. **`NEW_INC_PER_CHLD`**: The amount of income per child dependent of the borrower. 
6. **`NEW_INC_BY_ORG`**: The median income of borrowers grouped by organization type.
7. **`NEW_EMPLOY_TO_BIRTH_RATIO`**: The ratio of days employed to the borrower's age in days.
8. **`NEW_ANNUITY_TO_INCOME_RATIO`**: The ratio of the amount of annuity to be paid to the borrower's total income.
9. **`NEW_SOURCES_PROD`**: The product of three external sources of data provided by the borrower.
10. **`NEW_EXT_SOURCES_MEAN`**: The mean of three external sources of data provided by the borrower.
11. **`NEW_SCORES_STD`**: The standard deviation of three external sources of data provided by the borrower.
12. **`NEW_CAR_TO_BIRTH_RATIO`**: The ratio of days the borrower owns a car to the borrower's age in days.
13. **`NEW_CAR_TO_EMPLOY_RATIO`**: The ratio of days the borrower owns a car to the number of days employed.
14. **`NEW_PHONE_TO_BIRTH_RATIO`**: The ratio of the number of days since the borrower last changed their phone number to the borrower's age in days.
15. **`NEW_CREDIT_TO_INCOME_RATIO`**: The ratio of the amount of credit taken to the borrower's total income.
16. One-hot encoded categorical features: These features indicate the presence or absence of a category for each categorical variable in the dataset. The **`dummy_na=True`** parameter creates an additional column indicating missing values for each categorical feature.

### **Categorical**

1.  **`CODE_GENDER`**: Binary encoded categorical feature indicating gender of the client. 0 represents male and 1 represents female.
2.  **`FLAG_OWN_CAR`**: Binary encoded categorical feature indicating whether the client owns a car or not. 0 represents no car and 1 represents owning a car
3.  **`FLAG_OWN_REALTY`**: Binary encoded categorical feature indicating whether the client owns a property or not. 0 represents no property and 1 represents owning a property
4.  **`cat_cols`**: A list of categorical features after performing one-hot encoding on the dataset.
5. **`DAYS_EMPLOYED_PERC`**: A new feature representing the percentage of the days of employment with respect to the days of birth.
6. **`INCOME_CREDIT_PERC`**: A new feature representing the ratio of the income of the client to the amount of credit requested.
7. **`INCOME_PER_PERSON`**: A new feature representing the income of the client divided by the number of family members.
8. **`ANNUITY_INCOME_PERC`**: A new feature representing the ratio of the annuity payment to the income of the client.
9. **`PAYMENT_RATE`**: A new feature representing the ratio of the annuity payment to the amount of credit requested.
10. **`bureau`**: A pandas dataframe containing data from the bureau.csv file.
11.  **`bb`**: A pandas dataframe containing data from the bureau_balance.csv file.
12. **`bb_cat`**: A list of categorical features after performing one-hot encoding on the bureau_balance dataset.
13.  **`bureau_cat`**: A list of categorical features after performing one-hot encoding on the bureau dataset.

### Numeric

1. **`DAYS_CREDIT_mean`**: Mean of days between current loan application and previous loans taken by the client
2. **`DAYS_CREDIT_var`**: Variance of days between current loan application and previous loans taken by the client
3. **`DAYS_CREDIT_ENDDATE_mean`**: Mean of days between the end date of the previous credit and the current application date
4. **`DAYS_CREDIT_UPDATE_mean`**: Mean of the difference between the credit bureau update date and the current application date
5. **`CREDIT_DAY_OVERDUE_mean`**: Mean of days past due on the most overdue credit in Bureau records
6. **`AMT_CREDIT_MAX_OVERDUE_mean`**: Mean of maximum amount overdue on credit in Bureau records
7. **`AMT_CREDIT_SUM_mean`**: Mean of current credit amount for all loans taken by the client
8. **`AMT_CREDIT_SUM_sum`**: Total current credit amount for all loans taken by the client
9. **`AMT_CREDIT_SUM_DEBT_mean`**: Mean of current debt on all loans taken by the client
10. **`AMT_CREDIT_SUM_DEBT_sum`**: Total current debt on all loans taken by the client
11. **`AMT_CREDIT_SUM_OVERDUE_mean`**: Mean of current amount overdue on all loans taken by the client
12. **`AMT_CREDIT_SUM_LIMIT_mean`**: Mean of current credit limit of credit card reported in Bureau records
13. **`AMT_CREDIT_SUM_LIMIT_sum`**: Total current credit limit of credit card reported in Bureau records
14. **`AMT_ANNUITY_max`**: Maximum amount of loan annuity in Bureau records
15. **`AMT_ANNUITY_mean`**: Mean of loan annuity in Bureau records
16. **`CNT_CREDIT_PROLONG_sum`**: Total number of times credit was prolonged
17. **`MONTHS_BALANCE_MIN_min`**: Minimum of the monthly balance of previous credits in Bureau records before the application date of the current loan
18. **`MONTHS_BALANCE_MAX_max`**: Maximum of the monthly balance of previous credits in Bureau records before the application date of the current loan
19. **`MONTHS_BALANCE_SIZE_mean`**: Mean number of months in which Bureau had a record of previous credits of the client before the application date of the current loan
20. **`MONTHS_BALANCE_SIZE_sum`**: Total number of months in which Bureau had a record of previous credits of the client before the application date of the current loan.
21. **`AMT_ANNUITY`**: The maximum and mean value of the annuity amount of the previous application.
22. **`AMT_APPLICATION`**: The minimum and mean value of the amount applied for by the client in the previous application.
23. **`AMT_CREDIT`**: The minimum, maximum and mean value of the credit amount of the previous application.
24. **`APP_CREDIT_PERC`**: The minimum, maximum and mean value of the percentage of the credit amount requested with respect to the application amount.
25. **`AMT_DOWN_PAYMENT`**: The minimum, maximum and mean value of the down payment on the previous application.
26. **`AMT_GOODS_PRICE`**: The minimum, maximum and mean value of the price of the goods for which the loan is given on the previous application.
27. **`HOUR_APPR_PROCESS_START`**: The minimum, maximum and mean value of the hour of the day when the previous application was submitted.
28. **`RATE_DOWN_PAYMENT`**: The minimum, maximum and mean value of the down payment rate normalized on the previous application.
29. **`DAYS_DECISION`**: The minimum, maximum and mean value of the number of days since the previous application when the decision to grant the loan was made.
30. **`CNT_PAYMENT`**: The mean and sum of the number of payments that the client has to make on the previous loan.
