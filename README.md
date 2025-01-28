Gender Disparities in ICU Outcomes

Lyushen (Abraham) Song
Jessica Tong
Ahmed Farid Khan
Asra Ahmed
Abstract
Gender differences in ICU mortality outcomes remain underexplored. This study replicated the French and euRopean Outcome reGistry in Intensive Care Unit (FROG-ICU) study’s findings using the MIMIC-IV database, a U.S.-based cohort of 8,178 ICU patients (46% female, 54% male). The two gendered one-year mortality outcomes were similar with the FROG-ICU study’s findings across unadjusted, adjusted, and propensity-matched analyses. However, a higher 28-day mortality hazard was observed for women in the propensity-matched cohort [HR 1.13 (95% CI 1.05–1.22)], suggesting potential short-term survival disparities for women. Subgroup analyses by age and diagnosis revealed no significant gender-based survival differences. These findings highlight the importance of investigating gender-specific factors influencing ICU outcomes.
Introduction
Healthcare has historically been dominated by men, with male perspectives shaping much of modern medical knowledge and practices. This practice has been deeply ingrained since ancient times, with philosophers like Aristotle marking women as inferior, based on their “anatomical difference to men” (Cleghorn, 2021). Medical research has also disproportionately been focused on male subjects, creating a significant gap in women’s health. In 2019, British journalist Caroline Criado Perez highlighted this issue, stating that “for millennia, medicine has functioned on the assumption that male bodies can represent humanity as a whole.” This bias extends even to preclinical stages, where test animals and cells often tend to be male (Coleman, 2024).

Historically, men and women have experienced different healthcare outcomes. A 2019 of almost 7 million people in Denmark found that women were diagnosed an average of four years later than men for hundreds of different health conditions, with diabetes diagnoses coming 4.5 years after, and cancer being diagnosed in women when they were an average of 2.5 years older (Dunn, 2019). This disparity is particularly pronounced in areas such as pain management, where a 2024 study found that women are 10% less likely than man to have their pain level assessed upon arrival at the hospital, less likely to be given pain medication and experience longer wait times to be seen by a doctor (Tayal and Pompeii et. al., 2024). Healthcare provider bias can contribute to such disparities. Women’s pain is often taken less seriously than men’s, leading to longer wait times for treatment and less aggressive pain management. 

These disparities persist even in critical care settings. In 2012, Mahmood, Edeirawi and Wahidi assessed the relationship between the ICU outcomes and gender for 261,255 ICU patients in the APACHE IV dataset. They found that overall ICU mortality was 7.2% for men, and 7.9% for women. However, after adjusting for various factors like ethnicity and comorbid conditions, there was no significant difference in ICU mortality between genders for those patients that were 50 years or older. Interestingly, for patients under 50, women had a lower adjusted ICU mortality compared to men, with an adjusted odds ratio of 0.83. Another study of patients with severe sepsis and septic shock found that hospital mortality was higher for women (35%) compared to men (33%). After adjusting for baseline characteristics and care processes, women were found to have an 11% higher likelihood of hospital mortality (Pietropaoli, Glance et al., 2012). Another study that compared the crude hospital mortality rates between genders for acute myocardial infarction patients, found results of 14.8%% for women vs. 6.1% for men. After adjusting for age, the difference narrowed down to 14.1% for women vs. 12.83% in men (Milcent, Durand-Zaleski et al., 2007). 
FROG-ICU
Another study that explored the “independent association of gender and long-term survival of ICU patients” was the “French and euRopean Outcome reGistry in Intensive Care Unit” (FROG-ICU) study. It was a “prospective, observational, multi-center cohort designed to investigate the long-term mortality of critically ill adult patients.” The primary endpoint was 1-year mortality after ICU admission of women compared to men, while the secondary endpoint was the 28-day mortality after ICU admission of women compared to men. 
The study consisted of 2087 patients - 726 women and 1361 men. The men and women had similar baseline characteristics, clinical presentations and disease severity. The study found no significant difference between women and men (34.9% vs. 37.9, P = 0.18), and after multivariable adjustment, no difference in the hazard of death was observed [HR 0.99 (95% CI 0.77–1.28)]. However, despite similar characteristics and outcomes, women were underrepresented in the ICU population (only one-third of patients), warranting further investigation into admission practices. 

