# Sales volume of interchangeable products

## **The idea behind**

Referring to the idea of substitutes if a specific item or flavor is not available on the shelf, customers will choose another one; for example, various types of drinking yogurts or buttermilk). Feature acknowledges that some customers might have a preference for the initially desired product

## **Methodology**

To calculate the sales volume of interchangeable products, we will consider the sales data for different periods (3 months, 6 months, and 12 months). The methodology involves aggregating the sales volume of substitute items during these periods.

### **Data source**

The data source for this feature would be a sales dataset containing information about the products sold, their quantities, and corresponding dates. Additionally, there should be a dictionary table that categorizes products according to their interchangeability. The following columns are needed to create the feature:

**Sales Data Table:**

- **`Product_ID`**: The unique identifier for each product.
- **`Quantity_Sold`**: The quantity of products sold.
- **`Date_Sold`**: The date when the product was sold.

**Interchangeability Dictionary Table:**

- **`Product_ID`**: The unique identifier for each product.
- **`Interchangeable_Category`**: The category to which the product belongs (e.g., drinking yogurts, buttermilk).

Here is an example of the sales data table:

| Product_ID | Quantity_Sold | Date_Sold |
| --- | --- | --- |
| 1 | 50 | 2022-05-10 |
| 2 | 30 | 2022-05-10 |
| 1 | 20 | 2022-06-05 |
| 3 | 40 | 2022-06-05 |
| 2 | 35 | 2022-07-01 |
| 4 | 25 | 2022-07-01 |
| 1 | 60 | 2022-08-15 |
| 4 | 30 | 2022-08-15 |
| 2 | 55 | 2022-09-10 |
| 3 | 45 | 2022-09-10 |

And here is an example of the interchangeability dictionary table:

| Product_ID | Interchangeable_Category |
| --- | --- |
| 1 | Drinking Yogurts |
| 2 | Drinking Yogurts |
| 3 | Drinking Yogurts |
| 4 | Buttermilk |

### **Variables**

| Code | Short desc | Description |
| --- | --- | --- |
| 3M | 3 months | During 3 calendar months prior to the scoring date |
| 6M | 6 months | During 6 calendar months prior to the scoring date |
| 12M | 12 months | During 12 calendar months prior to the scoring date |

### **Code**

```sql

-- Sales volume of interchangeable products for 3 months (3M)
SELECT
  i.Interchangeable_Category,
  SUM(s.Quantity_Sold) AS Sales_Volume_3M
FROM
  Sales_Data s
JOIN
  Interchangeability_Dictionary i ON s.Product_ID = i.Product_ID
WHERE
  s.Date_Sold >= DATE_SUB(SCORING_DATE, INTERVAL 3 MONTH)
GROUP BY
  i.Interchangeable_Category;

-- Sales volume of interchangeable products for 6 months (6M)
SELECT
  i.Interchangeable_Category,
  SUM(s.Quantity_Sold) AS Sales_Volume_6M
FROM
  Sales_Data s
JOIN
  Interchangeability_Dictionary i ON s.Product_ID = i.Product_ID
WHERE
  s.Date_Sold >= DATE_SUB(SCORING_DATE, INTERVAL 6 MONTH)
GROUP BY
  i.Interchangeable_Category;

-- Sales volume of interchangeable products for 12 months (12M)
SELECT
  i.Interchangeable_Category,
  SUM(s.Quantity_Sold) AS Sales_Volume_12M
FROM
  Sales_Data s
JOIN
  Interchangeability_Dictionary i ON s.Product_ID = i.Product_ID
WHERE
  s.Date_Sold >= DATE_SUB(SCORING_DATE, INTERVAL 12 MONTH)
GROUP BY
  i.Interchangeable_Category;

```

### **Assembling example**

Using the provided example tables and the SQL code, we can calculate the sales volume of interchangeable products for different periods:

| Interchangeable_Category | Sales_Volume_3M | Sales_Volume_6M | Sales_Volume_12M |
| --- | --- | --- | --- |
| Drinking Yogurts | 160 | 275 | 335 |
| Buttermilk | 55 | 85 | 85 |

## **Feature performance**

No information provided.

## **Additional Info**

No additional information provided.
