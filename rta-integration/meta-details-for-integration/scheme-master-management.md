# Scheme Master Management

Scheme master management is the most crucial part because it decides the order validation on the app for the customer and also the validation on the RTA side for order placement. 

There are various sources of scheme master and the biggest issue is that the industry does not rely on one standard identifier for schemes. Hence, we need to make our system by collating data from various sources. 

Part of Scheme has 2 major components

a. ISIN, Scheme codes, Dividend identifier

b. Scheme limit information like min purchase amount, min add purchase amount min sip amount, sip dates etc. 

Scheme master needs to be build out of CAMS Scheme master and the data shared by the AMCs at the time of integration

### CAMS Scheme Master

**File Name : WBR39: Scheme details**

#### Format

| Field Sequence | Data Item | Maximum Width | Remarks | Comments |
| :--- | :--- | :--- | :--- | :--- |
| Field 1 | Amc\_code | 8 | Amc code |  |
| Field 2 | amc | 50 | AMC Name |  |
| Field 3 | sch\_code | 8 | Scheme code | Most important field |
| Field 4 | sch\_name | 100 | Scheme name | Scheme Name \( non usable \) |
| Field 5 | sch\_type | 15 | Scheme Type |  |
| Field 6 | div\_reinv | 1 | Divident reinvest flag | POssible Values  X : Both Payout and Reinvest options Available Y : Only reinvest Z : Growth |
| Field 7 | sip\_allow | 1 | SIP Allowed | SIP flag  |
| Field 8 | lien | 1 | LIEN | Not relevant |
| Field 9 | swt\_mn\_amt | 25,6 | Switch minimum amount | Amount conditions |
| Field 10 | swt\_mx\_amt | 25,6 | Switch maximum amount | Amount conditions |
| Field 11 | swt\_mn\_unt | 25,6 | Switch minimum units | Amount conditions |
| Field 12 | swt\_mx\_unt | 25,6 | Switch maximum units | Amount conditions |
| Field 13 | swi\_multi | 25,6 | Switch multiples | Amount conditions |
| Field 14 | adp\_mn\_amt | 25,6 | Additional purchase minimum amount | Amount conditions |
| Field 15 | adp\_mx\_amt | 25,6 | Additional purchase maximum amount | Amount conditions |
| Field 16 | adp\_mn\_unt | 25,6 | Additional purchase minimum units | Amount conditions |
| Field 17 | adp\_mx\_unt | 25,6 | Additional purchase maximum units | Amount conditions |
| Field 18 | newp\_mnval | 25,6 | New purchase minimum value | Amount conditions |
| Field 19 | newp\_mxval | 25,6 | New purchase maximum value | Amount conditions |
| Field 20 | p\_mn\_incr | 25,6 | Purchase minimum increment amount | Amount conditions |
| Field 21 | red\_mn\_amt | 25,6 | Redemption minimum amount | Amount conditions |
| Field 22 | red\_mx\_amt | 25,6 | Redemption maximum amount | Amount conditions |
| Field 23 | red\_mn\_unt | 25,6 | Redemption minimum units | Amount conditions |
| Field 24 | red\_mx\_unt | 25,6 | Redemption maximum units | Amount conditions |
| Field 25 | red\_incr | 25,6 | Redemption incremental | Amount conditions |
| Field 26 | mn\_swp\_amt | 25,6 | Minimum SWP amount | Amount conditions |
| Field 27 | mx\_swp\_amt | 25,6 | Maximum SWP amount | Amount conditions |
| Field 28 | close\_end | 1 | Close ended | close ended or open ended   Y : Close N: Open |
| Field 29 | elss\_sch | 1 | ELSS Scheme | Y : ELSS  N : No |
| Field 30 | mature\_dt | Date \(mm/dd/yyyy\) | Maturity Date | Only for close ended |
| Field 31 | face\_value | 25,6 | Face value | Not relevant |
| Field 32 | asset\_class | 10 | Asset class |  |
| Field 33 | sebi\_class | 60 | SEBI Asset class | SEBI Asset class |
| Field 34 | settle\_per | 3,0 | Settlement period | Not relevant |
| Field 35 | sip\_dates | 200 | SIP Dates | This is not much important since very few schemes/amcs have specific dates for SIP rest all nearly have all days but still should be read |
| Field 36 | swp\_dates | 200 | SWP Dates |  |
| Field 37 | stp\_dates | 200 | STP Dates |  |
| Field 38 | sys\_freqs | 200 | Systematic frequencies |  |
| Field 39 | swp\_allow | 1 | SWP ENABLED |  |
| Field 40 | stp\_allow | 1 | STP\_ENABLED |  |
| Field 41 | plan\_type | 7 | Plan Type \(DIRECT or REGULAR\) | REGULAR or DIRECT |
| Field 42 | sf\_code | 8 | Sub fund code |  |
| Field 43 | sf\_name | 100 | Sub fund name | This is the clean fund name and other extensions can be added dynamically later. This should be used |
| Field 44 | START\_DATE | Date \(mm/dd/yyyy\) | Scheme start date | Not relevant |
| Field 45 | SWT\_ALLOW | 1 | Switch allowed |  |
| Field 46 | ADP\_MN\_INC | 25,6 | Addl. Purchase incremental amount |  |
| Field 47 | PUR\_ALLOW | 1 | Purchase allowed |  |
| Field 48 | RED\_ALLOW | 1 | Redemption allowed |  |
| Field 49 | SIP\_MN\_INS | 3 | Minimum SIP installment months |  |
| Field 50 | SIP\_MN\_AMT | 25,6 | Minimum SIP amount |  |
| Field 51 | SIP\_MULTI | 25,6 | Multiple of SIP amount |  |
| Field 52 | SIP\_MX\_AMT | 25,6 | Maximum SIP amount |  |
| Field 53 | SWP\_MN\_INS | 3 | Minimum SWP installment months |  |
| Field 54 | SWP\_MULTI | 25,6 | Miltiple of SWP amount |  |
| Field 55 | parent\_scheme\_code | 5 | Parent scheme code | Not relevant |
| Field 56 | ISIN\_NO | 16 | ISIN Number |  |
| Field 57 | DISPLAY\_DATA\_ENTRY | 2 | DISPLAY DATA ENTRY |  |

