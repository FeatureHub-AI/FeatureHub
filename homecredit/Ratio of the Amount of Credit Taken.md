# Ratio of the Amount of Credit Taken to the Amount of Annuity to Be Paid by the Borrower

## **The idea behind**

We’d like to measure the ability of a borrower to pay back a loan, by comparing the amount of credit taken to the amount of annuity to be paid.

## **Methodology**

The methodology used to create this feature is simply taking the ratio of the amount of credit taken to the amount of annuity to be paid by the borrower.

### **Data source**

The data source needed for this feature includes the following columns:

- AMT_CREDIT: the amount of credit taken by the borrower
- AMT_ANNUITY: the amount of annuity to be paid by the borrower

As an example, we can create a table **`loan_info`** with the following columns and data:

| SK_ID_CURR | AMT_CREDIT | AMT_ANNUITY |
| --- | --- | --- |
| 100001 | 498960.0 | 9251.775 |
| 100002 | 406597.5 | 9251.775 |
| 100003 | 247500.0 | 21987.825 |
| 100004 | 180000.0 | 7312.725 |
| 100005 | 157500.0 | 6377.215 |
| 100006 | 625500.0 | 20361.600 |
| 100007 | 431280.0 | 16165.500 |
| 100008 | 328230.0 | 10368.750 |
| 100009 | 82065.0 | 3486.645 |
| 100010 | 461250.0 | 21865.500 |

### **Code**

```sql
sqlCopy code
SELECT SK_ID_CURR, AMT_CREDIT, AMT_ANNUITY, AMT_CREDIT / AMT_ANNUITY ASNEW_CREDIT_TO_ANNUITY_RATIO FROM loan_info;

```

### **Example**

Using the **`loan_info`** table above, the SQL code will produce the following table:

| SK_ID_CURR | AMT_CREDIT | AMT_ANNUITY | NEW_CREDIT_TO_ANNUITY_RATIO |
| --- | --- | --- | --- |
| 100001 | 50000 | 5000 | 10.0 |
| 100002 | 100000 | 7500 | 13.33 |
| 100003 | 200000 | 10000 | 20.0 |
| 100004 | 75000 | 6000 | 12.5 |
| 100005 | 120000 | 9000 | 13.33 |
| 100006 | 300000 | 15000 | 20.0 |
| 100007 | 250000 | 12500 | 20.0 |
| 100008 | 80000 | 8000 | 10.0 |
| 100009 | 150000 | 7500 | 20.0 |

## Additional Info

[https://www.kaggle.com/code/tunguz/xgb-simple-features](https://www.kaggle.com/code/tunguz/xgb-simple-features)
