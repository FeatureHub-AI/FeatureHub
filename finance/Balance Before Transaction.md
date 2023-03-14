

# Initial Balance Before the Transaction

Initial balance before the transaction refers to the balance of a customer prior to any transactions being made. 

## **The idea behind**

The purpose of this feature is to help understand the financial state of the customer before a transaction is made. The amount of the initial balance indicates if the customer is likely to make a transaction in near future, which amount can be expected as a transaction, and whether the transaction will have an impact on their future behavior.

## **Methodology**

To calculate the initial balance before the transaction, we need to access the customer's financial records. This data can be obtained from a variety of sources, including bank statements, transaction records, and financial management software. Once the data is obtained, the initial balance can be calculated by subtracting all transactions made prior to a given transaction from the customer's starting balance.

### **Data source**

The data source used to calculate the initial balance before the transaction is the customer's financial records. This data can be obtained from a variety of sources, including bank statements, transaction records, and financial management software. In this example, we will use a table called **`transactions`** with the following columns:

- **`customer_id`**: The unique identifier for the customer
- **`transaction_date`**: The date of the transaction
- **`transaction_amount`**: The amount of the transaction
- **`starting_balance`**: The customer's starting balance

An example table is shown below:

| customer_id | transaction_date | transaction_amount | starting_balance |
| --- | --- | --- | --- |
| 1 | 2020-01-01 | -100 | 1000 |
| 1 | 2020-01-02 | -200 | 900 |
| 1 | 2020-01-03 | -300 | 700 |
| 2 | 2020-01-01 | -50 | 500 |
| 2 | 2020-01-02 | -100 | 450 |
| 2 | 2020-01-03 | -150 | 300 |
| 3 | 2020-01-01 | -200 | 800 |
| 3 | 2020-01-02 | -100 | 700 |
| 3 | 2020-01-03 | -50 | 650 |
| 4 | 2020-01-01 | -300 | 700 |

### **SQL code**

The SQL code to calculate the initial balance before the transaction is shown below:

```sql

SELECT customer_id, transaction_date, transaction_amount, starting_balance - SUM(transaction_amount) AS initial_balance_before_transaction FROM transactions GROUP BYcustomer_id, transaction_date

```

### **Result table (example of how to calculate the feature)**

The result table for the initial balance before the transaction is shown below:

| customer_id | transaction_date | transaction_amount | initial_balance_before_transaction |
| --- | --- | --- | --- |
| 1 | 2020-01-01 | -100 | 1000 |
| 1 | 2020-01-02 | -200 | 900 |

## **Feature performance**

<img width="1000" alt="Screenshot_2023-02-13_at_13 54 56" src="https://user-images.githubusercontent.com/120475714/225043147-edd2d22b-ff8e-475f-a477-dfaf47b73971.png">


For further information on how to use this feature for predicting customer churn, please refer to the following articles:

[https://philarchive.org/archive/MEGFFT-2](https://philarchive.org/archive/MEGFFT-2)
