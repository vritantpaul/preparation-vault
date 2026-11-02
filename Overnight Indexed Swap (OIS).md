---
tags:
  - Concept
---
## Interest Swap

![[Index Swap.png]]

- <i>A</i>'s interest rate is fixed because A has to pay 7% (to B) and 1% (difference between interest rate paid by B and interest rate paid to lender 1), both on $1M (principal amount) i.e. A will always have to pay $80,000 as interest.
- <i>B</i>'s interest rate is variable as the interest B is paying to A is variable.

## Overnight Market & Rate

- <b>Overnight Market</b>: The overnight market is where banks and other financial institutions <i>lend and borrow money from each other</i> for a very short period, typically just one night. 
- <b>Overnight Rate</b>: The overnight rate is <i>the interest rate charged</i> in this market for these short-term loans. It's like a quick loan between banks that helps them manage their day-to-day cash needs.

## Secured Overnight Financing Rate (SOFR)

<b>SOFR</b> stands for the <b>Secured Overnight Financing Rate</b>. It's a benchmark[^1] interest rate that banks use to lend to each other overnight in the U.S. money markets. SOFR is intended to replace LIBOR (London Interbank Offered Rate) as a key reference rate for financial markets, as LIBOR is being phased out.

[^1]: A "<i>benchmark</i>" refers to a standard or reference point against which the performance or characteristics of other financial instruments, investments, or rates are measured or compared. It's essentially a yardstick that provides a basis for evaluation and comparison.

## Overnight Index Swap (OIS)
**How Overnight Index[^2] Swap (OIS) works?**

[^2]: An "<i>index</i>" is a system by which changes in the value of something and the rate at which it changes can be recorded, measured, or interpreted.

![[OIS.png]]

- <u>Case 1</u>: <b>Fixed Rate > SOFR</b>
	ABC bank is <i>paying</i>:
	Principal × Time in years × (Fixed Rate - SOFR) %
	=> $50M × 3/12 × (2.5-2.4)/100 = $12,500
- <u>Case 2</u>: <b>SOFR > Fixed Rate</b>
	ABC bank is <i>receiving</i>:
	Principal × Time in years × (SOFR - Fixed Rate) %
	=> $50M × 3/12 × (2.6-2.5)/100 = $12,500

### Sources
- [Interest Rate Swap 1 (Khan Academy)](https://youtu.be/PLjyj1FJqig?si=1Sycm0TN2vMiKwrv)
- [Interest Rate Swap 2 (Khan Academy)](https://youtu.be/xE43JrjCpjE?si=wG44kkoSdnnu2Oiw)
- [Overnight Index Swap (OIS) Explained (finRGB)](https://youtu.be/gJ8fLaMRAhw?si=g59CSSWcCNJ_HT78)
- [Secured Overnight Financing Rate (SOFR) (Investopedia)](https://www.investopedia.com/secured-overnight-financing-rate-sofr-4683954)
- [What is Overnight Indexed Swap? (Tradition Data)](https://www.traditiondata.com/market-education/overnight-index-swaps/)