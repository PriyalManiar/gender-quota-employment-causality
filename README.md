# Causal Analysis of Women's Parliamentary Representation on Female Employment using Gender Quota Reforms 

## Overview
This project explores the causal effect of women’s parliamentary representation on female employment using gender quota adoption as a natural experiment. The main challenge in this domain is endogeneity: countries with more female representation in the parliament may also have certain unobserved characteristics that would independently improve female employment and education.To address this, gender quota reforms for each country were used.

## Data Sources
* **Labor Participation:** Data on female labor participation was dense and had an annual coverage for 214 countries, sourced from the World Development Indicators (WDI). 
* **Timeframe:** The data was consolidated and processed from years 1995 to 2015.
* **Quota Data:** The QAROT (Quota Adoption and Reform Over Time) dataset was used due to code country alignment issues making longitudinal coding challenging with other databases.
* **Controls:** A time-varying control variable—log transformed GDP per Capita—was included. Adding it ensures that the estimated effect of quota adoption is not confounded by economic development.

## Methodology
To make the project expansive, three causal inference methods were implemented: 
1. **Difference-in-Difference (DiD):** Prior to implementation, the parallel trends assumption was tested, which supported the assumption that treated and control countries followed statistically indistinguishable trends in female labor participation prior to quota adoption. 
2. **Instrumental Variable (IV) Analysis:** This method uses quotas as an instrument to predict representation. 
3. **Mediation Analysis:** Included to decompose the total policy effect into a 'Direct Effect' (the impact of the quota law itself) and an 'Indirect Effect' (the impact through increased parliamentary representation). 

## Key Results
* **General Findings:** The results across all three methods consistently show a positive but statistically non-significant effect of quota adoption on female labor participation. 
* **IV Analysis Estimates:** The Instrumental Variable Analysis indicates that for a 1% increase in female parliamentary seats, female labor participation is estimated to increase by 0.033%. 
* **Mechanism of Action:** The Mediation Analysis suggests that the driver of improved labor outcomes is the increase in women's parliamentary representation. The Average Causal Mediation Effect (ACME) was found to be marginally significant, supporting that quotas work by changing who holds legislative power. 
* **Direct Policy Impact:** In contrast, the Average Direct Effect (ADE), which measures the impact of the quota law on labor participation through pathways other than increasing women's parliamentary representation, showed no statistical evidence of an effect. 

## Limitations and Future Work
* **Heterogeneous Effects:** One key shortcoming is the inability to disaggregate countries by social conditions. More conservative societies may respond to quota adoption very differently than progressive ones; not grouping them likely obscures heterogeneous causal effects, potentially dampening the overall estimate.A granular analysis would involve grouping countries by gender norms before estimating effects. 
* **Data Sparsity:** The data from WDI for female literacy was sparse due to countries reporting it only once every five to ten years. Had this been feasible to include, it would have provided a more holistic view of whether quotas result in development beyond labor participation alone. 

## Technologies Used
* Python (`pandas`, `numpy`)
* `wbgapi` for World Bank Data extraction
* `statsmodels` & `linearmodels` for causal inference and mediation modeling
