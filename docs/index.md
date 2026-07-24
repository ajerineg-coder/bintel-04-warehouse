# Project Documentation

This site provides project documentation.
Use the documentation navigation to explore.

## How-To Guide

Many instructions are common to all our projects.

See
[⭐ **Workflow: Apply Example**](https://denisecase.github.io/pro-analytics-02/workflow-b-apply-example-project/)
to get the example projects running on your machine.

## Project Documentation Pages (docs/)

- **Home** - this documentation landing page
- [**Project Instructions**](./project-instructions.md)
- [**Your Files**](./your-files.md)
- [**Glossary**](./glossary.md)
- [**API**](./api.md)

---

## Phase 4. Technical Modification

For my technical modification, I customized the visualization section of the project. I changed the regional sales chart title to **"Smart Sales Revenue by Customer Region,"** switched the color palette to purple, and added a third chart showing the top three product categories by total sales revenue.

I chose this because it makes it easier to quickly see which product categories bring in the most revenue.

After making my changes, I ran the application and confirmed all three charts displayed correctly. I did run into a few coding errors while adding the new chart, but fixing them helped me better understand how the application works.
---

## Phase 5. Custom Project

### Basis and Data

The warehouse was populated using three prepared CSV files: **customers_data.csv**, **products_data.csv**, and **sales_data.csv**. The customer file contains customer information, the product file contains product details, and the sales file contains transaction records linking customers and products. During preparation, duplicate records, invalid values, and inconsistent formatting were cleaned before loading. The completed warehouse was stored as **artifacts/smart_sales.duckdb**.

### Warehouse Design

The warehouse uses a star schema with **Sales** as the fact table and **Customers** and **Products** as the dimension tables.

The Sales table includes SaleID, CustomerID, ProductID, SaleDate, Quantity, and SaleAmount. The Customers table includes CustomerID, CustomerName, Region, SpendingScore, and TierLevel. The Products table includes ProductID, ProductName, Category, Price, WarrantyMonths, and ShelfZone.

CustomerID and ProductID serve as the primary keys in the dimension tables and foreign keys in the Sales fact table. A star schema works well because it simplifies reporting while keeping the data organized.

### ETVL Process

The prepared CSV files were extracted into the project and transformed before loading into the warehouse. During transformation, duplicate records were removed, invalid values were corrected, formatting was standardized, and additional attributes created in the previous module were included.

The warehouse tables were then populated and verified by successfully running the ETL workflow and confirming the expected row counts. The successful execution showed that the warehouse loaded correctly.

### Summary

I customized the reporting application by adding a chart that highlights the top three product categories by sales revenue and updating the regional sales chart.

This project helped me better understand how fact and dimension tables work together in a data warehouse and how that data can be used for reporting. A warehouse like this could help a business track sales trends, compare regions, and identify top-selling products to make better decisions.
