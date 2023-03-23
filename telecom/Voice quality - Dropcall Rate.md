# Voice quality - Dropcall Rate

Contributed by: [@alexfhgit](https://github.com/alexfhgit)<br> 
Inspired by: [@alexfhgit](https://github.com/alexfhgit) projects <br>

**Idea behind**

Many things happen on background / engineering level while operator provides services to their customers. Some of them can be directly felt by a customer, like an unexpected end of call. We want to know how frequently customer affected by this events.

**Data source**

Operator need probing or reject system where he stores technical logs of all network events. You will need a mapping / dictionary / dimension table that explains status codes on why call was successful or not. Here we need Drop call status code and detailisation on what is the reason behind it. To be honest it can depend on your architecture, it might be something like 'Low or insufficient balance', 'System failure', 'Attempt failure', etc.

## Count of events occured, total
Count events for a specific period of time

**DCR_ALL_CNT_W1**:	Number Dropcall, week 1

**DCR_ALL_CNT_W2**:	number Dropcall, week 2

**DCR_ALL_CNT_W3**:	Number Dropcall, week 3

**DCR_ALL_CNT_W4**:	number Dropcall, week 4

**DCR_ALL_CNT_4W**:	amount of dropcall, in 4 weeks

**DCR_ALL_CNT_M1**:	number Dropcall, month 1

**DCR_ALL_CNT_M2**:	number Dropcall, month 2

**DCR_ALL_CNT_M3**:	amount of dropcall, month 3

**DCR_ALL_CNT_3M**:	amount of dropcall, in 3 months

**DCR_ALL_CNT_PCT5_4W**:	amount of dropcall, in 4 weeks, Persentil 5

**DCR_ALL_CNT_PCT10_4W**:	amount of dropcall, in 4 weeks, Persentil 10

**DCR_ALL_CNT_PCT25_4W**:	The amount of dropcall, in 4 weeks, Persentil 25

**DCR_ALL_CNT_PCT50_4W**:	amount of dropcall, in 4 weeks, Persentil 50

**DCR_ALL_CNT_PCT75_4W**:	The amount of dropcall, in 4 weeks, Persentil 75

**DCR_ALL_CNT_PCT90_4W**:	the amount of dropcall, in 4 weeks, Persentil 90

**DCR_ALL_CNT_PCT95_4W**:	The amount of dropcall, in 4 weeks, Persentil 95

**DCR_ALL_CNT_PART_W1_4W**:	ratio the amount of dropcall, week 1 to the amount in 4 weeks

**DCR_ALL_CNT_PART_W2_4W**:	ratio the amount of dropcall, week 2 to the amount in 4 weeks

**DCR_ALL_CNT_PART_W3_4W**:	ratio the amount of dropcall, week 3 to the amount in 4 weeks

**DCR_ALL_CNT_PART_W4_4W**:	ratio the amount of dropcall, week 4 to the amount in 4 weeks

**DCR_ALL_CNT_PART_M1_3M**:	ratio the amount of dropcall, month 1 to the amount for 3 months

**DCR_ALL_CNT_PART_M2_3M**:	ratio the amount of dropcall, month 2 to the amount for 3 months

**DCR_ALL_CNT_PART_M3_3M**:	ratio the amount of dropcall, month 3 to the amount for 3 months

## Count of events occured, due to low or insufficient balance
Count events for a specific period of time

**DCR_LOW_CNT_W1**:	The amount of dropcall is insufficient balance, week 1

**DCR_LOW_CNT_W2**:	The amount of dropcall is insufficient balance, week 2

**DCR_LOW_CNT_W3**:	The amount of dropcall is insufficient balance, week 3

**DCR_LOW_CNT_W4**:	The amount of dropcall is insufficient balance, week 4

**DCR_LOW_CNT_4W**:	The amount of dropcall is insufficient balance, in 4 weeks

**DCR_LOW_CNT_M1**:	The amount of dropcall is insufficient balance, month 1

**DCR_LOW_CNT_M2**:	The amount of dropcall is insufficient balance, month 2

**DCR_LOW_CNT_M3**:	The amount of dropcall is insufficient balance, month 3

**DCR_LOW_CNT_3M**:	The amount of dropcall is insufficient balance, in 3 months

**DCR_LOW_CNT_PCT5_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 5

**DCR_LOW_CNT_PCT10_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 10

**DCR_LOW_CNT_PCT25_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 25

**DCR_LOW_CNT_PCT50_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 50

**DCR_LOW_CNT_PCT75_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 75

**DCR_LOW_CNT_PCT90_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 90

**DCR_LOW_CNT_PCT95_4W**:	The amount of dropcall is insufficient balance, in 4 weeks, Persentil 95

**DCR_LOW_CNT_PART_W1_4W**:	ratio amount of dropcall insufficient balance, week 1 to the amount in 4 weeks

**DCR_LOW_CNT_PART_W2_4W**:	ratio amount of dropcall insufficient balance, week 2 to the amount in 4 weeks

**DCR_LOW_CNT_PART_W3_4W**:	ratio amount of dropcall insufficient balance, week 3 to the amount in 4 weeks

**DCR_LOW_CNT_PART_W4_4W**:	ratio amount of dropcall insufficient balance, week 4 to the amount in 4 weeks

**DCR_LOW_CNT_PART_M1_3M**:	ratio amount of dropcall insufficient balance, month 1 to the amount for 3 months

**DCR_LOW_CNT_PART_M2_3M**:	ratio quantity dropcall insufficient balance, month 2 to the amount for 3 months

**DCR_LOW_CNT_PART_M3_3M**:	ratio amount of dropcall insufficient balance, month 3 to the amount in 3 months

## Count of events occured, due to system or routing or base station (aka BS) error
Count events for a specific period of time

**DCR_SYS_CNT_W1**:	amount of dropcall error BS, week 1

**DCR_SYS_CNT_W2**:	Number of DropCall error BS, week 2

**DCR_SYS_CNT_W3**:	Number Dropcall error BS, week 3

**DCR_SYS_CNT_W4**:	amount of dropcall error BS, week 4

**DCR_SYS_CNT_4W**:	The amount of DropCall error BS, in 4 weeks

**DCR_SYS_CNT_M1**:	quantity DropCall error BS, month 1

**DCR_SYS_CNT_M2**:	Number Dropcall error BS, month 2

**DCR_SYS_CNT_M3**:	quantity DropCall error BS, month 3

**DCR_SYS_CNT_3M**:	The amount of DropCall error BS, in 3 months

**DCR_SYS_CNT_PCT5_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 5

**DCR_SYS_CNT_PCT10_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 10

**DCR_SYS_CNT_PCT25_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 25

**DCR_SYS_CNT_PCT50_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 50

**DCR_SYS_CNT_PCT75_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 75

**DCR_SYS_CNT_PCT90_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 90

**DCR_SYS_CNT_PCT95_4W**:	The amount of DropCall error BS, in 4 weeks, Persentil 95

**DCR_SYS_CNT_PART_W1_4W**:	ratio quantity dropcall error BS, week 1 to the amount in 4 weeks

**DCR_SYS_CNT_PART_W2_4W**:	ratio quantity dropcall error BS, week 2 to the amount in 4 weeks

**DCR_SYS_CNT_PART_W3_4W**:	ratio number of dropcall error BS, week 3 to the amount in 4 weeks

**DCR_SYS_CNT_PART_W4_4W**:	ratio number of dropcall error BS, week 4 to the amount in 4 weeks

**DCR_SYS_CNT_PART_M1_3M**:	ratio quantity dropcall error BS, month 1 to the amount for 3 months

**DCR_SYS_CNT_PART_M2_3M**:	ratio quantity dropcall error BS, month 2 to the amount for 3 months

**DCR_SYS_CNT_PART_M3_3M**:	ratio quantity dropcall error BS, month 3 to the amount for 3 months

## Count of events occured, due to unsuccessfull commutation or routing attempt
Count events for a specific period of time

**DCR_ATMP_CNT_W1**:	The number of dropcall attempts to connect, week 1

**DCR_ATMP_CNT_W2**:	The number of dropcall attempts to connect, week 2

**DCR_ATMP_CNT_W3**:	number of dropcall attempts to connect, week 3

**DCR_ATMP_CNT_W4**:	number of dropcall attempts to connect, week 4

**DCR_ATMP_CNT_4W**:	The number of dropcall attempts to connect, in 4 weeks

**DCR_ATMP_CNT_M1**:	The number of dropcall attempts to connect, month 1

**DCR_ATMP_CNT_M2**:	The number of dropcall attempts to connect, month 2

**DCR_ATMP_CNT_M3**:	The number of dropcall attempts to connect, month 3

**DCR_ATMP_CNT_3M**:	the number of dropcall attempts to connect, in 3 months

**DCR_ATMP_CNT_PCT5_4W**:	The number of dropcall attempts to connect, in 4 weeks, Persentil 5

**DCR_ATMP_CNT_PCT10_4W**:	The number of DropCall attempts to connect, in 4 weeks, Persentil 10

**DCR_ATMP_CNT_PCT25_4W**:	The number of dropcall attempts to connect, in 4 weeks, Persentil 25

**DCR_ATMP_CNT_PCT50_4W**:	The number of dropcall attempts to connect, in 4 weeks, Persentil 50

**DCR_ATMP_CNT_PCT75_4W**:	The number of DropCall attempts to connect, in 4 weeks, Persentil 75

**DCR_ATMP_CNT_PCT90_4W**:	The number of dropcall attempts to connect, in 4 weeks, Persentil 90

**DCR_ATMP_CNT_PCT95_4W**:	The number of dropcall attempts to connect, in 4 weeks, Persentil 95

**DCR_ATMP_CNT_PART_W1_4W**:	ratio the number of dropcall attempts to connect, week 1 to the amount in 4 weeks

**DCR_ATMP_CNT_PART_W2_4W**:	ratio the number of dropcall attempts to connect, week 2 to the amount in 4 weeks

**DCR_ATMP_CNT_PART_W3_4W**:	ratio the number of dropcall attempts to connect, week 3 to the amount in 4 weeks

**DCR_ATMP_CNT_PART_W4_4W**:	ratio the number of dropcall attempts to connect, week 4 to the sum in 4 weeks

**DCR_ATMP_CNT_PART_M1_3M**:	ratio the number of dropcall attempts to connect, month 1 to the amount in 3 months

**DCR_ATMP_CNT_PART_M2_3M**:	ratio the number of dropcall attempts to connect, month 2 to the amount in 3 months

**DCR_ATMP_CNT_PART_M3_3M**:	ratio the number of dropcall attempts to connect, month 3 to the amount in 3 months

## Count of events occured, due to unexpected end of call that was not initiated by a called or calling party number
Count events for a specific period of time

**DCR_END_CNT_W1**:	amount of dropcall rupture of the connection, week 1

**DCR_END_CNT_W2**:	amount of dropcall rupture of the connection, week 2

**DCR_END_CNT_W3**:	amount of dropcall rupture of the connection, week 3

**DCR_END_CNT_W4**:	amount of dropcall rupture of the connection, week 4

**DCR_END_CNT_4W**:	amount of dropcall rupture of the connection, in 4 weeks

**DCR_END_CNT_M1**:	amount of dropcall rupture of the connection, month 1

**DCR_END_CNT_M2**:	amount of dropcall rupture of the connection, month 2

**DCR_END_CNT_M3**:	amount of dropcall rupture of the connection, month 3

**DCR_END_CNT_3M**:	amount of dropcall rupture, in 3 months

**DCR_END_CNT_PCT5_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 5

**DCR_END_CNT_PCT10_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 10

**DCR_END_CNT_PCT25_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 25

**DCR_END_CNT_PCT50_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 50

**DCR_END_CNT_PCT75_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 75

**DCR_END_CNT_PCT90_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 90

**DCR_END_CNT_PCT95_4W**:	The amount of dropcall rupture of the connection, in 4 weeks, Persentil 95

**DCR_END_CNT_PART_W1_4W**:	ratio quantity dropcall rp.

**DCR_END_CNT_PART_W2_4W**:	ratio quantity dropcall rupture of the connection, week 2 to the sum in 4 weeks

**DCR_END_CNT_PART_W3_4W**:	ratio quantity dropcall rp.

**DCR_END_CNT_PART_W4_4W**:	ratio quantity dropcall rp.

**DCR_END_CNT_PART_M1_3M**:	ratio quantity dropcall rupture of the connection, month 1 to the amount in 3 months

**DCR_END_CNT_PART_M2_3M**:	ratio quantity dropcall rupture of the connection, month 2 to the sum in 3 months

**DCR_END_CNT_PART_M3_3M**:	ratio quantity dropcall rupture of the connection, month 3 to the amount in 3 months

