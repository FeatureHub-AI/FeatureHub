
# Number of Days Since the Last SIM Change
 
The number of days since the last SIM change feature refers to the number of days elapsed since a customer's SIM card was last changed and shows how long a customer has been using the current SIM card. 

## The idea behind

SIM card change is rather an extraordinary event and we expect that a majority of subscribers will have a value equal to their lifetime. For those with a lower value, SIM card change can happen for several reasons, such as upgrades to a new phone, when subscribers may need to switch to a new compatible SIM card. This case is rather a positive experience. However, it can also happen due to fraud, damaged, or lost SIM card, which is a rather negative experience. If a subscriber's SIM card is damaged, lost, or stolen, he will need to replace it in order to continue using his phone. It can lead to frustration and an increased chance of switching to a competitor. 

#### Example 

This is John. He is a loyal, engaged customer. However, five days ago his SIM was stolen. He replaced his SIM card two days ago, but due to a negative experience with his current operator, he is considering switching to another mobile provider.  

## Methodology 👨🏻‍💻

The number of days since the last SIM change is represented by single snapshot variable, called "LT_SIM_CURR". You need to find the difference between the current date and the date of the most recent SIM change. 

**Hint**: In case there were no changes of SIM, this feature will be equal to the subscriber's lifetime or NULL value. In case of NULL value dont forget to properly imputed before using in AI ML algorithm.


#### Metacode example 

Here is the example of SQL code to create feature

```
SELECT subscriber_id, 
       max(date_diff(sim_change_date, snapshot_date, day)) AS LT_SIM_CURR
FROM sim_change_log
GROUP BY 1;
```

## Data source

- Subscriber SIM change log: This data source should contain information about each time a subscriber's SIM changes, including the subscriber's ID and the date of the SIM change.
- CRM or Salesforce: This might be and issue or support ticket regarding SIM change request.

#### Minimum required data

- Subscriber ID
- Subscriber SIM change log dataset

#### Data example
Subscriber SIM changes log dataset:

| Subscriber ID | SIM Change Date |
| ------------ | ---------------- |
| 12345        | 2020-01-01      |
| 12345        | 2020-02-01      |
| 67890        | 2020-03-01      |
| 67890        | 2020-04-01      |



## Additional info

#### Origin 🕵🏻‍♂️

With application of e-sim this kind of feature become even more exciting and potential for different case studies.

#### Related articles 📚

If you found articles or pages with behavioral research, case studies, or experiments - feel free to contribute via the personal space panel.



