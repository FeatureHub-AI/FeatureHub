# Device change

Contributed by: [@irenegrv](https://github.com/IreneGrv) Origin: [@alexfhgit](https://github.com/alexfhgit) projects

**Idea behind**

IMEI change is a meaningful event that does not normally happens every day. That is why we expect that the majority of subscribers will have from 0 to 1 changes over a given period of time. This sample will include subscribers who did not change their IMEI, since they use their device and are happy with them, and those who changed their device once probably due to an upgrade. We, though, are looking for those whose behavior is somehow different. Such subscribers will change their IMEI way more frequently because they probably have more than one SIM for different purposes. And this will be the audience, we are interested to explore and to run additional analyses.****

**Methodology** 

The number of IMEI changes for a subscriber is represented by single snapshot variable, called "IMEI_CNG_CNT_PERIOD". You need to calculate all appearences of IMEI change in IMEI_log or DMS dataset.

**Hint**: You will need properly calculated DMS dataset, so it only store info of IMEI change, and not IMEI usage per each network event. In case subscriber did not change IMEI you will receive NULL value, we need to manualy change it to 0.

**Metacode example**

Here is the example of SQL code to create feature

```sql
SELECT subscriber_id,
       coalesce(count(case when date_diff(event_time, snapshot_date, day) between -7 and -1 then 1 else null end), 0) AS IMEI_CNG_CNT_W1
FROM subscriber_imei_change_log
GROUP BY 1;

```

**Data source**

- Subscriber IMEI change log: This data source should contain information about each time a subscriber's IMEI changes, including the subscriber's ID and the date of the IMEI change.

Minimum required data:

- Subscriber ID
- Subscriber IMEI change log dataset

## The number of IMEI change over periods

The number of IMEI change refers to the count of how many times a subscriber has changed their device over a given period

**IMEI_CNG_CNT_W1**: The number of shifts IMEI, week 1

**IMEI_CNG_CNT_W2**: The number of shifts IMEI, week 2

**IMEI_CNG_CNT_W3**: The number of shifts IMEI, week 3

**IMEI_CNG_CNT_W4**: The number of shifts IMEI, week 4

**IMEI_CNG_CNT_4W**: The number of IMEI shifts, for 4 weeks

**IMEI_CNG_CNT_1M**: The number of IMEI shifts, for 1 month
**IMEI_CNG_CNT_3M**: The number of IMEI shifts,  for 3 month

**IMEI_CNG_CNT_12M**: The number of IMEI shifts, for 12 month
**IMEI_CNG_CNT_ALL**: The number of IMEI shifts, for all period of time

#
