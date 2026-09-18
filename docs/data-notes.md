# Data notes

## Included workbook

The project includes the supplied `data/Online Retail.xlsx` workbook. Its worksheets are `Online Retail` and `Sheet1`. The following counts were calculated directly from the `Online Retail` worksheet, using rows with an invoice number. The workbook is included without changing its contents.

| Item | Value |
| --- | ---: |
| Retail line items | 541,909 |
| Distinct invoice identifiers | 25,900 |
| Distinct customer IDs, excluding `Guest` | 4,372 |
| Countries | 38 |
| Records labelled `Guest` | 135,080 |
| Records with an identified customer | 406,829 |
| Records with negative quantity | 10,624 |

Invoice timestamps range from **1 December 2010 at 08:26** to **9 December 2011 at 12:50**. The file does not establish a timezone.

## Main fields

| Field | Meaning |
| --- | --- |
| `InvoiceNo` | Invoice identifier. Several product lines can share one invoice. |
| `StockCode` | Item identifier. |
| `Description` | Product or line-item description. |
| `Quantity` | Recorded line-item quantity; negative values are present. |
| `InvoiceDate` | Invoice date and time. |
| `UnitPrice` | Recorded unit price. |
| `CustomerID` | Customer identifier or the shared `Guest` label. |
| `Country` | Country recorded for the line item. |

The workbook also contains helper columns and a separate summary sheet. These have been preserved as supplied.

## Interpretation

- **Records, invoices and customers are different counts.** The screenshot's rounded 542K card matches the 541,909 line items. The distinct customer count excludes `Guest`.
- **Guest records do not identify distinct guests.** The 135,080 guest rows cannot be treated as 135,080 individual people. A shared customer identifier is also not, by itself, proof of account-registration status.
- **Negative quantities are retained in the supplied workbook.** Their treatment should be considered when interpreting sales, returns and revenue measures.
- **The date range spans two calendar years.** Use the year filter when comparing months; otherwise, a month-name chart can combine the same month from different years.
- **Dashboard values depend on report logic and filters.** These workbook counts describe the source data. The embedded DAX definitions and a full Power BI refresh have not been independently executed as part of this repository preparation.

The dataset's original publisher and reuse licence are not specified in the supplied workbook. No new licence is assigned to the dataset by this repository.
