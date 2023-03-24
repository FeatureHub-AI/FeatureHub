# Voice quality - Recall Rate

Contributed by: [@alexfhgit](https://github.com/alexfhgit)<br> 
Inspired by: [@alexfhgit](https://github.com/alexfhgit) projects <br>

**Idea behind**

Many things happen on background / engineering level while operator provides services to their customers. Some of them can be directly felt by a customer, like an unexpected end of call. But also there can be situations when customer need few extra seconds before his call reaches a called party number. Base station and routing systems might generate events that called recalls.

**Data source**

Operator need probing or reject system where the technical logs of all network events are stores. You will need a mapping / dictionary / dimension table that explains status codes on why call was successful or not. After Drop Call event, the next popular thing is Recall event.

## Number of recalls per period
Count of recall events for a specific period of time

<!--Is it per user  ?-->

**RCR_ALL_CNT_W1**:	number of recall, week 1

**RCR_ALL_CNT_W2**:	number of recall, week 2

**RCR_ALL_CNT_W3**:	number of recall, week 3

**RCR_ALL_CNT_W4**:	number of recall, week 4

**RCR_ALL_CNT_4W**:	number of recall, in 4 weeks

**RCR_ALL_CNT_M1**:	number of recall, month 1

**RCR_ALL_CNT_M2**:	number of recall, month 2

**RCR_ALL_CNT_M3**:	number of recall, month 3

**RCR_ALL_CNT_3M**:	number of recall, in 3 months


## Number of recalls per percentile per period
<!-- Need description hereWHAT is PCT? percentile from what? Not clear. Neeed to gove a name here -->

**RCR_ALL_CNT_PCT5_4W**:	the amount of recall, in 4 weeks, Percentile 5

**RCR_ALL_CNT_PCT10_4W**:	the amount of recall, in 4 weeks, Percentile 10

**RCR_ALL_CNT_PCT25_4W**:	the amount of recall, in 4 weeks, Percentile 25

**RCR_ALL_CNT_PCT50_4W**:	the amount of recall, in 4 weeks, Percentile 50

**RCR_ALL_CNT_PCT75_4W**:	The amount of recall, in 4 weeks, Percentile 75

**RCR_ALL_CNT_PCT90_4W**:	the amount of recall, in 4 weeks, Percentile 90

**RCR_ALL_CNT_PCT95_4W**:	The amount of recall, in 4 weeks, Percentile 95


## Part or ratio? or what?
<!-- Need description here-->

**RCR_ALL_CNT_PART_W1_4W**:	ratio the amount of recall, week 1 to the amount in 4 weeks

**RCR_ALL_CNT_PART_W2_4W**:	ratio the amount of recall, week 2 to the amount in 4 weeks

**RCR_ALL_CNT_PART_W3_4W**:	ratio the amount of recall, week 3 to the amount in 4 weeks

**RCR_ALL_CNT_PART_W4_4W**:	ratio the amount of recall, week 4 to the amount in 4 weeks

**RCR_ALL_CNT_PART_M1_3M**:	ratio the amount of recall, month 1 to the amount for 3 months

**RCR_ALL_CNT_PART_M2_3M**:	ratio the amount of recall, month 2 to the amount for 3 months

**RCR_ALL_CNT_PART_M3_3M**:	ratio the amount of recall, month 3 to the amount in 3 months
