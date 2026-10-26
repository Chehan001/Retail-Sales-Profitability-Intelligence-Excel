# Business Insights — WalgamaMart

## Scope
This report summarizes the synthetic retail dataset used in the Excel portfolio project. The baseline covers **500 sales transaction rows from January 2025 through June 2026**. Values below are overall, unfiltered totals.

## Executive KPI snapshot

| Metric | Value |
|---|---:|
| Total revenue | LKR 15,033,192.35 |
| Gross profit | LKR 2,700,692.35 |
| Gross profit margin | 17.96% |
| Total orders | 500 |
| Units sold | 1,560 |
| Average order value | LKR 30,066.38 |

## Findings supported by the KPIs

### 1. Revenue and profitability
The business generated approximately **LKR 15.03 million** in post-discount sales and **LKR 2.70 million** in gross profit. A **17.96% gross margin** means approximately LKR 17.96 of gross profit for every LKR 100 in sales, before operating expenses and taxes.

**Management action:** Review product-level margins and discount policies. Prioritize products that generate sustainable gross profit, not simply high sales revenue.

### 2. Basket and order economics
The 500 orders contained 1,560 units, or **3.12 units per order** on average. Average order value was approximately **LKR 30,066.38**.

**Management action:** Compare average order value and units per order across stores and sales channels. Test relevant cross-selling or product bundles, while monitoring gross margin.

### 3. Store and product performance
The workbook includes PivotTables for revenue by store and the top ten products by gross profit. These views support comparisons, but a store's sales rank alone does not establish its profitability or efficiency.

**Management action:** Compare store revenue alongside gross profit and margin. For products, review both total gross profit and unit-level margin before making inventory or promotion decisions.

### 4. Channel performance
The workbook distinguishes **In-Store** and **Online** sales. The sales-channel chart can reveal revenue mix, but it does not by itself show channel operating costs, customer acquisition costs, or net profit.

**Management action:** Monitor channel revenue and gross margin separately; avoid declaring a channel more profitable without its relevant operating expenses.

## Recommended further analyses
1. Monthly year-over-year comparisons for matching months, using complete periods only.
2. Store gross margin ranking, not only revenue ranking.
3. Product profitability by category, if a reliable product master/category field is added.
4. Discounts versus gross margin, segmented by store and channel.
5. Returns, shipping, labor, rent and other expenses to estimate net profitability when data becomes available.

## Data and dashboard limitations
- Synthetic sample data; findings are for practice and portfolio demonstration.
- Gross profit excludes operating expenses and taxes.
- The current order count assumes each `OrderID` is unique per transaction row.
- Formula-driven KPI cards in `KPI_Summary` are overall totals and do not automatically react to slicers.
- Do not interpret the illustrative visual mockup's growth indicators or last-updated date as measured results.

## Portfolio conclusion
WalgamaMart demonstrates the ability to prepare a structured Excel sales model, calculate management KPIs, build PivotTable-based analysis, visualize business performance, and translate numeric results into practical management questions and actions.