#### Sample Data received

| AMC\_CODE,C,8 | AMC,C,50 | SCH\_CODE,C,8 | SCH\_NAME,C,100 | SCH\_TYPE,C,15 | DIV\_REINV,C,1 | SIP\_ALLOW,C,1 | LIEN,C,1 | SWT\_MN\_AMT,N,25,6 | SWT\_MX\_AMT,N,25,6 | SWT\_MN\_UNT,N,25,6 | SWT\_MX\_UNT,N,25,6 | SWI\_MULTI,N,25,6 | ADP\_MN\_AMT,N,25,6 | ADP\_MX\_AMT,N,25,6 | ADP\_MN\_UNT,N,25,6 | ADP\_MX\_UNT,N,25,6 | NEWP\_MNVAL,N,25,6 | NEWP\_MXVAL,N,25,6 | P\_MN\_INCR,N,25,6 | RED\_MN\_AMT,N,25,6 | RED\_MX\_AMT,N,25,6 | RED\_MN\_UNT,N,25,6 | RED\_MX\_UNT,N,25,6 | RED\_INCR,N,25,6 | MN\_SWP\_AMT,N,25,6 | MX\_SWP\_AMT,N,25,6 | CLOSE\_END,C,1 | ELSS\_SCH,C,1 | MATURE\_DT,D | FACE\_VALUE,N,25,6 | ASSET\_CLAS,C,10 | SEBI\_CLASS,C,60 | SETTLE\_PER,N,3,0 | SIP\_DATES,C,200 | SWP\_DATES,C,200 | STP\_DATES,C,200 | SYS\_FREQS,C,200 | SWP\_ALLOW,C,1 | STP\_ALLOW,C,1 | PLAN\_TYPE,C,7 | SF\_CODE,C,8 | SF\_NAME,C,100 | START\_DATE,D | SWT\_ALLOW,C,1 | ADP\_MN\_INC,N,25,6 | PUR\_ALLOW,C,1 | RED\_ALLOW,C,1 | SIP\_MN\_INS,N,25,6 | SIP\_MN\_AMT,N,25,6 | SIP\_MULTI,N,25,6 | SIP\_MX\_AMT,N,25,6 | SWP\_MN\_INS,N,25,6 | SWP\_MULTI,N,25,6 | PARENT\_SCH,C,5 | ISIN\_NO,C,16 | DISPLAY\_DA,C,1 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| D | DSP Mutual Fund | 11 | DSP Flexi Cap Fund - Regular Plan - IDCW \(54EA Benefits\) \(Earlier: DSP Equity Fund\) | Equity\(G\) | X | N | Y | 0.01 | 9999999999.99 | 0.001 | 9999999999.999 | 0.01 | 0 | 9999999999.99 | 0.001 | 9999999999.999 | 0 | 10000000000000000 | 0.01 | 500 | 9999999999.99 | 0.001 | 9999999999.999 | 0.01 | 500 | 1000000000000000 | N | N | 26/04/99 | 10 | EQUITY | Other Equity Schemes | 3 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM,DZ,BZ | N | N | REGULAR | DSPEQ | DSP Flexi Cap Fund | 29/04/97 | Y | 0.01 |  |  |  | 0 | 0.01 | 10000000000 |  | 0.01 | 11 |  | Y |
| D | DSP Mutual Fund | 32 | DSP Bond Fund - IDCW - \(54EB Benefits\) | Bond | X | N | Y | 0.01 | 9999999999.99 | 0.001 | 9999999999.999 | 0.01 | 0 | 9999999999.99 | 0.001 | 9999999999.999 | 0 | 9999999999.99 | 0.01 | 500 | 9999999999.99 | 0.001 | 9999999999.999 | 0.01 | 500 | 10000000000 | N | N | 02/05/99 | 10 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | N | N | REGULAR | DSPBD | DSP Bond Fund | 29/04/97 | Y | 0.01 |  |  |  | 0 | 0.01 | 0 |  | 0.01 | 32 |  | Y |
| D | DSP Mutual Fund | 05 | DSP Equity & Bond Fund - IDCW \(54EA Benefits\) | Balanced | X | N | Y | 500 | 9999999999.99 | 0.01 | 9999999999.999 | 0.01 | 0 | 9999999999.99 | 0.01 | 9999999999.999 | 0 | 9999999999.99 | 0.01 | 500 | 9999999999.99 | 0.01 | 9999999999.999 | 0.01 | 500 | 10000000000 | N | N | 03/05/99 | 10 | EQUITY | Balanced | 3 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | N | N | REGULAR | DSPBL | DSP Equity & Bond Fund | 03/05/99 | Y | 0.01 |  |  |  | 0 | 0.01 | 10000000000 |  | 0.01 | 5 |  | Y |
| D | DSP Mutual Fund | 776 | DSP Top 100 Equity Fund - Direct Plan - Growth | Equity\(G\) | Z | Y | Y | 0.01 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 500 | 9999999999.99 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 10000000000 | N | N | 31/12/99 | 10 | EQUITY | Other Equity Schemes | 3 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | Y | B | DIRECT | DSPTE | DSP TOP 100 Equity | 31/12/12 | Y | 0.01 |  |  | 6 | 500 | 1 | 10000000000 | 6 | 0.01 | 776 | INF740K01PR3 | Y |
| D | DSP Mutual Fund | 831 | DSP Low Duration Fund - Direct Plan - IDCW - Monthly | Ultra Liquid | X | Y | Y | 0.01 | 1000000000000000 | 0 | 100000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 500 | 100000000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 0.01 | 500 | 1E+17 | N | N | 31/12/99 | 10 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,19,18,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,19,18,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,19,18,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | Y | B | DIRECT | DUSTF | DSP Low Duration Fund | 27/02/15 | Y | 0.01 |  |  | 6 | 500 | 0.01 | 1E+17 | 6 | 0.01 | 831 | INF740K014Q9 | Y |
| D | DSP Mutual Fund | 567 | DSP Equity Savings Fund - Reg - IDCW - Quarterly | MIP | X | Y | Y | 0.01 | 1000000000000000 | 0 | 100000000000000 | 0.01 | 500 | 1000000000000000 | 0 | 100000000000000 | 500 | 1000000000000000 | 0.01 | 500 | 1000000000000000 | 0 | 100000000000000 | 0.01 | 500 | 1000000000000000 | N | N | 31/12/99 | 10 | EQUITY | Other Equity Schemes | 3 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM,DZ,BZ | Y | B | REGULAR | DEQSF | DSP Equity Savings Fund | 08/03/16 | Y | 0.01 |  |  | 6 | 500 | 0.01 | 1000000000000000 | 6 | 0.01 | 567 | INF740KA1488 | Y |
| D | DSP Mutual Fund | 70 | DSP Short Term Fund - Regular Plan - Growth | STP | Z | Y | Y | 0.01 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 500 | 9999999999.99 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 1000000000000000 | N | N | 31/12/99 | 10 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | Y | B | REGULAR | DSPST | DSP Short Term Fund | 09/09/02 | Y | 0.01 |  |  | 6 | 500 | 0.01 | 10000000000 | 6 | 0.01 | 70 | INF740K01656 | Y |
| D | DSP Mutual Fund | 78 | DSP Credit Risk Fund - Regular Plan - Growth | STP | Z | Y | Y | 0.01 | 10000000000 | 0 | 9999999999.999 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 500 | 9999999999.99 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 10000000000 | N | N | 31/12/99 | 10 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | Y | B | REGULAR | DSPFR | DSP Credit Risk Fund | 12/05/03 | Y | 0.01 |  |  | 6 | 500 | 0.01 | 1E+16 | 6 | 0.01 | 78 | INF740K01599 | Y |
| D | DSP Mutual Fund | 527 | DSP Ultra Short Fund - Regular Plan - IDCW - Reinvestment | Ultra Liquid | Y | N | Y | 0.01 | 1000000000000000 | 0 | 100000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 500 | 100000000000000000 | 0.01 | 500 | 10000000000000 | 0 | 1000000000000 | 0.01 | 500 | 10000000000000 | N | N | 31/12/99 | 1000 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | N | N | REGULAR | DSPLP | DSP Ultra Short Fund | 22/10/12 | Y | 0.01 |  |  |  | 500 | 0.01 | 1E+17 |  | 0.01 | 526 | INF740K01ML3 | E |
| D | DSP Mutual Fund | 728 | DSP Equity & Bond Fund - Direct Plan - IDCW | Balanced | X | Y | Y | 0.01 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 500 | 9999999999.99 | 0.01 | 500 | 9999999999.99 | 0 | 9999999999.999 | 0.01 | 500 | 10000000000 | N | N | 31/12/99 | 10 | EQUITY | Balanced | 3 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | Y | B | DIRECT | DSPBL | DSP Equity & Bond Fund | 31/12/12 | Y | 0.01 |  |  | 6 | 500 | 1 | 10000000000 | 6 | 0.01 | 728 | INF740K01NZ1 | Y |
| D | DSP Mutual Fund | 834 | DSP Low Duration Fund - Direct Plan - IDCW - Quarterly Reinvest | Ultra Liquid | Y | N | Y | 0.01 | 1000000000000000 | 0 | 100000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 500 | 100000000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 0.01 | 500 | 1E+17 | N | N | 31/12/99 | 10 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,19,18,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,19,18,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,19,18,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | N | N | DIRECT | DUSTF | DSP Low Duration Fund | 27/02/15 | Y | 0.01 |  |  |  | 500 | 0.01 | 1E+17 |  | 0.01 | 833 | INF740K017Q2 | E |
| D | DSP Mutual Fund | 806 | DSP Banking and PSU Debt Fund - Dir - IDCW - Monthly | STP | X | Y | Y | 0.01 | 1000000000000000 | 0 | 100000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 500 | 100000000000000000 | 0.01 | 500 | 100000000000000000 | 0 | 100000000000000000 | 0.01 | 500 | 1E+17 | N | N | 31/12/99 | 10 | DEBT | Debt\(other than assured return schemes\) | 1 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM,SM | Y | B | DIRECT | DSPBP | DSP Banking and PSU Debt Fund | 10/09/13 | Y | 0.01 |  |  | 6 | 500 | 0.01 | 1E+17 | 6 | 0.01 | 806 | INF740K01ZX0 | Y |
| D | DSP Mutual Fund | 577 | DSP Arbitrage Fund - Reg - IDCW | Arbitrage Fund | X | Y | Y | 0.01 | 10000000000000 | 0 | 1000000000000 | 0.01 | 500 | 10000000000000 | 0 | 1000000000000 | 500 | 10000000000000 | 0.01 | 500 | 10000000000000 | 0 | 1000000000000 | 0.01 | 500 | 10000000000000 | N | N | 31/12/99 | 10 | EQUITY | Other Equity Schemes | 3 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | 01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31 | Q,OM | Y | B | REGULAR | DABEF | DSP Arbitrage Fund | 15/01/18 | Y | 0.01 |  |  | 6 | 500 | 0.01 | 10000000000000 | 6 | 0.01 | 577 | INF740KA1DJ2 | Y |



KARVY Scheme Master

File Name : 

Format 

Sample











