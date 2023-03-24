 
<!--
NAME: Active Days Combination
TAGS
Industries: Telecom
Tasks: Churn prediction, LTV
Sources: FeatureHub.AI
Entities: Active Days
 -->
 
# Active Days Combination

The combination of active days over a period of time is a way of encoding the customers activity, which includes usage of any type of services provided by operator.

## The idea behind

The combination of active days over a period provides insight into the usage patterns and habits of customers. During the week subscriber can have '1111111' or '1101010' combination. In the first case we see that subscriber uses services every day, which has a positive effect on his activity, no silent days and, as a result, reduces his probability to churn. However, in the second case we see that subscriber is less active and uses services less frequently which can be a sign of deliberately reduced activity which increases his chances to cancel subscription.

#### Example 

This is Julia. She used to use her phone every day. But recently she is not satisfied with her mobile provider so she reduced her usage to a minimum, only to make calls to contacts who uses the same mobile network.  


## Methodology 👨🏻‍💻

The combination of active days over a period is represented by a number of variables, called "ACT_COMB_PERIOD". 
To calculate the combination of active days for one week per subscriber, you will need to create a 7-day binary vector for each subscriber where each element represents the active or not active status for that day. For every day active customer you will see '1111111', for customer that was active 5 days in a row but last 2 days was silent you will see '1111100'

**Hint**: So we have array of 7 days, starting from left to right. The left or first element represents activity status for the most latest day of a period, while right or last element represents activity status for the most recent day of a chosen period. We recommend to utilize your own methodology of activity and test different ways. For example it is common to count customer active if he either generates ougoing calls OR outgoing SMS OR spend over 20 MB of data. It is much easier to pre-aggregate daily activity data, because SQL / python code might look too complex. We recommend starting with at least weekly activity patterns because they include all week days at least once.


#### Metacode example

Here is the example of SQL code to create ACT_COMB_W1.

```
-- It is highly dependent on your available datasets. We can help you generate code if you contact us and share your data schema. 
-- If you know universal template, please contribute.

```

#### Variables

We used the following variables

```sql
# For 1 week
ACT_COMB_W1

# For 2 week - this refers to exact 2nd week prior to snapshot date, e.g. event_date between current_date - 15 and current_date - 8
ACT_COMB_W2

# For 3 week
ACT_COMB_W3

# For 4 week
ACT_COMB_W4
```

## Data source

You need any daily snapshot dataset per each subscriber.

#### Datasets

LA or ASPN - the Last Activity or Antisuspension snapshot tables, with a daily aggregated data of a whole customer base.


#### Minimum required data

- Subscriber ID: A unique identifier for each subscriber.
- Activity snapshot date: The date of calculating customer status either active or silent
- Activity status: A binary column where 1 = active and 0 = not active or silent.

#### Data example
| subscriber_id | activity_date       | active |
|----------------|---------------------|--------|
| 123456         | 2021-01-01           |  1      |
| 123456         | 2021-01-02          | 0      |
| 123456         | 2021-01-03           | 0      |
| 123456         | 2021-01-04           |  1      |
| 123456         | 2021-01-05           |  1      |


## Additional info

#### Origin 🕵🏻‍♂️

This type of features appeared after neural network hype and sequence analysis. This way of transformation proved its performance in deep learning algoriths and found its place in classic supervised machine learning.

#### Related articles 📚
