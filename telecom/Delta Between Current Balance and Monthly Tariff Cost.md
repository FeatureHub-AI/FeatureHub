# Delta Between Current Balance and Monthly Tariff Cost


Delta between current balance and monthly tariff cost feature refers to the difference between the current balance on a mobile phone account and the monthly cost of the plan or tariff that the user is subscribed to. This feature allows to see how much subscribers have remaining in their account before the next billing cycle and provides valuable insights into customer behavior and financial performance.

## The idea behind

A low delta between the current balance and the monthly tariff cost means that the customer's account balance is close to or less than the cost of their monthly plan or tariff. The higher is difference, the higher is risk that subscriber will not have a sufficient balance before the next billing. Such customer is at a higher risk of overage charges, if they do not add more funds to their account or upgrade their plan. It can also indicate that the customer may be thinking of switching to another provider, as they are not satisfied with the balance they have to pay every month.


#### Example 

This is Meghan. She is subscribed to a monthly tariff plan which is renewed monthly every 10th. Usually, she tops up her account without delays to use the benefits of her monthly plan. Last month she did not have sufficient funds in her account and her balance was not even close to the cost of her tariff plan, so when her monthly tariff plan expired, she continued to use services with additional charges. Her activity decreased and finally, after two months she decided to switch to another operator. 

## Key effects
 
#### 💡 Effect on churn prediction

When customers have a clear understanding of their account balance and monthly costs, they are more likely to stay with the service, as they are better able to manage their expenses and avoid overage charges.

However, if customers are frequently experiencing low balances or overage charges, they become frustrated with the service and be more likely to switch to a competitor. 

If the difference between the current balance and the monthly tariff cost is high, this may indicate that the customer is overpaying for a service they do not need or use. This may lead to dissatisfaction and ultimately churn as well.

#### 💡 Effect on usage patterns 

This feature helps to identify customers with high usage patterns and target them with appropriate offers. It also helps to identify customers who may be in need of a different plan or service, and target them with appropriate offers or promotions. This allows the company to improve customer service, increase revenue and reduce churn. 


#### 💡 Effect on LTV prediction

When customers have a clear understanding of their account balance and monthly costs, they are more likely to be mindful of their usage and make conscious decisions about their usage patterns. This leads to more efficient use of the service and avoiding overage charges, which in turn leads to a more positive experience with the service and a reduced likelihood of customers canceling their service. Thus, customers with a low delta between the current balance and monthly tariff cost before the next billing, can be expected to have a higher LTV than others.

## Methodology 👨🏻‍💻

The Delta Between Current Balance and Monthly Tariff Cost is represented by single snapshot variable, called "BAL_DELTA_PPM". To calculate it you should determine the current balance for each customer, then determine the monthly tariff cost for each customer. Then find how much balance is lacking to the needed payment. If it is enough, make it equal 0.

**Hint**: It is also important to note that this calculation is only a snapshot in time, and the delta will change as the customer makes payments, uses the service, and as the next billing cycle approaches, but the model will train on lots of combinations and situations. It will be useful to have dictionary of price plan daily and monthly fees. If price plan does not provide PPD option, your metric will be NULL and request further imputation techniques.

#### Metacode example

Here is the example of SQL code to create feature

```sql
SELECT
 customer_id,
 lowest(0, balance - ppm) AS BAL_DELTA_PPM
FROM
 customers_ASPN
```


## Data source

You would need any LA (Last Activity) or ASPN (Antisuspension) datasets inside your datamart to calculate such feature.


#### Datasets
DIM_PRICE_PLAN - dimension or dictionary table with all price plans options
LA or ASPN - your daily snapshot dataset


#### Minimum required data

- MSISDN
- ACTION_DATE - snapshot day
- BALANCE - balance snapshot on a snapshot day
- PRICE_PLAN - id of current price plan
- PPD - price of PPD option of current price plan, NULL if not applicable
- PPM - price of PPM option of current price plan, NULL if not applicable

#### Data example


|MSISDN| Action date | Balance | PPD | PPM | PRICE_PLAN |
|------|------------|------------|----|-------|-------|
|1001| 01/01/2022   | $100      | $10 | $30 | Easy go XL |
|1001| 01/02/2022 | $120 | $15 | $30 | Easy go XL |
|1001| 01/03/2022 | $150 | $20 | $30 | Easy go XL |


## Additional info

#### Origin 🕵🏻‍♂️

Some markets started providing PRP (prepaid) services with many options, where monthly payment become not obligatory. Introduction of pay per day or pay per use option changed customer behavior and data scientists needed another metric to describe their patterns. This type of features is very common in low ARPU, Prepaid and CIS markets.

#### Related articles 📚


