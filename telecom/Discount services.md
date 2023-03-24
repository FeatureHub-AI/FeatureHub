# Discount services

**Idea behind**

Customers often subscribe to a tariff plan due to attractive discounts offered during a promotion or special offer. such as those offered as part of Customer Value Management (CVM) campaigns that may include zeroing monthly fees or providing absolute or relative discounts. 

However, this does not necessarily mean they are willing to continue paying the full price after the offer has expired. Sometimes customers may forget when their discounts expired, leaving them surprised by the new price of their tariff plan. As a result, they may decide to stick to their current plan or change their decision. To better understand this behavior, we want to track how much time has elapsed since their last discount expired as well as to track the time left until the special offer expires and how it impacts their behavior.

**Data source**

Some possible data sources include:

- SRVO / SRVP datasets: with all permanent, temporary or one-time services activation statuses
- Billing systems: Telecommunications companies typically have a billing system that tracks subscriber information, including the date of the last monthly fee charge and the date of the next charge.
- CRM systems: Telecommunications companies may also use a customer relationship management (CRM) system that stores subscriber information, including billing information.

## Features list

**SRV_TPDISCOUNT_DAYS_CNT_LAST:**	The number of days from the date of the last shutdown of the discount on the tariff plan

**SRV_TPDISCOUNT_DAYS_CNT_NEXT:**	The number of days before the future disconnection of the discount of the tariff plan (CVM discount)