Considering that the FROG-ICU study was conducted on a relatively small European population, we wanted to see if the results could be generalized to a wider population. Our study aims to replicate this research using a US patient population. The MIMIC-IV database is a comprehensive resource for critical care research, containing data from 299,712 unique individuals, 431,231 hospital admissions and 73,181 unique ICU stays (Johnson & Bulgarelli et. al.). We felt that this extensive dataset would allow for an in-depth analysis of patient characteristics, treatments and outcomes in a US healthcare setting. By comparing our findings with those of the FROG-ICU study, we hope to contribute to a more nuanced understanding of gender disparities in critical care across different healthcare systems and populations.
Materials and Methodology
Study Design
The FROG-ICU study defined their inclusion criteria as a “requirement for invasive mechanical ventilation and/or vasopressor or inotrope drug support for more than 24 h following ICU admission’ (Hollinger & Gayat, et. al.). The study excluded patients that were less than 18 years old, and those that had a severe head injury, brain death or were in a persistent vegetative state. The study also excluded patients that had received an organ transplant in the last 12 months prior to ICU admission, or if they did not have social security coverage. The primary endpoint of the study was 1-year mortality, while the secondary endpoint was 28-day mortality.
For our study, we applied similar inclusion and exclusion criteria to the MIMIC-IV database to ensure comparability with the FROG-ICU study. We utilized ICD-9 codes from the diagnoses_icd table to identify and exclude patients meeting the FROG-ICU exclusion criteria upon ICU admission. Specifically, we filtered out patients with severe head injuries, brain death, persistent vegetative states, and recent organ transplants (within 12 months prior to ICU admission).
We further refined our cohort using the patients table to include only individuals over 18 years of age and those with Medicare or Medicaid insurance, aligning with the FROG-ICU study's social security coverage requirement. To meet the inclusion criteria, we analyzed the procedureevents table to confirm that patients received either invasive mechanical ventilation and/or vasopressor or inotrope drug support for more than 24 hours following ICU admission. 
This approach ensured that our study population closely mirrored that of the FROG-ICU study, allowing for more direct comparisons of outcomes between the two cohorts.
Statistical Analysis
The difference between male and female critically ill patients groups was assessed with Mann–Whitney U-test, and Fisher’s exact test for continuous and categorical variables respectively, as shown in Table 1. The Kaplan-Meier survival curves were plotted for 28 days and 365 days survival. For both Kaplan-Meier plots, there was no significant divergence between the two genders. The log-rank tests indicated that the differences between the two groups’ survivals showed no significance for either of the endpoints.

The Cox-PH was deployed to acquire the hazard ratio. The first model was unadjusted followed by adjusted models with confounding variables of Sequential Organ Failure Assessment (SOFA) score, and Charlson Comorbidity Index (CCI) and The Acute Physiology Score (APS) II. The subgroup analyses were also used to analyze different subgroups for age (below vs. above the median) and three diagnoses (Sepsis, Neurological, and Heart Failure). Each cox regression was tested for and passed the proportional hazard assumption. 
 
The propensity score matching method was deployed to reduce the bias of baseline characteristics for both female and male populations, for both the primary and secondary endpoints. The propensity score matching on gender includes all clinical variables of following: Age, Charlson Comorbidity Index, Acute Physiology Score III (APS III), Hypertension, Diabetes Mellitus, Dyslipidemia, Coronary Heart Disease, Severe Valvular Heart Disease, Chronic Heart Failure, Peripheral Vascular Disease, Prior Stroke, Chronic Obstructive Pulmonary Disease (COPD), Chronic Kidney Disease, Chronic Liver Disease, Active Malignant Tumor, HIV Infection, Invasive Ventilation, Noninvasive Ventilation, Vasopressor Use, Loss of Autonomy, Cognitive Dysfunction, SOFA Slope (Sequential Organ Failure Assessment slope), Median SOFA Score, Standard Deviation of SOFA Score (std_sofa), Admission Temperature (°C), Maximum Heart Rate (24 hours), Arterial pH, Hemoglobin (g/dL), First Glasgow Coma Scale (GCS) Total Score, Blood Urea Nitrogen (BUN, mg/dL), Creatinine (mg/dL), Respiratory Disorder at Admission, Sepsis at Admission, Trauma at Admission, Neurological Disease at Admission, Cardiac Arrest at Admission, Cardiogenic Shock at Admission, Hemorrhagic Shock at Admission, APS III Strata (stratified APS III). The propensity score matching used a one-to-one ratio (one female and one male) with the “nearest neighbor” method. A fixed caliper of 0.2 was applied to match treated and untreated individuals. Only pairs with a propensity score difference ≤ 0.2 were retained. All statistical analyses were performed using the Python environment on Google Cloud.

