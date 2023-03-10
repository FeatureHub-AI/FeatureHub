
# **Paperless Bill**

The paperless billing feature checks whether a telecom subscriber has opted for paperless billing or not. 

## **The idea behind**

The customers, who opted for a paperless bill, value on-the-go convenience and quick access to their bills. They are more likely progressive subscribers with internet access who also cares about being more time-efficient and keeping their environment organized and less cluttered. So the purpose of this feature is to understand what usage patterns and preferences has this type of subscribers.

## **Methodology**

The feature is calculated by checking the billing preference of the customer. If a customer has opted for paperless billing, then the feature value is set to 1, otherwise, it is set to 0.

### **Data source**

The data for this feature can be obtained from the billing preference data of the telecom customers. The data should have the following columns:

- customer_id: unique identifier for the customer
- paperless_billing: whether the customer has opted for paperless billing or not (0: no, 1: yes)

Here is an example table with 10 rows:

| customer_id | paperless_billing |
| --- | --- |
| 1 | 1 |
| 2 | 0 |
| 3 | 1 |
| 4 | 1 |
| 5 | 0 |
| 6 | 0 |
| 7 | 1 |
| 8 | 0 |
| 9 | 1 |
| 10 | 0 |

### **SQL code**

The following SQL code can be used to assemble the feature:

```sql

SELECT customer_id, paperless_billing AS paperless_billing FROM billing_preferences

```

### **Result table**

The result of the above SQL code will be a table with the following columns:

| customer_id | paperless_billing |
| --- | --- |
| 1 | 1 |
| 2 | 0 |
| 3 | 1 |
| 4 | 1 |
| 5 | 0 |
| 6 | 0 |
| 7 | 1 |
| 8 | 0 |
| 9 | 1 |
| 10 | 0 |

## **Feature performance**

The mutual information score for feature is 0.019194

## **Additional Info**

For further information on how to use this feature for predicting customer churn, please refer to the following articles:

 **[https://towardsdatascience.com/end-to-end-machine-learning-project-telco-customer-churn-90744a8df97d](https://towardsdatascience.com/end-to-end-machine-learning-project-telco-customer-churn-90744a8df97d)** 

[https://www.kaggle.com/datasets/sooryaprakash12/telecom-churn-prediction](https://www.kaggle.com/datasets/sooryaprakash12/telecom-churn-prediction)

[](https://www.notion.so/5dad08f3346743f1b56a43dc0f48e9e1)
