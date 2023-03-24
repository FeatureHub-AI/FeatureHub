
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
