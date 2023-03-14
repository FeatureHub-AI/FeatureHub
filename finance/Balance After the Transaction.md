# New Balance After the Transaction

Assigned to: Irina G
Created by: Irina G
Industry: Finance
Priority: Low
Status: In work

# **New Balance After the Transaction**

The new balance after the transaction is a metric that provides information on the state of a customer's balance after a transaction has been made. 

## **The Idea Behind**

The purpose of this feature is to provide information on the state of a customer's balance after a transaction has been made. This information can be used to detect any suspicious or fraudulent behavior, such as unauthorized transactions or balance manipulations. By tracking the new balance after a transaction, financial institutions can have a better understanding of a customer's financial activity and ensure the security of their account.

## **Methodology**

The feature is calculated by subtracting the transaction amount from the initial balance. The new balance after the transaction represents the updated state of a customer's account after a transaction has taken place.

### **Data Source**

The data source for this feature is the customer transaction data. This data contains information on the customer's account balance, transaction amount, and transaction date. The data is stored in a table named **`customer_transactions`**, with the following columns:

| customer_id | transaction_date | transaction_amount | initial_balance |
| --- | --- | --- | --- |
| 1 | 2020-01-01 | 500 | 1000 |
| 2 | 2020-01-02 | 250 | 1500 |
| 3 | 2020-01-03 | 100 | 2000 |
| ... | ... | ... | ... |

### **SQL Code**

The following SQL code can be used to calculate the new balance after the transaction metric:

```sql
vbnetCopy code
SELECT customer_id, transaction_date, transaction_amount, initial_balance, initial_balance - transaction_amount as new_balance FROMcustomer_transactions;

```

### **Result Table (Example of How to Calculate the Feature)**

The result of the calculation would be a table with the following columns:

| customer_id | transaction_date | transaction_amount | initial_balance | new_balance |
| --- | --- | --- | --- | --- |
| 1 | 2020-01-01 | 500 | 1000 | 500 |
| 2 | 2020-01-02 | 250 | 1500 | 1250 |
| 3 | 2020-01-03 | 100 | 2000 | 1900 |
| ... | ... | ... | ... | ... |

## **Feature Performance**

![Screenshot 2023-02-13 at 13.54.56.png](New%20Balance%20After%20the%20Transaction%20798e3540e5bf410487be58419b5651bd/Screenshot_2023-02-13_at_13.54.56.png)

## **Additional Info**

The information for this feature was sourced from the article "Machine learning techniques for fraud detection in e-banking systems" by J. Bajaj, J. Kaur, and R. Kaur (**[https://philarchive.org/archive/MEGFFT-2](https://philarchive.org/archive/MEGFFT-2)**).
