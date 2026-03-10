# [cite_start]Causal Analysis of Women's Parliamentary Representation on Female Employment using Gender Quota Reforms [cite: 1]

## Overview
[cite_start]This project explores the causal effect of women’s parliamentary representation on female employment using gender quota adoption as a natural experiment. [cite: 3] [cite_start]The main challenge in this domain is endogeneity: countries with more female representation in the parliament may also have certain unobserved characteristics that would independently improve female employment and education. [cite: 4] [cite_start]To address this, gender quota reforms for each country were used. [cite: 5]

## Data Sources
* [cite_start]**Labor Participation:** Data on female labor participation was dense and had an annual coverage for 214 countries, sourced from the World Development Indicators (WDI). [cite: 10]
* [cite_start]**Timeframe:** The data was consolidated and processed from years 1995 to 2015. [cite: 11]
* [cite_start]**Quota Data:** The QAROT (Quota Adoption and Reform Over Time) dataset was used due to code country alignment issues making longitudinal coding challenging with other databases. [cite: 14]
* [cite_start]**Controls:** A time-varying control variable—log transformed GDP per Capita—was included. [cite: 16] [cite_start]Adding it ensures that the estimated effect of quota adoption is not confounded by economic development. [cite: 18]

## Methodology
[cite_start]To make the project expansive, three causal inference methods were implemented: [cite: 7]
1. [cite_start]**Difference-in-Difference (DiD):** Prior to implementation, the parallel trends assumption was tested, which supported the assumption that treated and control countries followed statistically indistinguishable trends in female labor participation prior to quota adoption. [cite: 21]
2. [cite_start]**Instrumental Variable (IV) Analysis:** This method uses quotas as an instrument to predict representation. [cite: 29]
3. [cite_start]**Mediation Analysis:** Included to decompose the total policy effect into a 'Direct Effect' (the impact of the quota law itself) and an 'Indirect Effect' (the impact through increased parliamentary representation). [cite: 13]

## Key Results
* [cite_start]**General Findings:** The results across all three methods consistently show a positive but statistically non-significant effect of quota adoption on female labor participation. [cite: 24]
* [cite_start]**IV Analysis Estimates:** The Instrumental Variable Analysis indicates that for a 1% increase in female parliamentary seats, female labor participation is estimated to increase by 0.033%. [cite: 29] 
* [cite_start]**Mechanism of Action:** The Mediation Analysis suggests that the driver of improved labor outcomes is the increase in women's parliamentary representation. [cite: 32] [cite_start]The Average Causal Mediation Effect (ACME) was found to be marginally significant, supporting that quotas work by changing who holds legislative power. [cite: 33]
* [cite_start]**Direct Policy Impact:** In contrast, the Average Direct Effect (ADE), which measures the impact of the quota law on labor participation through pathways other than increasing women's parliamentary representation, showed no statistical evidence of an effect. [cite: 34]

## Limitations and Future Work
* [cite_start]**Heterogeneous Effects:** One key shortcoming is the inability to disaggregate countries by social conditions. [cite: 40] [cite_start]More conservative societies may respond to quota adoption very differently than progressive ones; not grouping them likely obscures heterogeneous causal effects, potentially dampening the overall estimate. [cite: 41, 42] [cite_start]A granular analysis would involve grouping countries by gender norms before estimating effects. [cite: 43]
* [cite_start]**Data Sparsity:** The data from WDI for female literacy was sparse due to countries reporting it only once every five to ten years. [cite: 9] [cite_start]Had this been feasible to include, it would have provided a more holistic view of whether quotas result in development beyond labor participation alone. [cite: 44, 45]

## Technologies Used
* Python (`pandas`, `numpy`)
* `wbgapi` for World Bank Data extraction
* `statsmodels` & `linearmodels` for causal inference and mediation modeling
