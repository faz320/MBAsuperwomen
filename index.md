# MBA Superwomen
<img src="pics/superwomen.png" alt="superwomen" width="400"/>
<br>
**_You will never know who's who!_**
<br>

# ESG Impact on Financial Performance
I.&nbsp;&nbsp;&nbsp;<a href='#introduction'>Introduction</a> <br>
II.&nbsp;&nbsp;<a href='#methodology'>Methodology</a> <br>
III.&nbsp;<a href='#results'>Results</a> <br>

<a id ='introduction'></a>
## **I.&nbsp;&nbsp;&nbsp;INTRODUCTION**
### ESG Background

**ESG criteria** are a set of standards for a firm’s operations; refers to the three key factors when measuring the sustainability and ethical impact of an investment in a business or company <br>
-- **Environmental:** how a company performs as a steward of nature <br>
-- **Social:** examines how it manages relationships with employees, suppliers, customers, and the communities where it operates <br>
-- **Governance:** deals with a company’s leadership, executive pay, audits, internal controls and shareholder rights

<p align="center">
  <img src="pics/ESG Picture 1.png" alt="ESG Pic 1" width="500"/>
</p>
<br>

**The Financial Times defines ESG as:**
> “A generic term used in capital markets and used by investors to evaluate corporate behavior and to determine the future financial performance of companies… [ESG] is a subset of non-financial performance indicators which include sustainable, ethical and corporate governance issues such as managing a company’s carbon footprint and ensuring there are systems in place to ensure accountability.”

**Paris Agreement in 2015:**

> After the Paris agreement, firms most exposed to climate transition risk also saw their ratings deteriorate whereas other comparable firms did not... These results have policy implications for corporate disclosures and strategies around climate change and the treatment of the climate-related transition risk faced by the financial sector (European Central Bank).<br>
<br>
> Over 100 companies have signed The Climate Pledge... It's part of a growing trend of corporations announcing climate targets in line with or ahead of those established by the Paris Agreement. In 2021 alone, 75 new companies have joined The Climate Pledge - bringing the total to 108 (Perillon).<br>

### <a href="https://www.mckinsey.com/business-functions/sustainability/how-we-help-clients">McKinsey - New Perspective on ESG (February 2020)</a>

-- **Increasing public and company _perception_** and pressure that ESG programs create short-term and long-term value <br>
&nbsp;&nbsp;&nbsp;- 10%-15% median premium to acquire a company with a positive ESG record over a company with a negative record (regardless of whether executives believe ESG programs have no effect on shareholder value) <br>

<p align="center">
  <img src="pics/ESG Picture 2.png" alt="ESG Pic 2" width="600"/>
</p>
<br>

-- 58% of respondents say **the current political environment has _increased_** the importance of ESG programs <br>
&nbsp;&nbsp;&nbsp;- Strengthening the organization’s **competitive position** and meeting **stakeholder expectations** for good corporate behavior <br>
&nbsp;&nbsp;&nbsp;- The existence of high-performing ESG programs is **a proxy for good management** <br>

<p align="center">
  <img src="pics/ESG Picture 3.png" alt="ESG Pic 3" width="600"/>
</p>
<br>

-- **Compliance** was cited as **the most important** aspect of ESG-related activities, rather than changing business processes to incorporate good ESG practices <br>

<p align="center">
  <img src="pics/ESG Picture 4.png" alt="ESG Pic 4" width="600"/>
</p>
<br>

### Research Question

**How do ESG ratings impact companies’ financial performance and credit rating?** <br>
-- We will study and aggregate three individual ESG categories (Environmental, Social and Governance) <br>
-- We will then examine their impact on corporate financial performance including profitability and financial risk, as well as credit ratings <br>

### <a href="https://www.mdpi.com/2071-1050/13/7/3746/htm">Literature Review (Western University 2021)</a>

#### Objective
-- To examine the relationship between ESG factors and corporate financial performance, including profitability and financial risk <br>
-- To provide the rationale for ESG-integrated investment management strategies <br>

#### Data Used
-- S&P Capital IQ-Compustat database; from 1991 to 2013 based on 4708 firms in all industries, and combined with MSCI ESG dataset <br>

#### Findings 
-- Positive effect of ESG factors on corporate profitability, and the effect was more pronounced for larger firms <br>
-- Corporate governance (G) has the most significant impact, particularly for firms with weak governance <br>
-- Social factor (S) has the most significant impact on credit rating, while the environmental score surprisingly has a negative effect <br>
-- While the ESG factors seem to have largely positive impact on financial performance based on approximately 2200 studies, the research in this area is extensive, accelerating, and still inconclusive depending on data sample, sample period, empirical methods and different industries or countries <br>

