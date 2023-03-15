
# Number of All Active Content Services 

The count of all active content services like VAS (Value-Added Services) and CPA (Caller Paid Applications) refers to the number of these services used by a subscriber. VAS includes services such as ringtones, games, and SMS services, while CPA includes services such as premium SMS and subscription-based services. 
This feature can be used to evaluate customer engagement, understand the usage patterns of these services, and target marketing and promotional efforts accordingly. 

## The idea behind

The number of active services for a subscriber provides insight into the subscriber's usage patterns and preferences. It helps the telecom company to understand which services and features are most popular among their subscribers and to tailor their offerings accordingly.
It allows us to identify potential revenue-generating opportunities, evaluate the level of engagement and predict churn more accurately. Overall the idea is that the more active content services subscribers have, the more engaged and advanced customers they are. 

#### Example 

This is Sven. He is a young and savvy-tech user. He is subscribed to a monthly tariff plan with unlimited on-net minutes, he also has additional services such as a Data bundle, ringtones, and games. He can be a perfect customer for a tariff plan upgrade, which will provide him more value for the money and prolong his lifetime value. On the other hand, when Sven uses services less frequently and becomes less active, he may need retention offers. 
 
## Key effects
 
#### 💡 Effect on churn prediction

Subscribers who are using a high number of VAS and CPA features are more engaged with the telecom service and less likely to cancel their subscriptions. This can be used as a metric to identify customers who are at risk of leaving and target retention efforts to them. Additionally, providing good and diverse VAS and CPA services can also help to increase customer satisfaction and reduce the likelihood of churn. 

#### 💡 Effect on usage patterns 

Subscribers with a larger number of active services are more likely to use those services frequently, as they have a greater variety of options available to them. This usually results in higher overall usage, including more calls, text messages, and data usage. On the other hand, subscribers with a smaller number of active services usually use those services less frequently and thus have lower overall usage. Additionally, subscribers with many active services are more likely to bundle services together, like using their phone and internet together.

#### 💡 Effect on LTV prediction

Subscribers with a larger number of active content services are more profitable for the company, as they generate more revenue through their usage of those services. As a result, they are considered to have a higher LTV. On the other hand, subscribers with a smaller number of active services would be less profitable and considered to have a lower LTV. 

## Methodology 👨🏻‍💻

The number of all active content services of a subscriber is represented by single snapshot variable, called "SRV_VAS_CNT". To calculate such metric you need to count only VAS services without deactivation date or when expected deactivation date is tomorrow and beyond.

**Hint**: VAS stands for Value Added Services and usually provide non-direct / non-network related type of services and content, e.g. access to books, newsletter, music, streaming, insurance, melody change. It is common for such services to be activated via short number SMS.



#### Metacode example - TO DO 

Here is the example of SQL code to create SRV_VAS_CNT

```
SELECT
  subscriber_id,
  COUNT(DISTINCT service_name) AS SRV_ALL_CNT
FROM
  subscriber_services
WHERE
  (service_type = 'VAS'
    AND end_date IS NULL
    OR end_date > SNAPSHOT_DATE)
GROUP BY
  subscriber_id

```


## Data source

Some possible data sources include:
- SRVO / SRVP datasets: with all permanent, temporary or one-time services activation statuses
- Billing systems: Telecommunications companies typically have a billing system that tracks subscriber information, including the date of the last monthly fee charge and the date of the next charge.
- CRM systems: Telecommunications companies may also use a customer relationship management (CRM) system that stores subscriber information, including billing information.


#### Datasets

- Subscriber ID
- Service type (e.g. voice, data, SMS)
- Activation date
- Status of the service (e.g. active, inactive, suspended)

#### Minimum required data

- Subscriber ID
- Service type (e.g. voice, data, SMS)
- Activation date
- Deactivation date
- Status of the service (e.g. active, inactive, suspended)

#### Data example

| Subscriber ID | Service name | Activation Date | Status | Deactivation Date | Service type|
|---------------|--------------|-----------------|---------|-------------------|-------------|
| 12345 | Ringtone | 01/01/2022 | Active | NULL | VAS |
| 12345 | Data 4G| 05/01/2022 | Active | 10/03/2022 | CRM |
| 12345 | Cyber protect| 10/01/2022 | Active | 01/02/2022 | VAS |
| 67890 | Voice Bundle 2| 01/01/2022 | Active| NULL | CRM |
| 67890 | Data 5G| 01/01/2022 | Inactive| 01/05/2022 | CRM |



## Additional info

#### Origin 🕵🏻‍♂️

This feature became popular in low ARPU market where operators were trying to generate extra money with third party services. It become common feeling that such services are associated with suspicious, toxic, forced subscriptions by customers.

#### Related articles 📚

If you found articles or pages with behavioral research, case studies, or experiments - feel free to contribute via the personal space panel.

