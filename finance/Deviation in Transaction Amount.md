# Deviation in Transaction Amount

# **Deviation in Transaction Amount**

This feature detects unusual instances where there is a deviation between the amount debited from the sender's account and the amount credited to the receiver's account. 

## **The idea behind**

The deviation in transaction amount feature is designed to flag instances where there is a significant difference between the amount debited and the amount credited during a financial transaction. While small deviations can be attributed to service provider charges, large discrepancies may indicate fraudulent transactions or errors. 

## **Methodology**

To create this feature, we subtract the amount credited from the amount debited and calculate the absolute difference. This value is then compared to a threshold value to determine if it is within an acceptable range. The threshold value can be set based on the typical charges levied by service providers or based on historical data on transaction amounts.

## **Data source**

The data source used for this feature is a transaction table containing the following columns:

- transaction_id: unique identifier for each transaction
- sender_account: the account number of the sender
- receiver_account: the account number of the receiver
- transaction_amount: the amount debited from the sender's account
- credit_amount: the amount credited to the receiver's account

An example table with 10 rows is shown below:

| transaction_id | sender_account | receiver_account | transaction_amount | credit_amount |
| --- | --- | --- | --- | --- |
| 1 | 123456789 | 987654321 | 1000 | 1000 |
| 2 | 456789123 | 321654987 | 500 | 500 |
| 3 | 789123456 | 654987321 | 750 | 750 |
| 4 | 159263478 | 456789321 | 100 | 99.5 |
| 5 | 963852741 | 258147369 | 2000 | 1998.5 |
| 6 | 852963741 | 369258147 | 1500 | 1505 |
| 7 | 741852963 | 147258369 | 3000 | 3010 |
| 8 | 321654987 | 456789123 | 250 | 252.5 |
| 9 | 654987321 | 789123456 | 1750 | 1748 |
| 10 | 258147369 | 963852741 | 5000 | 5015 |

## **SQL code**

The SQL code to create this feature is as follows:

```sql

SELECT transaction_id, sender_account, receiver_account, transaction_amount, credit_amount, ABS(transaction_amount - credit_amount) AS deviation_in_amount FROMtransaction_table;

```

## **Result table (example of how to calculate the feature)**

The resulting table will have an additional column named "deviation_in_amount" that calculates the absolute difference between the transaction amount and credit amount.

| transaction_id | sender_account | receiver_account | transaction_amount | credit_amount | deviation_in_amount |
| --- | --- | --- | --- | --- | --- |
| 1 | 123456789 | 987654321 | 1000 | 1000 | 0 |
| 2 | 456789123 | 321654987 | 500 | 500 | 0 |
| 3 | 789123456 | 654987321 | 750 | 750 | 0 |
| 4 | 159263478 | 456789321 | 100 | 99.5 | 0.5 |
| 5 | 963852741 | 258147369 | 2000 | 1998.5 | 1.5 |
| 6 | 852963741 | 369258147 | 1500 | 1505 | 5 |
| 7 | 741852963 | 147258369 | 3000 | 3010 | 10 |
| 8 | 321654987 | 456789123 | 250 | 252.5 | 2.5 |
| 9 | 654987321 | 789123456 | 1750 | 1748 | 2 |
| 10 | 258147369 | 963852741 | 5000 | 5015 | 15 |

## **Feature performance**

The deviation in transaction amount feature can be useful in identifying potential cases of transaction fraud or errors. However, its performance may be impacted by the threshold value used to determine what constitutes an acceptable deviation. In addition, the accuracy of this feature may be influenced by the quality and completeness of the data used to calculate it.

## **Additional Info**

Source: **[https://medium.com/analytics-vidhya/transaction-fraud-detection-%EF%B8%8F-%EF%B8%8F-automating-money-laundering-alerts-8d7d265befa9](https://medium.com/analytics-vidhya/transaction-fraud-detection-%EF%B8%8F-%EF%B8%8F-automating-money-laundering-alerts-8d7d265befa9)**
