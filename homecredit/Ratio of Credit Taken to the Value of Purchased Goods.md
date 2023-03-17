# The Ratio of the Amount of Credit Taken to the Value of the Goods or Property Being Purchased

## **The idea behind**

This feature measures the ratio of the amount of credit taken to the value of the goods or property being purchased, and can be used to assess an individual's financial health and creditworthiness. A high ratio may suggest that an individual is taking on too much debt relative to their assets, which could lead to financial difficulties, while a low ratio may indicate a more conservative approach to borrowing and managing finances. This information can be useful for lenders, creditors, and financial institutions to evaluate credit risk and make informed lending decisions.

## **Methodology**

To calculate the NEW_CREDIT_TO_GOODS_RATIO, we use the formula:

```sql
makefileCopy code
NEW_CREDIT_TO_GOODS_RATIO = Total Credit Amount / Total Value of Goods or Property

```

### **Data source**

The data source required for this feature includes two columns:

- **`Credit Amount`**: the total amount of credit taken by the individual.
- **`Value of Goods or Property`**: the total value of the goods or property being purchased.

Below is an example table with 10 rows of data:

| Credit Amount | Value of Goods or Property |
| --- | --- |
| 1000 | 5000 |
| 500 | 2000 |
| 2000 | 10000 |
| 10000 | 50000 |
| 5000 | 15000 |
| 1000 | 5000 |
| 3000 | 12000 |
| 8000 | 32000 |
| 4000 | 16000 |
| 200 | 1000 |

### **Code**

To assemble the NEW_CREDIT_TO_GOODS_RATIO feature using SQL code, we can use the following query:

```
sqlCopy code
SELECT (SUM(`Credit Amount`) / SUM(`Value of Goods or Property`)) AS`NEW_CREDIT_TO_GOODS_RATIO` FROM example_table;

```

### E**xample**

Using the above SQL code, we can assemble the NEW_CREDIT_TO_GOODS_RATIO feature as follows:

| Credit Amount | Value of Goods or Property | NEW_CREDIT_TO_GOODS_RATIO |
| --- | --- | --- |
| 1000 | 5000 | 0.2 |
| 500 | 2000 | 0.25 |
| 2000 | 10000 | 0.2 |
| 10000 | 50000 | 0.2 |
| 5000 | 15000 | 0.3333 |
| 1000 | 5000 | 0.2 |
| 3000 | 12000 | 0.25 |
| 8000 | 32000 | 0.25 |
| 4000 | 16000 | 0.25 |
| 200 | 1000 | 0.2 |

## **Additional Info**

[https://www.kaggle.com/code/tunguz/xgb-simple-features](https://www.kaggle.com/code/tunguz/xgb-simple-features)
