# DPI Competitor Website Visits

Contributed by: [@alexfhgit](https://github.com/alexfhgit)<br> 
Inspired by: [@alexfhgit](https://github.com/alexfhgit) projects <br>

**Idea behind**

Showing interest in direct competitor services is a good trigger in many industries. Using URL domain categorization we can identify all session with domains that belong to our competitors.

**Data source**

We need a DPI, aka Deep Packet Inspection system, to be used by operator to identify traffic domains and categorise them as competitors. It would be easier if you have a dimension / dictionary table that identifies each domain and subdomain to categories and subcategories. In this case understanding that its a competitors website. Best practice to include even convergent services, for example if your competitor have separate domains for mobile services and fiber internet provider.


## Count of days of usage
Take all days that have at least 1 session with competitor domains visits

**DPI_SITE_CMP_CNT_W1**:	number of visits to competitors, week 1

**DPI_SITE_CMP_CNT_W2**:	The number of visits to competitors, week 2

**DPI_SITE_CMP_CNT_W3**:	number of visits to competitors, week 3

**DPI_SITE_CMP_CNT_W4**:	The number of visits to competitors, week 4

**DPI_SITE_CMP_CNT_4W**:	The number of visits to competitors' sites, in 4 weeks

**DPI_SITE_CMP_CNT_M1**:	The number of visits to competitors' sites, month 1

**DPI_SITE_CMP_CNT_M2**:	The number of visits to competitors' sites, month 2

**DPI_SITE_CMP_CNT_M3**:	The number of visits to competitors' sites, month 3

**DPI_SITE_CMP_CNT_3M**:	The number of visits to competitors' sites, in 3 months

**DPI_SITE_CMP_CNT_PART_W1_4W**:	ratio the number of visits to competitors' sites, week 1 to the amount in 4 weeks

**DPI_SITE_CMP_CNT_PART_W2_4W**:	ratio the number of visits to competitors, week 2 to the amount in 4 weeks

**DPI_SITE_CMP_CNT_PART_W3_4W**:	ratio the number of visits to competitors' sites, week 3 to the amount in 4 weeks

**DPI_SITE_CMP_CNT_PART_W4_4W**:	ratio the number of visits to competitors' sites, week 4 to the amount in 4 weeks

**DPI_SITE_CMP_CNT_PART_M1_3M**:	ratio the number of visits to competitors' sites, month 1 to the amount for 3 months

**DPI_SITE_CMP_CNT_PART_M2_3M**:	ratio the number of visits to competitors' sites, month 2 to the amount for 3 months

**DPI_SITE_CMP_CNT_PART_M3_3M**:	ratio the number of visits to competitors' sites, month 3 to the amount for 3 months

## Volume consumed

Note that we dont calculate volume on purpose, because just event of visiting a competitor website is a strong indicator itself. But we offer you to try 
and test on your own

