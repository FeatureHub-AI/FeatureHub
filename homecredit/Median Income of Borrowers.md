
# **Median Income of Borrowers Grouped by Organization Type**

## **The idea behind**

This feature is to provide the median income level of borrowers based on their organization type, which can be used by lenders to evaluate the creditworthiness of borrowers. Borrowers with higher incomes may be more likely to repay their loans on time, while those with lower incomes may be more at risk of defaulting. This feature can be used to analyze market trends and inform policy decisions related to lending and financial services. 

## **Methodology**

The feature is calculated by grouping the borrowers by their organization type and then finding the median income level of each group.

### **Data source**

The data source for this feature is a table containing information about borrowers, including their income and organization type. The following columns are needed to create this feature:

- borrower_id: unique identifier for each borrower
- income: income level of the borrower
- organization_type: type of organization the borrower belongs to

Example table:

| borrower_id | income | organization_type |
| --- | --- | --- |
| 1 | 50000 | Sole proprietor |
| 2 | 60000 | Corporation |
| 3 | 40000 | Partnership |
| 4 | 55000 | Sole proprietor |
| 5 | 35000 | Partnership |
| 6 | 65000 | Corporation |
| 7 | 45000 | Sole proprietor |
| 8 | 55000 | Corporation |
| 9 | 50000 | Partnership |
| 10 | 60000 | Corporation |

### **Code**

```sql
sqlCopy code
SELECT organization_type, MEDIAN(income) AS median_income_by_org_type FROM borrower_tableGROUP BY organization_type

```

### **Assembling example**

| borrower_id | income | organization_type | median_income_by_org_type |
| --- | --- | --- | --- |
| 1 | 50000 | Sole proprietor | 52500 |
| 2 | 60000 | Corporation | 60000 |
| 3 | 40000 | Partnership | 42500 |
| 4 | 55000 | Sole proprietor | 52500 |
| 5 | 35000 | Partnership | 42500 |
| 6 | 65000 | Corporation | 60000 |
| 7 | 45000 | Sole proprietor | 52500 |
| 8 | 55000 | Corporation | 60000 |
| 9 | 50000 | Partnership | 42500 |
| 10 | 60000 | Corporation | 60000 |

## **Additional Info**

**[https://www.kaggle.com/code/tunguz/xgb-simple-features](https://www.kaggle.com/code/tunguz/xgb-simple-features)**
