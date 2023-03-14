<!--
NAME: Number of All Active Services
TAGS
Industries: Telecom
Tasks: Churn prediction, LTV
Sources: FeatureHub.AI
Entities: Active Services
 -->
 
# Active Services 

The number of all active services refers to the total number of services that the subscriber is currently using or subscribed to. This includes phone services, Internet services, etc., and technical services as well. 
This feature can be used as a way to understand the level of engagement of a subscriber with a telecom company, and to identify potential upselling or cross-selling opportunities.

## The idea behind

The number of active services for a subscriber provides insight into the subscriber's usage patterns and preferences. It helps to evaluate the level of engagement, and to understand which services and features are most popular among subscribers. Overall the idea is that the more active services subscribers have, the more engaged, reliant and advanced customers they are. 

#### Example 

This is Sven. He is an active, advanced user. He is subscribed to a monthly tariff plan with unlimited on-net minutes, he also has additional services such as a Data bundle, roaming, and negative balance. He can be a perfect customer for a tariff plan upgrade, which will provide him more value for the money and prolong his lifetime value. On the other hand, when Sven uses services less frequently and becomes less active, he may need retention offers. 
 
## Key effects
 
#### 💡 Effect on churn prediction

Subscribers with a larger number of active services are more invested in the company and have a stronger sense of loyalty, which is making them less likely to leave. On the other hand, subscribers with a smaller number of active services may be less engaged and more likely to churn. 

#### 💡 Effect on usage patterns 

Subscribers with a larger number of active services are more likely to use those services frequently, as they have a greater variety of options available to them. This usually results in higher overall usage, including more calls, text messages, and data usage. On the other hand, subscribers with a smaller number of active services usually use those services less frequently and thus have lower overall usage. Additionally, subscribers with many active services are more likely to bundle services together, like using their phone and internet together.

#### 💡 Effect on LTV prediction

Subscribers with a larger number of active services are more profitable for the company, as they generate more revenue through their usage of those services. As a result, they are considered to have a higher LTV. On the other hand, subscribers with a smaller number of active services would be less profitable and considered to have a lower LTV. 

## Methodology 👨🏻‍💻

The number of all active services of a subscriber is represented by single snapshot variable, called "SRV_ALL_CNT". To calculate such metric you need to count all services without deactivation date or when expected deactivation date is tomorrow and beyond.

**Hint**: Potentially some services are included by default in price plan. And their deactivation date may vary from NULL, Undefined or fake like 2099 year.


#### Metacode example

Here is the example of SQL code to create SRV_ALL_CNT

```
SELECT
  subscriber_id,
  COUNT(DISTINCT service_name) AS SRV_ALL_CNT
FROM
  subscriber_services
WHERE
  (end_date IS NULL
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

| Subscriber ID | Service name | Activation Date | Status | Deactivation Date |
|---------------|--------------|-----------------|---------|-------------------|
| 12345 | Voice Bundle 1 | 01/01/2022 | Active | NULL |
| 12345 | Data 4G| 05/01/2022 | Active | 10/03/2022 |
| 12345 | SMS Roaming 50| 10/01/2022 | Active | 01/02/2022 |
| 67890 | Voice Bundle 2| 01/01/2022 | Active| NULL |
| 67890 | Data 5G| 01/01/2022 | Inactive| 01/05/2022 |


## Additional info

#### Origin 🕵🏻‍♂️

It is hard to separate services by type, e.g. VAS, voice, price plan, utilities. So the idea was to get atleast some information value from service usage. It was found that even this type of calculation brings model gain.

#### Related articles 📚

If you found articles or pages with behavioral research, case studies, or experiments - feel free to contribute via the personal space panel.


