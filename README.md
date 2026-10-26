# WalgamaMart | Retail Sales & Profitability Dashboard

An Excel-based retail performance analytics portfolio project using a fictional retail sales dataset. The dashboard summarizes revenue, profitability, store performance, sales channels, and top products.

## Business scenario
WalgamaMart is a fictional multi-store retailer that sells through in-store and online channels. Management needs a consistent view of sales performance to compare stores, review monthly patterns, and identify profitable products.

## Project objectives
- Track sales revenue, gross profit, and gross profit margin.
- Compare sales across stores and channels.
- Examine monthly revenue trends.
- Rank products by gross profit.
- Provide interactive filters for store and sales channel on the original PivotChart dashboard.

## Tools and techniques
Microsoft Excel; Excel Tables and structured references; formulas; PivotTables; PivotCharts; slicers; linked KPI cards. No external database or web service is required.

## Dataset
The synthetic `sales` table contains 500 transaction rows dated January 2025 to June 2026, with 17 columns including transaction identifiers, dimensions, and calculated financial measures. See [Data dictionary](documentation/data_dictionary.md).

## KPI definitions
| KPI | Calculation |
|---|---|
| Total revenue | Sum of `SalesAfterDiscount` |
| Gross profit | Sum of `GrossProfit` |
| Gross margin | Gross profit / revenue |
| Total orders | Count of `OrderID` rows (valid because IDs are unique in this dataset) |
| Quantity sold | Sum of `Quantity` |
| Average order value | Revenue / total orders |

## Baseline project results
- Total revenue: **LKR 15,033,192.35**
- Gross profit: **LKR 2,700,692.35**
- Gross margin: **17.96%**
- Orders: **500**
- Quantity sold: **1,560 units**
- Average order value: **LKR 30,066.38**

These are unfiltered totals from the provided project version; refresh and revalidate if the source data changes.

## Dashboard components
1. KPI cards: revenue, gross profit, margin, orders, units, average order value.
2. Monthly sales revenue line chart.
3. Revenue by store bar chart.
4. Sales by channel doughnut chart.
5. Top 10 products by gross profit bar chart.
6. Store and sales channel slicers on the original PivotChart dashboard.

## How to use
1. Open `WalgamaMart_Dashboard.xlsx` in Microsoft Excel desktop.
2. Select the `Dashboard` worksheet to explore the original PivotCharts and slicers.
3. Use slicers to filter the compatible connected PivotTables and PivotCharts.
4. Use `KPI_Summary` for overall KPI totals; these SUM-based KPI cells **do not respond to slicers**.
5. If sales data is edited, choose **Data → Refresh All**, then check all formulas, PivotTables and charts.
6. If the workbook includes `Executive_Dashboard`, treat its separate charts as a visual overview; they are not necessarily slicer-connected.

## Project structure
```text
WalgamaMart-Retail-Sales-Dashboard/
├── dashboard/
│   └── WalgamaMart_Dashboard.xlsx
├── screenshots/
│   └── dashboard_preview.png
├── documentation/
│   ├── data_dictionary.md
│   ├── business_insights.md
│   └── system_overview.png
└── README.md
```

## Key limitations
- This is a fictional dataset, not a live commercial system.
- The reported margin is **gross margin**, not net profit margin; operating expenses and taxes are excluded.
- Row counts represent orders only because this sample uses one unique OrderID per transaction row. For multi-line orders, use distinct OrderID counts.
- Slicer-connected PivotCharts and independent formula-driven KPI cards may show different filter scopes.
- The dashboard is a local Excel workbook and does not automatically synchronize with external systems.

## Business interpretation
See [Business insights](documentation/business_insights.md) for evidence-based findings, follow-up questions and suggested management actions.