Figure 1: Kaplan-Meier survival curve for 365 days


Figure 2: Kaplan-Meier survival curve for 28 days
Results
Patient Characteristics during ICU Stay
Our study included a significantly larger sample size (N = 8,178) compared to the FROG-ICU study (N = 2,087). The gender distribution in our cohort was more balanced, with 46% female patients (n = 3,767) and 54% male patients (n = 4,411), in contrast to the FROG-ICU study's 35% female representation. Our study population was also older, with a median age of 69 years (70 for females, 69 for males), compared to the median age of 63 in the FROG-ICU study.
To assess whether different genders in our cohort had similar baseline characteristics, we calculated the Charlson Comorbidity Index, APS III, and SOFA scores. Although the FROG-ICU study used SAPS-II, APS III is slightly more comprehensive as it includes more variables. Aligning with the FROG-ICU study findings, men and women in our study cohort demonstrated comparable baseline characteristics. These similarities extended to age, comorbidity burden, and Charlson Comorbidity Index, as can be seen in Table 1.
 
Both genders had comparable median CCI scores (6.0 for both females and males), with a slight but statistically significant difference (p = 0.035). This suggests that while the comorbidity burden was similar, minor variations existed. The median APS III score was identical for both genders (51.0), with no statistically significant difference (p = 0.987), indicating that disease severity at admission, as measured by this score, was balanced across both genders. The media SOFA score was slightly higher in males (5.0) compared to females (4.0), with a statistically significant difference. This is consistent with findings from other studies that have also reported men as having a higher SOFA score - potentially due to differences in organ dysfunction components like renal and liver function (Zimmerman et al., 2024). Additionally, both genders exhibited similar clinical presentations, including comparable blood pressure, heart rate, use of vasopressors, and mechanical ventilation requirements. Overall, our study’s median SOFA score was lower than that of the FROG-ICU study (8.0), while the median APS III score of 51 was comparable to FROG-ICU’s SAPS II median score of 49.
  
Several comorbidities were much more prevalent in our study. Hypertension was significantly higher (67.1% vs 43.3% in FROG-ICU), as was diabetes (26.9% vs 18.4%), heart failure (42.7% vs 7.3%), and chronic kidney disease (33% vs 11.6%). These differences suggest that our study population had a higher comorbidity burden than the FROG-ICU study. 

The intervention ventilation rates across both studies were similar (84.7% in our study vs 80.3% in FROG-ICU), while vasopressor use was lower in our study (63.4% vs 72.2% in FROG-ICU). Laboratory values also differed, with lower hemoglobin (median 9.5 g/dL vs 10.0 g/dL) and higher creatinine (median 1.1 mg/dL vs 0.84 mg/dL) in our study.

To summarize, our study population appears to be older and have more comorbidities compared to the FROG study.

Table 1: The Mann-Whitney U-test was used to obtain median and P values for continuous variables and Fisher’s exact test was used to obtain percentages for categorical variables

Primary Endpoint Analysis: One-Year Mortality Rate
For the one-year mortality rate, we first fit the data on the Cox Proportional Hazard regression, with gender being the only covariate. As seen in Figure 3, the hazard of death for females compared to males is slightly above one, [HR 1.02, (95% CI 0.96–1.08)], which showcases a similar hazard ratio for females. This means there’s no significant mortality rate difference (54.2% (male) vs. 55.3% (female), p = 0.53). Adjustments were then conducted by adding in multi-covariates: Charlson Comorbidity Index, Acute Physiology Score III, and Sequential Organ Failure Assessment. Similarly, no significant difference in mortality rates was found in this regression due to the p-value showing no significance (52.3% vs. 45.0%,  p = 0.58). 
Similar one-year survival rates were found among the propensity-matched cohorts of 7,534 patients (54.2% vs. 56.4%,  p = 0.20), which contains 3,767 women and 3,767 men. This indicates that the hazard rate for death is similar for both genders [HR 1.04, (95% CI 0.98- 1.11)].

