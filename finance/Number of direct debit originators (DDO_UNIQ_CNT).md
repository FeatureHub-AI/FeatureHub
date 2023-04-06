# Number of direct debit originators (DDO_UNIQ_CNT)

Counts the number of direct debit originators that have initiated at least one direct debit transaction per defined period per client

## **The idea behind**

A large number of direct debit originators indicate that this bank account  is actively being used and the client most likely has high trust in the bank or /and doesn't have any alternatives.

## **Methodology**

The feature counts the number of unique direct debit originators that have initiated at least one direct debit transaction per defined period. This feature is created using the transaction table with client_id, transaction_id, operation_date, counterpart_name, and transaction_method columns. We filter for direct debit transactions (transaction_method = 'direct_debit') and then count the unique counterpart names for each client for each defined period.

### **Data source**

The data source is a transaction table with columns:

| Column Name | Description |
| --- | --- |
| client_id | Unique identifier of the client |
| transaction_id | Unique identifier of the transaction |
| operation_date | Date when the transaction occurred |
| counterpart_name | Name of the other party involved in a financial transaction |
| transaction_method | Method used to make the transaction (direct_debit, card, transfer) |

Here is an example of the transaction table

| client_id | transaction_id | operation_date | counterpart_name | transaction_method |
| --- | --- | --- | --- | --- |
| 1 | 1 | 2023-02-20 | Telecom | direct_debit |
| 1 | 2 | 2023-03-01 | Restaurant | card |
| 1 | 3 | 2023-03-02 | Social Security | direct_debit |
| 1 | 4 | 2022-03-02 | Telecom | direct_debit |
| 1 | 12 | 2023-03-01 | Accountant | direct_debit |
| 2 | 13 | 2023-03-01 | Telecom | direct_debit |
| 3 | 14 | 2023-03-15 | Accountant | direct_debit |
| 4 | 15 | 2023-03-20 | Carwash | card |

### **Variables**

 **DDO_UNIQ_CNT_M1**: Number of direct debit originators, month 1.

 **DDO_UNIQ_CNT_3M**: Number of direct debit originators, for 3 months.

 **DDO_UNIQ_CNT_6M**: Number of direct debit originators, for 6 months.

 **DDO_UNIQ_CNT_12M**: Number of direct debit originators, for 12 months.

### **Code**

For **DDO_UNIQ_CNT_M1**: Number of direct debit originators, month 1.

```sql
SELECT
    client_id,
    COUNT(DISTINCT counterpart_name) AS DDO_UNIQ_CNT_M1
FROM
    transactions
WHERE
    transaction_method = 'direct_debit'
    AND operation_date >= DATE_ADD(scoring_date, INTERVAL -1 MONTH)
GROUP BY
    client_id
```

### ****Assembling example****

For **DDO_UNIQ_CNT_M1**: Number of direct debit originators, month 1.

From the data source example

| client_id | DDO_UNIQ_CNT_M1 |
| --- | --- |
| 1 | 3 |
| 2 | 1 |
| 3 | 1 |
| 4 | 0 |

## **Feature performance**

The DDO_UNIQ_CNT is one of the top 50 important features for churn prediction and LTV models.