### Hypotheses
-- ESG has a positive impact on corporate profitability <br>
-- Among different ESG factors, governance category has the most significant impact on corporate finance performance <br>
-- ESG factors have a significant correlation with corporate credit risks, which are measured by credit ratings <br>

<a id ='methodology'></a>
## **II.&nbsp;&nbsp;METHODOLOGY**
### Data Collection 
#### Data Source
-- All data including financial ratios, ESG disclosure scores and default risk from 2011 to 2021 of S&P 500 firms is retrieved from Bloomberg Terminals located in the Rauch Business Center at Lehigh University <br>

#### Bloomberg Query Language
-- BQL is written in Excel in Bloomberg terminals to download the data in batches <br>
-- ‘SPX Index’ retrieves information for S&P 500 firms <br>
-- BQL Example: <br>
`‘A US = B4& "EQUITY" =BDH(B3, $C$1, A3, A3, "Currency = USD", "Period = FY", "BEST_FPERIOD_OVERRIDE = FY", "FILING_STATUS = MR", "Sort = A", "Dates = H", "DateFormat = P", "Fill = —", "Direction = H", "UseDPDF = Y")’`<br>
&nbsp;&nbsp;&nbsp;&nbsp;> **B3** represents the ticker symbol <br>
&nbsp;&nbsp;&nbsp;&nbsp;> **C1** represents the variable name <br>
&nbsp;&nbsp;&nbsp;&nbsp;> **A3** represents the fiscal year <br>

#### Variables 

<p align="center">
  <img src="pics/variables.png" alt="Variables" width="600"/>
</p>
<br>

<p align="center">
  <img src="pics/figure 1 - tesla v2.png" alt="Figure 1" width="800"/>
</p>
<br>

#### Dataset Summary

<p align="center">
  <img src="pics/table 1 - summary v2.png" alt="Table 1" width="800"/>
</p>
<br>

### Data Transformation and Cleaning
-- The dataset is in a firm-year format. Mean values of the ESG scores and financial ratios were used when analyzing the relationship between the financial performance and ESG rating of the firms <br>
-- All ESG scores are expressed in a range between 0.1 and 100, from the very minimum governance data disclosed to all data disclosed, as collected by Bloomberg. Companies with zero disclosure will show a value of 0 <br>
-- The dataset contains many missing values. As shown in Table 3, 17.4% of the current ratio and 11.5% of ESG disclosure, environmental disclosure, social disclosure and governmental disclosure each are missing. The missing values were ignored as part of this assessment <br>

<p align="center">
  <img src="pics/table 2 - missing values v2.png" alt="Table 2" width="800"/>
</p>
<br>

-- Our credit scores are based on the Bloomberg default risk model, expressed in a combination of both numbers and letters <br>
&nbsp;&nbsp;&nbsp;&nbsp;> For example, 1-year default risk IG2 which represents an estimated 1-year default probability between 0.002%-0.004%. For the purpose of this analysis, the maximum value of the range was assigned to the corresponding risk (i.e., 0.004%) <br>

<p align="center">
  <img src="pics/figure 2 - american airline v2.png" alt="Figure 2" width="800"/>
</p>
<br>

-- The dataset was also sliced into two sets (2011-2015 and 2016-2021) to compare the findings pre- and post- Paris Agreement <br>

### Relationship Analysis
-- **Visualization:** Correlation heatmap and scatter plots were used to visualize the relationship between different pairs of variables. Boxplots were used to visualize the changes over the years. All figures can be found in later sections <br>
-- **Regression analysis:** 12 multivariate regression models were constructed, 4 regressions for the profitability variable, aka. ROA, across all years. Another 8 regressions were constructed for the profitability variable to compare the effect before and after the Paris Agreement. Nature log was applied to total asset observations to mitigate the potential issues related to measurement scaling. The following are the generalized regression formulas that were used in this analysis
`RETURN_ON_ASSET = ɑ + 𝛽1(ESG_DISCLOSURE_SCORE, SOCIAL_DISCLOSURE_SCORE, GOVNCE_DISCLOSURE_SCORE or ENVIRON_DISCLOSURE_SCORE) + 𝛽2(TOT_DEBT_TO_TOT_EQY) + 𝛽3(CUR_RATIO) + 𝛽4(log(BS_TOT_ASSET) + e`
`RN365 = ɑ + 𝛽1(ESG_DISCLOSURE_SCORE, SOCIAL_DISCLOSURE_SCORE, GOVNCE_DISCLOSURE_SCORE or ENVIRON_DISCLOSURE_SCORE) + 𝛽2(TOT_DEBT_TO_TOT_EQY) +𝛽3(CUR_RATIO) + 𝛽4(log(BS_TOT_ASSET) + e`







<a id ='results'></a>
## **III.&nbsp;RESULTS**