Figure 3: Forest plot for 1-year mortality according to gender.  
Secondary Endpoint Analysis: 28-Day Mortality Rate 
No significant difference in mortality rates was found for 28 days after ICU admission (38.7% vs. 39.9%, p = 1.51). Accordingly, no difference in the death hazard for women compared to men was found [HR 1.03, (95% CI 0.96 - 1.11)]. After multicovariates adjustment, there was still no significant difference between women and men's death hazard rates [HR 0.93, (95% CI 0.46 - 1.88)].   

When looking at the propensity-matched cohort of 7,534 patients, a significantly higher death hazard rate was observed for women within 28 days of their ICU admissions [HR 1.13, (95% CI 1.05 - 1.22)].

Figure 4: Forest plot for 28-day mortality according to gender.   
Subgroup Analysis 
Subgroup analysis was performed on two main subsets: age and diagnosis at ICU admission. As shown in figure 5 and figure 6, a similar trend was observed for the subgroups at both one year and 28 days after ICU admission, with no significant difference in death hazard rates.
 
Figure 5: Forest plots for 1-year and 28-day mortalities according to gender and age.

 
Figure 6: Forest plots for 1-year and 28-day mortalities according to gender and patient diagnosis.
Discussion 
The FROG-ICU study created a roadmap for this study and this paper tried to answer the same question using a dataset from a different geographical location and with different baseline characteristics. One of the challenges with the FROG-ICU study was that women were underrepresented in the ICU population (only one-third of patients). This study consists of 54% male patients (n = 4,347) and 46% female patients (n =3,703), which represents a more balanced study population. Despite having similarities with the FROG-ICU study, this study’s data came from MIMIC-IV, which was collected by Beth Israel Deaconess Medical Center (BIDMC) in Boston, therefore, the patients characteristics were quite different from FROG-ICU. 

There are a few notable differences, such as the study population having an older median age and more patients having comorbidities like hypertension, diabetes, heart failure, and chronic kidney disease. These differences might come from the geographic and lifestyle differences between the U.S. and Europe. This study can be a more appropriate representation of the U.S. patients and be used for clinical research in the U.S.. From the results, there was no significant relationship between gender and one-year-end point across unadjusted, adjusted, and propensity-score matched cohorts. For the secondary end point (28 days), no significant results were found for unadjusted and adjusted Cox-PH, however, a 13% higher death hazard rate was observed for women within 28 days of their ICU admissions [HR 1.13, (95% CI 1.05 - 1.22)]. The purpose of this study was to replicate the FROG-ICU study to see if the results could be generalized to a wider and different population, and to lay groundwork for future work related to gender and ICU mortality. 

Not many studies have been conducted on assessing the impact of gender on long-term ICU outcomes for critically ill patients. In fact, the study performed on the FROG-ICU population is one of the first major studies to conduct such in-depth research into this topic (Hollinger, Gayat, et al. 2019). The results from our study mirror the findings of the FROG-ICU study in 12 of the 15 replicated analyses. There are differences in three analyses as shown in Table 2.
 


FROG-ICU Disparity
MIMIC-IV Disparity
Propensity Score Matched - Secondary Endpoint
Not significant
Significant
Subgroup: Median Age - Primary Endpoint
Significant
Not significant
Subgroup: Median Age - Secondary Endpoint
Significant
Not significant

Table 2: Showcasing the differences between the results from MIMIC-IV and FROG-ICU

The first and most consequential difference is the observance of a significant difference in gender outcomes for 28-day mortality in the propensity-score matched cohort. This cohort was created by matching male and female patients based on 39 confounding factors, so it reduces the bias in the analysis by the greatest amount, as compared to the adjusted and unadjusted cox regressions. As a result, we can infer from our findings that women are less likely than men to survive in the short-term (28 days) after ICU admission. This finding should be qualified by the detail that there are a few non-biological factors (such as socioeconomic differences) that our analysis did not account for. Further research and more data is needed in order to explore this aspect of the mortality outcome difference between the genders. On the other hand, the FROG-ICU study showed a significant relationship for older women compared to older men - with older women more likely to survive than men at both the 28-day mark and the 1-year mark. The reasons for this difference are not clear, but one potential speculation is the difference in median ages (FROG-ICU: 63 years old vs. MIMIC IV: 69 years old) for the patient populations.

