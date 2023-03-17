
# Delta Between Current Balance and Daily Tariff Cost


The delta between the current balance and the daily tariff cost feature refers to the difference between the current balance and the daily tariff cost. This feature is typically used to determine how much money is remaining in an account after the daily tariff cost has been paid. This feature is very useful for providers of services that are charged daily, such as pay-per-use services, or pay-per-day services, or for tracking usage of service throughout the day.

## The idea behind

A low delta between the current balance and the daily tariff cost feature indicates that the current balance is not enough to use a pay-per-day tariff. It means that the account holder needs to add more funds to use a service without interruption. Subscriber with insufficient funds for daily tariff has a higher chance to become inactive and to cancel the subscription. 

#### Example 

This is Meghan. Usually, she has sufficient funds in her account, but lately, she did not activate her PPM and there is not enough balance for the PPD tariff as well. She did not top up her account, her activity decreased and she does not use services anymore as she used to before. 

## Key effects
 
#### 💡 Effect on churn prediction

A high difference between the current balance and the daily tariff cost indicates a strong likelihood of churn, or a customer terminating their service. This could suggest that the customer is not happy with the cost of their service and may be looking for a more affordable option. 

#### 💡 Effect on usage patterns 

Customers with a high delta are more likely to reduce their usage in order to avoid overage charges or to avoid running out of balance. 


#### 💡 Effect on LTV prediction

Customers with a high delta between the current balance and the daily tariff cost are less likely to continue using the service long-term, which would ultimately lower their LTV. Additionally, if these customers are more likely to reduce their usage or switch to a cheaper service, their LTV will also decrease. 

## Methodology 👨🏻‍💻

The delta between the current balance and the daily tariff cost is represented by single snapshot variable, called "BAL_DELTA_PPD". To calculate it you should determine the current balance for each customer, then determine the daily tariff cost for each customer. Then do the logical comparison.


**Hint**: It is also important to note that this calculation is only a snapshot in time, and the delta will change as the customer makes payments, uses the service, and as the next billing cycle approaches, but the model will train on lots of combinations and situations. It will be useful to have dictionary of price plan daily and monthly fees. If price plan does not provide PPD option, your metric will be NULL and request further imputation techniques.

#### Metacode example

Here is the example of SQL code to create BAL_DELTA_PPD

```sql
SELECT
 customer_id,
 balance - ppd AS BAL_DELTA_PPD
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

If you found articles or pages with behavioral research, case studies, or experiments - feel free to contribute via the personal space panel.
