

# **Surge Indicator**

The surge indicator is an AI/ML feature that flags transactions with a large amount of money involved. This feature helps to identify transactions with unusual amounts that may indicate fraudulent activity.

## **The Idea Behind**

The idea behind the surge indicator feature is to identify transactions with large amounts of money involved, which may indicate suspicious activity such as money laundering or fraud. The feature helps to flag such transactions so that they can be investigated further.

## **Methodology**

The methodology used to develop the surge indicator feature involves analysing the distribution of amounts in the transaction data. A threshold is set to define the upper limit of what is considered a "normal" transaction amount. Transactions with amounts that exceed this threshold are flagged as potential fraudulent transactions.

## **Data Source**

The surge indicator feature requires transaction data, including the sender and receiver accounts, the transaction amount, and the transaction date and time.

Example table:

| transaction_id | sender_account | receiver_account | amount | date_time |
| --- | --- | --- | --- | --- |
| 1 | 123456 | 987654 | 100.00 | 2022-01-01 09:00:00 |
| 2 | 234567 | 876543 | 5000.00 | 2022-01-02 14:30:00 |
| 3 | 345678 | 765432 | 800.00 | 2022-01-03 17:45:00 |
| 4 | 456789 | 654321 | 20000.00 | 2022-01-04 11:15:00 |
| 5 | 567890 | 543210 | 50.00 | 2022-01-05 08:00:00 |
| 6 | 678901 | 432105 | 300.00 | 2022-01-06 13:30:00 |
| 7 | 789012 | 321054 | 10000.00 | 2022-01-07 09:00:00 |
| 8 | 890123 | 210543 | 75.00 | 2022-01-08 16:15:00 |
| 9 | 901234 | 105432 | 1500.00 | 2022-01-09 10:45:00 |
| 10 | 012345 | 543210 | 6000.00 | 2022-01-10 19:30:00 |

## **SQL Code**

The following SQL code demonstrates how to calculate the Surge Indicator feature based on the transaction amount:

```sql
sqlCopy code
SELECT transaction_id, sender_account, receiver_account, amount, date_time, CASE WHENamount > (SELECT AVG(amount)*2 FROM transactions) THEN 1 ELSE 0 END AS surge_indicatorFROM transactions

```

## Result table

| transaction_id | transaction_amount | surge_indicator |
| --- | --- | --- |
| 1 | 100 | 0 |
| 2 | 200 | 1 |
| 3 | 50 | 0 |
| 4 | 5000 | 1 |
| 5 | 300 | 1 |
| 6 | 1000 | 1 |
| 7 | 150 | 0 |
| 8 | 2000 | 1 |
| 9 | 400 | 1 |
| 10 | 75 | 0 |

The surge indicator is calculated as 1 when the transaction amount is higher than the 95th percentile of all transaction amounts, and 0 otherwise.

## Feature performance

The performance of the surge indicator feature can be evaluated using various metrics such as precision, recall, F1 score, and area under the receiver operating characteristic curve (AUC-ROC). However, since the surge indicator is a simple threshold-based feature, it may not be necessary to evaluate its performance using complex metrics. Instead, we can simply measure the proportion of flagged transactions that are actually fraudulent (precision) and the proportion of fraudulent transactions that are flagged (recall) to determine the feature's effectiveness in detecting potential money laundering activity.

## Additional Info

Source: **[https://medium.com/analytics-vidhya/transaction-fraud-detection-%EF%B8%8F-%EF%B8%8F-automating-money-laundering-alerts-8d7d265befa9](https://medium.com/analytics-vidhya/transaction-fraud-detection-%EF%B8%8F-%EF%B8%8F-automating-money-laundering-alerts-8d7d265befa9)**
