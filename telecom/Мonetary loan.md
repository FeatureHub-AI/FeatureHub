# Monetary loan

Contributed by: [@ilyaostrovskygit](https://github.com/ilyaostrovskygit)

Inspired by: [@alexfhgit](https://github.com/alexfhgit) projects

**The idea behind**

When a prepaid subscriber reaches a zero balance, the telecom service will be deactivated for use. The user must recharge or take a loan from the operator to reactivate the service. This loan is an additional service that the user must activate.

Users who frequently rely on the loan service may be more likely to churn (for example), as they may be experiencing financial difficulties or dissatisfaction with the service.

**Data source**

The transactional data, which  include information on the user's balance, loan activity, and service activation/deactivation.

## Amount of taken loans per period

The total amount of loans the user has taken over certain period

**ML_SUM_W1:**	The amount of taken loans, week 1

**ML_SUM_W2:** The amount of taken loans, week 2

**ML_SUM_W3:** The amount of taken loans, week 3

**ML_SUM_W4:** The amount of taken loans, week 4

**ML_SUM_12M:** The amount of taken loans, for 12 months

**ML_SUM_3M:** The amount of taken loans, for 3 months

**ML_SUM_6M:** The amount of taken loans, for 6 months

**ML_SUM_M1:** The amount of taken loans, month 1

**ML_SUM_M2:** The amount of taken loans, month 2

**ML_SUM_M3:** The amount of taken loans, month 3

## Loan amount (min, max, average, last)

**ML_SUM_MAX_12M**: The maximal one-time amount of loan taken by user, for 12 months

**ML_SUM_MIN_12M:** The minimal one-time amount of loan taken by user, for 12 months

**ML_SUM_AVG_12M:** The average amount of loans taken by user, for 12 months

**ML_SUM_LAST_12M:** The amount of the last loan taken by user, for 12 months

## Number of day from the last loan

**ML_DAYS_CNT_LAST:** The number of days from the moment of the last taken loan, in 12 months

## Number of times the loan was taken per period

The number of times a user has taken a loan per period

**ML_CNT_W1:**	The number of times a user has taken a loan, week 1

**ML_CNT_W2:**	The number of times a user has taken a loan, week 2

**ML_CNT_W3:**	The number of times a user has taken a loan, week 3

**ML_CNT_W4:**	The number of times a user has taken a loan, week 4

**ML_CNT_4W:**	The number of times a user has taken a loan, in 4 weeks

**ML_CNT_M1:**	The number of times a user has taken a loan, month 1

**ML_CNT_M2:**	The number of times a user has taken a loan, month 2

**ML_CNT_M3:**	The number of times a user has taken a loan, month 3

**ML_CNT_3M:**	The number of times a user has taken a loan, in 3 months

**ML_CNT_6M:**	The number of times a user has taken a loan, in 6 months

**ML_CNT_12M:** The number of times a user has taken a loan, in 12 months

## Automatic loan service

A user can have a service with an automatic loan that is given automatically in the event the user's balance reaches zero. User can activate and deactivate this service. The service usually has different amounts for automatic loan

**ML_AUTO_AMOUNT:** The amount of automatic loan

**ML_AUTO_DAYS_CNT_ACTIVE: T**he number of days from the moment of the last activation of automatic loan service

**ML_AUTO_DAYS_CNT_DISABLE:**	The number of days from the moment of the last deactivation of automatic loan service

**ML_AUTO_DAYS_CNT_LAST: T**he number of days from the moment of the last automatic loan given to a user, in 12 months

## Repayment period

The number of days between taking out a loan and its actual repayment

**ML_DUE_DUR_AVG_12M:** The average repayment period of all taken loans, in 12 months

**ML_DUE_DUR_LAST_12M:** The  repayment period of last loan, in 12 months

**ML_DUE_DUR_MAX_12M:** The maximal repayment period of all taken loans, in 12 months

**ML_DUE_DUR_MIN_12M:** The minimal repayment period of all taken loans, in 12 months
