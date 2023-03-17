# Income per Child

## **The idea behind**

This feature measures the amount of income per child dependent of the borrower and can be used to evaluate an individual's ability to support their dependents. It is  an important factor to consider when evaluating an individual's ability to repay a home loan, especially if they have dependents. Higher income per child dependent indicates a higher ability to support their dependents financially, which can increase the likelihood of loan repayment. It can also help lenders in determining the loan amount and repayment terms based on the borrower's financial capacity.

## **Methodology**

This feature INC_PER_CHLD can be calculated by dividing an individual's income by the number of child dependents they have.

### **Data source**

The data needed to create the  feature includes an individual's income and the number of child dependents they have.

Here is an example table with data that can be used to create the feature:

| borrower_id | income | num_children |
| --- | --- | --- |
| 1 | 50000 | 2 |
| 2 | 80000 | 3 |
| 3 | 60000 | 1 |
| 4 | 45000 | 2 |
| 5 | 70000 | 4 |
| 6 | 55000 | 1 |
| 7 | 90000 | 2 |
| 8 | 40000 | 0 |
| 9 | 75000 | 3 |
| 10 | 65000 | 2 |

### **Code**

To calculate the INC_PER_CHLD feature, the following SQL code can be used:

```sql
sqlCopy code
SELECT borrower_id, income / num_children AS INC_PER_CHLD FROM borrower_info;

```

### **Example**

Applying the SQL code above to the example data in the borrower_info table, we can create the following table with the INC_PER_CHLD feature:

| borrower_id | INC_PER_CHLD |
| --- | --- |
| 1 | 25000 |
| 2 | 26666.67 |
| 3 | 60000 |
| 4 | 22500 |
| 5 | 17500 |
| 6 | 55000 |
| 7 | 45000 |
| 8 | NULL |
| 9 | 25000 |
| 10 | 32500 |

## **Additional Info**

[https://www.kaggle.com/code/tunguz/xgb-simple-features](https://www.kaggle.com/code/tunguz/xgb-simple-features)
