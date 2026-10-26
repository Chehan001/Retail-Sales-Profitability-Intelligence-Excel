# Data Dictionary — WalgamaMart

## Source table
**Worksheet:** `sales`  
**Excel table:** `sales`  
**Grain:** One sales transaction row per order in this sample.  
**Coverage:** January 2025–June 2026.  
**Volume:** 500 transaction rows.

| Column | Suggested data type | Meaning / calculation |
|---|---|---|
| `OrderID` | Text / identifier | Order identifier; unique per row in the sample |
| `LineID` | Integer / identifier | Transaction line identifier |
| `Date` | Date | Transaction date |
| `ProductID` | Text / identifier | Product code |
| `StoreID` | Text / identifier | Store code, e.g. S01–S05 |
| `CustomerID` | Text / identifier | Customer code |
| `SalesChannel` | Category | In-Store or Online |
| `Quantity` | Whole number | Units purchased |
| `UnitPrice` | Decimal (LKR) | Selling price per unit before discount |
| `DiscountRate` | Decimal (0–1) | Fractional discount applied to gross sales |
| `UnitCostAtSale` | Decimal (LKR) | Cost per unit at the time of sale |
| `GrossSales` | Decimal (LKR) | `Quantity * UnitPrice` |
| `DiscountAmount` | Decimal (LKR) | `GrossSales * DiscountRate` |
| `SalesAfterDiscount` | Decimal (LKR) | `GrossSales - DiscountAmount` |
| `CostOfGoodsSold` | Decimal (LKR) | `Quantity * UnitCostAtSale` |
| `GrossProfit` | Decimal (LKR) | `SalesAfterDiscount - CostOfGoodsSold` |
| `GrossProfitMargin` | Decimal / percentage | `GrossProfit / SalesAfterDiscount`, where revenue is nonzero |

## KPI definitions

| KPI | Excel-style formula | Interpretation |
|---|---|---|
| Total Revenue | `=SUM(sales[SalesAfterDiscount])` | Net sales after discounts; before operating expenses |
| Gross Profit | `=SUM(sales[GrossProfit])` | Revenue less cost of goods sold |
| Gross Margin | `=IFERROR(SUM(sales[GrossProfit])/SUM(sales[SalesAfterDiscount]),0)` | Weighted gross margin across transactions |
| Total Orders | `=COUNTA(sales[OrderID])` | Works here because OrderID is unique per row |
| Quantity Sold | `=SUM(sales[Quantity])` | Total units sold |
| Average Order Value | `=IFERROR(SUM(sales[SalesAfterDiscount])/COUNTA(sales[OrderID]),0)` | Revenue per order in this dataset |

## Data validation checks
- No blank `OrderID`, `Date`, `ProductID`, `StoreID` or `SalesChannel` values.
- `Quantity > 0`; `UnitPrice >= 0`; `UnitCostAtSale >= 0`.
- `DiscountRate` between 0 and 1.
- `GrossSales = Quantity × UnitPrice`.
- `GrossProfit = SalesAfterDiscount − CostOfGoodsSold`.
- Check duplicate `OrderID` before interpreting row count as distinct orders.
- Confirm all PivotTables and charts have been refreshed after changes.

**Note:** Financial values are in Sri Lankan rupees (LKR). Field descriptions reflect the project's current calculation model; they are not evidence of external accounting-system integration.
