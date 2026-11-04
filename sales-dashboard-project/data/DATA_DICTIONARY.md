# Data dictionary - train.csv

9,800 rows. One row = one product line on an order. 4,922 distinct orders, 793 customers, 2015-2018. All monetary values in USD.

| Column | Type | Description |
|---|---|---|
| Row ID | int | Unique line-item identifier |
| Order ID | string | Order identifier (one order can hold several rows) |
| Order Date | date (DD/MM/YYYY) | Date the order was placed |
| Ship Date | date (DD/MM/YYYY) | Date the order shipped |
| Ship Mode | category | Same Day / First Class / Second Class / Standard Class |
| Customer ID | string | Unique customer identifier |
| Customer Name | string | Customer name |
| Segment | category | Consumer / Corporate / Home Office |
| Country | string | All rows: United States |
| City | string | Customer city (529 distinct) |
| State | string | Customer state (49 distinct) |
| Postal Code | int | 11 missing values; not used in revenue analysis |
| Region | category | Central / East / South / West |
| Product ID | string | Unique product identifier (1,861 distinct) |
| Category | category | Furniture / Office Supplies / Technology |
| Sub-Category | category | 17 distinct (e.g. Phones, Chairs, Binders) |
| Product Name | string | Product description |
| Sales | float | Line-item revenue in USD |

Derived columns used in the notebook: `order_date`, `ship_date`, `fulfill_days` (ship minus order), `year`, `month`, `quarter`.
