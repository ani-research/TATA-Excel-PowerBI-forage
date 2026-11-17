# Online Retail Analysis -- TATA Job Simulation

## Project overview

This project contains the Excel data-preparation and Power BI reporting
files used as part of a **TATA job simulation**. The work is based on an
online retail transactions dataset and is organised around preparing
transaction-level data, summarising sales activity, and exploring
revenue and quantity patterns across time, countries, and customers.

## Files in this project

  `Online Retail Data Set.xlsx`       Source dataset. Contains 541,909
                                      transaction records (excluding the
                                      header) and 10 columns, including
                                      two helper fields used to flag
                                      records for inclusion or exclusion.

  `Online Retail.xlsx`                Excel working file containing the
                                      transaction-level `Online Retail`
                                      sheet and a country-level pivot
                                      summary in `Sheet2`. It has a
                                      `Revenue` column in the transaction
                                      sheet. `Sheet1` is blank.

  `Online Retail.pbix`                Power BI report with four report
                                      pages (`Question 1` to
                                      `Question 4`) containing
                                      time-series, country, customer, and
                                      geographic visuals.
                                      
  -----------------------------------------------------------------------

## Source dataset

The source workbook contains one row per transaction line. Its fields
are:


  `InvoiceNo`                         Invoice identifier.

  `StockCode`                         Product or stock identifier.

  `Description`                       Product description.

  `Quantity`                          Number of units on the transaction
                                      line.

  `Items sold`                        Helper flag: `Include` when
                                      `Quantity` is at least 1; otherwise
                                      `Exclude`.

  `InvoiceDate`                       Date and time of the transaction.

  `UnitPrice`                         Unit price recorded for the
                                      transaction line.

  `Earnings`                          Helper flag: `Include` when
                                      `UnitPrice` is zero or positive;
                                      otherwise `Exclude`.

  `CustomerID`                        Customer identifier.

  `Country`                           Country associated with the
                                      transaction.
                                      
  -----------------------------------------------------------------------

The two helper flags are implemented with Excel formulas: -
`Items sold`: `=IF(Quantity<1,"Exclude","Include")` - `Earnings`:
`=IF(UnitPrice<0,"Exclude","Include")`

These flags identify records according to the stated conditions; they do
not themselves calculate sales or revenue.

## Excel working file

`Online Retail.xlsx` contains: - **`Online Retail`** --
Transaction-level data with invoice, product, quantity, date, unit
price, customer, and country fields, plus a `Revenue` column. -
**`Sheet2`** -- A pivot-table summary of total quantity by country. The
displayed pivot output reports a grand total of 5,176,450 units. -
**`Sheet1`** -- Blank in the supplied workbook.

The `Revenue` field is used in the Power BI report. The supplied Excel
worksheet displays the column header, but the cells inspected in the
workbook are blank; therefore, this README does not assume a revenue
formula or calculation is present in that worksheet.

## Power BI report

The `.pbix` file contains four report pages:


  `Question 1`                        Line chart titled **Revenue 2011**,
                                      showing the sum of revenue by
                                      month.

  `Question 2`                        **Revenue by Country** treemap;
                                      **Quantity and Revenue by Country**
                                      clustered column chart; and a
                                      filled map titled **Market
                                      tapped**.

  `Question 3`                        Clustered column chart titled
                                      **Revenue by Customer**, showing
                                      the sum of revenue by customer ID.

  `Question 4`                        Map showing countries, with bubble
                                      size based on the sum of quantity.
                                      
  -----------------------------------------------------------------------

The report uses the `Online Retail` table and the `Revenue`,
`InvoiceDate`, `Country`, `Quantity`, and `CustomerID` fields for its
visuals.

## Suggested analysis questions

-   How does revenue change month by month during 2011?
-   Which countries contribute the most revenue and transaction
    quantity?
-   How does the geographic distribution of sales vary across countries?
-   Which customers account for the largest revenue amounts?
-   Do countries with higher quantities also generate higher revenue?

