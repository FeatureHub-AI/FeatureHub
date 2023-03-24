# Active services

**Idea behind**

The number of all active services refers to the total number of services that the subscriber is currently using or subscribed to. This includes phone services, Internet services, etc., and technical services as well. This feature can be used as a way to understand the level of engagement of a subscriber with a telecom company, and to identify potential upselling or cross-selling opportunities. Overall the idea is that the more active services subscribers have, the more engaged, reliant and advanced customers they are.

**Methodology** 

The number of all active services of a subscriber is represented by single snapshot variable, called "SRV_ALL_CNT". To calculate such metric you need to count all services without deactivation date or when expected deactivation date is tomorrow and beyond.

**Hint**: Potentially some services are included by default in price plan. And their deactivation date may vary from NULL, Undefined or fake like 2099 year.

**Metacode example**

Here is the example of SQL code to create SRV_ALL_CNT

```sql
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

**Data source**

Some possible data sources include:

- SRVO / SRVP datasets: with all permanent, temporary or one-time services activation statuses
- Billing systems: Telecommunications companies typically have a billing system that tracks subscriber information, including the date of the last monthly fee charge and the date of the next charge.
- CRM systems: Telecommunications companies may also use a customer relationship management (CRM) system that stores subscriber information, including billing information.

**Datasets**

- Subscriber ID
- Service type (e.g. voice, data, SMS)
- Activation date
- Status of the service (e.g. active, inactive, suspended)

**Minimum required data**

- Subscriber ID
- Service type (e.g. voice, data, SMS)
- Activation date
- Deactivation date
- Status of the service (e.g. active, inactive, suspended)

## Active services feature

- **SRV_ALL_CNT:**	The number of active services (all)