Three ICU prognosis scores - (APS III, SOFA, and CCI) were used in the adjusted cox regression. None of these prognosis measures use gender as a factor in their calculation. The results from both the unadjusted regression and the adjusted regression showed no significant differences for mortality outcomes. Consequently, our results further support the exclusion of gender as a factor in the aforementioned calculations.

The MIMIC-IV database, which comprises critical care data for over 70,000 patients admitted to intensive care units at the BIDMC, represents a relatively homogeneous patient population. Such a limitation may affect the external validity of any findings derived solely from MIMIC-IV, as they may not fully generalize to other healthcare settings or geographical regions. The FROG-ICU sample exhibits less balance between the genders than MIMIC-IV. By comparison, the MIMIC-IV cohort’s more equitable representation of male and female patients offers an important advantage, particularly in studies examining gender differences in mortality. Such balance ensures that observed differences in outcomes are less likely to be confounded by skewed gender distributions, ultimately enabling a clearer understanding of how gender may influence critical illness trajectories and improving the applicability of findings to a broader patient population.

When interpreting the results of the subgroup analysis, we must acknowledge that our study population had an older median age (69) compared to the FROG-ICU, and more patients have hypertension, diabetes, heart failure, and chronic kidney disease. As such, these differences can have an impact on the insignificance of the results. 

The study has some limitations. First, this study is based on observational data and therefore cannot prove causation. Second, this data did not include some important covariates such as socio-economic status and patient compliance. Lastly, it was difficult to infer information about pre-planned surgeries from the data, which prevented us from comparing this specific sub-group analysis with the analysis from the FROG-ICU study. 
Conclusion
This study indicates that gender does not significantly impact long-term ICU survival, as we found similar one-year and 28 days mortality rates between men and women in unadjusted, adjusted, and PSM cohort analyses. However, a slightly higher short-term mortality hazard for women was observed within 28 days post ICU in propensity-matched cohorts. Further research is needed to continue exploring if there is a causal relationship between gender and short term ICU survival. 
References
Cleghorn, E. (2021). Medical myths about gender roles go back to Ancient Greece. Women are still paying the price today. Time. https://time.com/6074224/gender-medicine-bias/

Criado Perez, C. (2019). Invisible women: Exposing data bias in a world designed for men. Chatto & Windus.

Coleman, T. (2024, August 16). Gender bias in medical research: how women are still overlooked. The Week. https://theweek.com/health/gender-bias-medical-research-women

Dunn, L. (2019, May 22). Women are diagnosed years later than men for same diseases, study finds. NBC News. https://www.nbcnews.com/health/health-news/women-are-diagnosed-years-later-men-same-diseases-study-finds-n987216

Tayal U, Pompei G, Wilkinson I, et al. (2024). Advancing the access to cardiovascular diagnosis and treatment among women with cardiovascular disease: a joint British Cardiovascular Societies’ consensus document. Heart.110:e4.

Mahmood, K., Eldeirawi, K., & Wahidi, M. M. (2012). Association of gender with outcomes in critically ill patients. Critical Care, 16(3), R92.

Pietropaoli, A. P., Glance, L. G., Oakes, D., & Fisher, S. G. (2010). Gender differences in mortality in patients with severe sepsis or septic shock. Gender medicine, 7(5), 422–437. https://doi.org/10.1016/j.genm.2010.09.005

Milcent, C., Dormont, B., Durand-Zaleski, I., & Steg, P. G. (2007). Gender differences in hospital mortality and use of percutaneous coronary intervention in acute myocardial infarction. Circulation, 115(7), 833-839. https://doi.org/10.1161/CIRCULATIONAHA.106.664979

Johnson, A., Bulgarelli, L., Pollard, T., Horng, S., Celi, L. A., & Mark, R. (2023). MIMIC-IV (version 2.2). PhysioNet. https://doi.org/10.13026/6mm1-ek67.

Hollinger, A., Gayat, E., Féliot, E., Paugam-Burtz, C., Fournier, M.-C., Duranteau, J., Lefrant, J.-Y., Leone, M., Jaber, S., Mebazaa, A., Arrigo, M., Cariou, A., Deye, N., Duranteau, J., Guidet, B., Jaber, S., Jacob, L., Lefrant, J.-Y., Leone, M., … Wolff, M. (2019). Gender and survival of critically ill patients: Results from the FROG-ICU study. Annals of Intensive Care, 9(1). https://doi.org/10.1186/s13613-019-0514-y
