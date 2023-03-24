
# Active Days

**Idea behind**

Active Days feature is a key indicator of a subscriber's level of engagement and retention in a subscription-based business. By examining the combination of active days and their patterns, we can help the model better understand and encode the behavior of the subscriber. Specifically, we analyze the maximum consecutive days of activity and non-activity to gain insight into the subscriber's service usage patterns.

Moreover, by examining the active days feature in relation to the subscriber's lifetime, we can estimate their level of activity throughout their subscription, including their frequency of service usage and patterns. 

**Data source**

You need any daily snapshot dataset per each subscriber.

LA or ASPN - the Last Activity or Antisuspension snapshot tables, with a daily aggregated data of a whole customer base.

**Minimum required data**

- Subscriber ID: A unique identifier for each subscriber.
- Activity snapshot date: The date of calculating customer status either active or silent
- Activity status: A binary column where 1 = active and 0 = not active or silent.

## Number of active days over a period

- **ACT_CNT_W1:**	The number of active days, week 1
- **ACT_CNT_W2:**	The number of active days, week 2
- **ACT_CNT_W3:**	The number of active days, week 3
- **ACT_CNT_W4:**	The number of active days, week 4
- **ACT_CNT_4W:**	The number of active days, in 4 weeks
- **ACT_CNT_3M:**	The number of active days, in 3 months

## Combination of active days
To calculate the combination of active days for one week per subscriber, you will need to create a 7-day binary vector for each subscriber where each element represents the active or not active status for that day. For every day active customer you will see '1111111', for customer that was active 5 days in a row but last 2 days was silent you will see '1111100'

**Hint**: So we have array of 7 days, starting from left to right. The left or first element represents activity status for the most latest day of a period, while right or last element represents activity status for the most recent day of a chosen period. We recommend to utilize your own methodology of activity and test different ways. For example it is common to count customer active if he either generates ougoing calls OR outgoing SMS OR spend over 20 MB of data. It is much easier to pre-aggregate daily activity data, because SQL / python code might look too complex. We recommend starting with at least weekly activity patterns because they include all week days at least once.

- **ACT_COMB_W1:**	Combination of Activity Days, week 1

## **Maximum of consecutive days of activity**

- **ACT_MAXSEQ_4W:**	Maximum consecutive days of activity, in 4 weeks
- **ACT_MAXSEQ_M1:**	Maximum  consecutive days of activity, month 1
- **ACT_MAXSEQ_M2:**	Maximum  consecutive days of activity, month 2
- **ACT_MAXSEQ_M3:**	Maximum  consecutive days of activity, month 3
- **ACT_MAXSEQ_3M:**	Maximum  consecutive days of activity, in 3 months

## Ratio of number of active days to the lifetime

- **LT_ACT_CNT_PART:**	The ratio of the number of days of activity to the life date of the subscriber

## Maximum consecutive non-active days

- **NACT_MAXSEQ_4W:**	Maximum  consecutive days of non-active, in 4 weeks
- **NACT_MAXSEQ_M1:**	Maximum  consecutive days of non-active, month 1
- **NACT_MAXSEQ_M2:**	Maximum  consecutive days of non-active, month 2
- **NACT_MAXSEQ_M3:**	Maximum  consecutive days of non-active, month 3
- **NACT_MAXSEQ_3M:**	Maximum  consecutive days of non-active, in 3 months
