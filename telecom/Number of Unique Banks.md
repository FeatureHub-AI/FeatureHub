<!--
NAME:  Number of Unique Banks
TAGS
Industries: Telecom
Tasks: Churn prediction, LTV
Sources: FeatureHub.AI
Entities: External Services
 -->
 
 # Number of Unique Banks

The number of unique banks is a metric that represents how many different banks has customer. This feature shows how many notifications subscriber receives from each bank to a phone number, that bounds a customer to the financial institutions. This feature plays a significant role in subscriber churn prediction. 

## The idea behind

Interaction with banks and other financial institutions is an integral part of our everyday life. We call our banks, we use apps, and we get SMS from a bank about our account balance, charges, etc. That's why a sudden absence of SMS from the bank can be used as a signal of customer behavior change. It is highly unlikely that subscriber stops using such essential services as bank services, it rather indicates subscriber uses another phone number to connect them and stay updated. Using SMS from banks as a connection between bank and subscriber provides us insight into how many unique banks communicate with a subscriber on a regular basis and how many stopped communicating with them.

#### Example 

This is Alex, for the last five years he has used Bank A and Bank B and recently decided to change the operator. For better security, he transfers two-factor authentication for the Bank B to another phone number. He will recieve all the notifications to his new phone number. 
In this case, the absence of incoming SMS from bank indicates about second SIM, which probably one day will become a primary since the connection to banking services are an important part of Alex's everyday life.

## Key effects
 
#### 💡 Effect on churn prediction

Incoming SMS from a bank is used as a feature in a machine-learning model to predict customer churn. As mentioned above, in a case subscriber connects essential services such as bank services to another phone number, his likelihood to churn increases significantly. This is also can be considered as a risk that competitor number becomes a primary.  

#### 💡 Effect on LTV prediction

The number of unique SMS from a bank can also have an impact on customer lifetime value. A consistent number of unique SMS from banks indicates that the bank is actively communicating with its customers via SMS, which means that the current SIM card is used by the subscriber as a primary. 

## Methodology 👨🏻‍💻

The unique banks count is represented by a number of variables, called "SMS_BANK_CNTD_PERIOD". 
This feature can be calculated by counting distinct alf-numerical sender names associated with bank category. You would need dimension / dictionary table to identify if sender name can be identified as bank. 

**Hint**: 
You need to adjust dictionary table to always be up to date. As well gathering such information for each country / region you provide service, because banks may vary. In the telecommunication industry patterns appear starting from at least week periods because daily is biased a lot. That's why we recommend using mostly monthly and weekly trends, not daily. In some cases, we will explicitly point to the use of daily data. Anyway, you can try what fits your task the most.

#### Metacode example

Here is he example of SQL code to create SMS_BANK_CNTD_W1

```sql
SELECT MSISDN,
  COUNT(distinct sender) FILTER(
  WHERE
    sender_type = 'bank'
    AND DATE_DIFF(snapshot_date, event_date, day) BETWEEN -7
    AND -1) AS SMS_BANK_CNTD_W1
FROM
  sms_messages
GROUP BY 1
```

#### Variables

We used the following variables

```sql

# sms_bank_cntd_w1

# sms_bank_cntd_w2

# sms_bank_cntd_w3

# sms_bank_cntd_w4

# sms_bank_cntd_4w
```  

## Data source
An example of data source in the telecom industry that could be used to calculate the number of SMS messages sent by the bank would be the SMS gateway logs and dimension table, either combined or stored separately.

#### Datasets
Subscriber ID
SMS messages: the sender's number, and the recipient's number.
Sender information: This would include the sender's name or phone number, which you would use to filter the SMS messages sent by the bank.
Time sent: This would include the date and time the SMS was sent, which you could use to filter messages by a specific time range.
Additional information: This may include information such as the message's unique identifier, the sender's IP address, and the protocol used to send the message.


#### Minimum required data
Subscriber ID - this is your customer id to generate scoring

event_date - this is used to adjust time ranges for aggregation

sender - this is alfa-numerical name of a sender / recepient of SMS

sender_type - this is category, can be calculated by dimension or dictionary table for sender names in your country



#### Data example

| Subscriber ID | event_date    | sender | Sender_type  |
|---------------|-------------|-----------|--------------|
| 12345         | 2023-01-24    | sabadell        | bank      |
| 12345         | 2023-01-24    | 954491726         | personal       |
| 12345         | 2023-01-23    | santander         | bank       |
| 12345         | 2023-01-22    | 9172616382         | personal      |
| 12345         | 2023-01-22    | aliexpress         | e-com      |


## Additional info

#### Origin 🕵🏻‍♂️

Overall usage of this kind of dimension tables to determine sender type appeared when big data become popular, so data scientists started to search for extra information in raw data rather than generic aggregations.

#### Related articles 📚



