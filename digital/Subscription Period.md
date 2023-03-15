

# **Subscription Period**

This feature refers to the length of time that a user subscribes to a product or service, typically for a recurring payment.

## **The Idea Behind**

The subscription period has a significant impact on the lifetime value of an app user. The length of the subscription period can be used as an indicator of customer’s loyalty and engagement. We expect users who commit to longer subscription periods are more likely to have a vested interest in the app. 

## **Methodology**

To calculate the subscription period, we follow these steps:

1. Determine the start date of the subscription. This is the date when the user first subscribed to the app.
2. Determine the end date of the subscription. This is the date when the user cancels their subscription or when the subscription expires.
3. Calculate the subscription length. This is the length of time that the user has been subscribed to the app, and can be calculated by subtracting the start date from the end date.

### **Data Source**

The data source used for calculating the subscription period is the subscription history table. This table includes the user ID, start date, and end date of each subscription. An example of the subscription history table is shown below:

| user_id | start_date | end_date |
| --- | --- | --- |
| 1 | 2022-01-01 | 2022-06-30 |
| 2 | 2021-10-01 | 2022-12-31 |
| 3 | 2022-02-15 | 2022-03-15 |
| 4 | 2022-01-01 | 2022-01-15 |
| 5 | 2022-03-01 | 2022-06-30 |
| 6 | 2021-12-01 | 2022-05-31 |
| 7 | 2022-01-01 | 2023-01-01 |
| 8 | 2022-02-01 | 2022-02-15 |
| 9 | 2022-01-01 | 2022-06-30 |
| 10 | 2022-02-01 | 2022-07-31 |

### **SQL Code**

The following SQL code can be used to calculate the subscription period:

```sql
sqlCopy code
SELECT user_id, start_date, end_date, DATEDIFF(end_date, start_date) ASsubscription_period_days FROM subscription_history;

```

### **Result Table (Example of How to Calculate the Feature)**

| user_id | start_date | end_date | subscription_period_days |
| --- | --- | --- | --- |
| 1 | 2022-01-01 | 2022-06-30 | 181 |
| 2 | 2021-10-01 | 2022-12-31 | 457 |
| 3 | 2022-02-15 | 2022-03-15 | 28 |
| 4 | 2022-01-01 | 2022-01-15 | 14 |
| 5 | 2022-03-01 | 2022-06-30 | 121 |
| 6 | 2021-12-01 | 2022-05-31 | 181 |
| 7 | 2022-01-01 | 2023-01-01 | 365 |
| 8 | 2022-02-01 | 2022-02-15 | 14 |
