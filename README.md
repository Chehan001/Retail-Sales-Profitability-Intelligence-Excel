# LankaMart Retail Analytics — Beginner Dataset

Synthetic practice data, not real company records. All amounts are LKR.

Import each CSV in Excel using Data > Get Data > From Text/CSV. Start with sales.csv, products.csv and stores.csv.

Sales line IDs are unique. DiscountRate is a decimal (0.10 = 10%). UnitCostAtSale is the historical cost for each sale. Returns reference original LineID and include ReturnedCost. Targets and expenses are monthly, not per transaction.

Important: The dataset contains sales through June 2026 but monthly targets and expenses are supplied only for January–June 2025, as a small beginner exercise. For reliable comparative reporting, expand monthly targets and expenses to every period being analyzed.

Key sales formulas: GrossSales=Quantity*UnitPrice; DiscountAmount=GrossSales*DiscountRate; SalesAfterDiscount=GrossSales-DiscountAmount; COGS=Quantity*UnitCostAtSale.

NetRevenue=SalesAfterDiscount-RefundAmount; NetCOGS=COGS-ReturnedCost; GrossProfit=NetRevenue-NetCOGS; OperatingProfit=GrossProfit-Expenses. Aggregate refunds and expenses at the correct reporting grain before combining; do not join monthly expenses to every sales row.
