# SNA - Contacts circle

Contributed by: [@alexfhgit](https://github.com/alexfhgit)<br> 
Inspired by: [@alexfhgit](https://github.com/alexfhgit) projects <br>

**Idea behind**

We communicate with many people around us and build communication bridges. Customer, just as a human, might be proactive, attractive, isolated, which might define his behavior in operator. Note that we need only circle of contacts - so its a distinct numbers, not the total count of communications with them. About naming - usually caller is called 'A number' and recipient is called 'B number', thats why all features look like BNUM.

**Data source**

You will need voice and sms event per subscriber level. All calculations will be based on counting on called_party_number (aka phone number of caller or recipient).

## Count of unique communicated contacts, only competitors
Do the count distinct calculation over different periods of time

**BNUM_CMP_UNIQ_CNT_W1**:	number of unique competitors' contacts, week 1

**BNUM_CMP_UNIQ_CNT_W2**:	The number of unique competitors' contacts, week 2

**BNUM_CMP_UNIQ_CNT_W3**:	The number of unique competitors' contacts, week 3

**BNUM_CMP_UNIQ_CNT_W4**:	the number of unique competitors' contacts, week 4

**BNUM_CMP_UNIQ_CNT_4W**:	the number of unique competitors' contacts, in 4 weeks

**BNUM_CMP_UNIQ_CNT_M1**:	The number of unique competitors' contacts, month 1

**BNUM_CMP_UNIQ_CNT_M2**:	The number of unique competitors' contacts, month 2

**BNUM_CMP_UNIQ_CNT_M3**:	The number of unique competitors' contacts, month 3

**BNUM_CMP_UNIQ_CNT_3M**:	the number of unique competitors' contacts, in 3 months

**BNUM_CMP_UNIQ_CNT_PCT5_4W**:	the number of unique competitors' contacts, in 4 weeks, Persentil 5

**BNUM_CMP_UNIQ_CNT_PCT10_4W**:	The number of unique competitors' contacts, in 4 weeks, Persentil 10

**BNUM_CMP_UNIQ_CNT_PCT25_4W**:	The number of unique competitors' contacts, in 4 weeks, Persentil 25

**BNUM_CMP_UNIQ_CNT_PCT50_4W**:	The number of unique competitors' contacts, in 4 weeks, Persentil 50

**BNUM_CMP_UNIQ_CNT_PCT75_4W**:	the number of unique competitors' contacts, in 4 weeks, Persentil 75

**BNUM_CMP_UNIQ_CNT_PCT90_4W**:	the number of unique competitors' contacts, in 4 weeks, Persentil 90

**BNUM_CMP_UNIQ_CNT_PCT95_4W**:	the number of unique competitors' contacts, in 4 weeks, Persentil 95

**BNUM_CMP_UNIQ_CNT_PART_W1_4W**:	the ratio of the number of unique contacts of competitors, week 1 to the amount of 4 weeks

**BNUM_CMP_UNIQ_CNT_PART_W2_4W**:	the ratio of the number of unique competitors' contacts, week 2 to the amount in 4 weeks

**BNUM_CMP_UNIQ_CNT_PART_W3_4W**:	the ratio of the number of unique contacts of competitors, week 3 to the amount in 4 weeks

**BNUM_CMP_UNIQ_CNT_PART_W4_4W**:	the ratio of the number of unique competitors' contacts, week 4 to the amount of 4 weeks

**BNUM_CMP_UNIQ_CNT_PART_M1_3M**:	the ratio of the number of unique competitors' contacts, month 1 to the amount for 3 months

**BNUM_CMP_UNIQ_CNT_PART_M2_3M**:	the ratio of the number of unique competitors' contacts, month 2 to the amount for 3 months

**BNUM_CMP_UNIQ_CNT_PART_M3_3M**:	The ratio of the number of unique competitors' contacts, month 3 to the amount for 3 months


## Count of unique communicated contacts, all of them
Do the count distinct calculation over different periods of time

**BNUM_UNIQ_CNT_W1**:	number of unique contacts, week 1

**BNUM_UNIQ_CNT_W2**:	number of unique contacts, week 2

**BNUM_UNIQ_CNT_W3**:	number of unique contacts, week 3

**BNUM_UNIQ_CNT_W4**:	number of unique contacts, week 4

**BNUM_UNIQ_CNT_4W**:	the number of unique contacts, in 4 weeks

**BNUM_UNIQ_CNT_M1**:	The number of unique contacts, month 1

**BNUM_UNIQ_CNT_M2**:	The number of unique contacts, month 2

**BNUM_UNIQ_CNT_M3**:	number of unique contacts, month 3

**BNUM_UNIQ_CNT_3M**:	the number of unique contacts, in 3 months

**BNUM_UNIQ_CNT_PCT5_4W**:	the number of unique contacts, in 4 weeks, Persentil 5

**BNUM_UNIQ_CNT_PCT10_4W**:	the number of unique contacts, in 4 weeks, Persentil 10

**BNUM_UNIQ_CNT_PCT25_4W**:	the number of unique contacts, in 4 weeks, Persentil 25

**BNUM_UNIQ_CNT_PCT50_4W**:	the number of unique contacts, in 4 weeks, Persentil 50

**BNUM_UNIQ_CNT_PCT75_4W**:	The number of unique contacts, in 4 weeks, Persentil 75

**BNUM_UNIQ_CNT_PCT90_4W**:	the number of unique contacts, in 4 weeks, Persentil 90

**BNUM_UNIQ_CNT_PCT95_4W**:	The number of unique contacts, in 4 weeks, Persentil 95

**BNUM_UNIQ_CNT_PART_W1_4W**:	The ratio of the number of unique contacts, week 1 to the amount for 4 weeks

**BNUM_UNIQ_CNT_PART_W2_4W**:	The ratio of the number of unique contacts, week 2 to the amount in 4 weeks

**BNUM_UNIQ_CNT_PART_W3_4W**:	The ratio of the number of unique contacts, week 3 to the amount in 4 weeks

**BNUM_UNIQ_CNT_PART_W4_4W**:	The ratio of the number of unique contacts, week 4 to the amount in 4 weeks

**BNUM_UNIQ_CNT_PART_M1_3M**:	the ratio of the number of unique contacts, month 1 to the amount for 3 months

**BNUM_UNIQ_CNT_PART_M2_3M**:	the ratio of the number of unique contacts, month 2 to the amount for 3 months

**BNUM_UNIQ_CNT_PART_M3_3M**:	the ratio of the number of unique contacts, month 3 to the amount for 3 months

