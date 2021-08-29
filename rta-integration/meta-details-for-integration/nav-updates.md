# NAV Updates

NAV Updates is another crucial factor for preparing reports for the customers and to show them the change in their investments. 

NAV Sources

1. The most reliable source for NAV updates is the AMFI Website. The link [https://www.amfiindia.com/spages/NAVAll.txt](https://www.amfiindia.com/spages/NAVAll.txt) updates everyday with the latest NAVs and should be read to update the NAV against the ISINs. 
2. Other Sources of NAV can be directly from the RTA \( but the RTA files are not NAV based necessarily \) 

### CAMS NAV File

CAMS provides WBR1/WBR8 file for NAV everyday which can be scheduled and read to update NAV

#### Format

WBR1 / WBR8 : NAV Data Feed

| Field Sequence | Data Item | Maximum Width | Remarks |
| :--- | :--- | :--- | :--- |
| Field 1 | Product Code | 8 | A unique product code aigned by CAMS for each NAV |
| Field 2 | Product Name | 100 | Name of the Product |
| Field 3 | NAV Date | Date \(mm/dd/yyyy\) |  |
| Field 4 | NAV Value | 25,6 |  |
| Field 5 | Dividend Per Unit | 25,6 | Retail Dividend per unit |
| Field 6 | Corpdivrate | 25,6 | Corporate dividend per unit |
| Field 7 | Scheme Type | 15 | Scheme Type |
| Field 8 | ISIN\_NO | 16 | ISIN Number |



