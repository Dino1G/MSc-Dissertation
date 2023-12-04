# A&E Inpatient Clustering Using K-Prototypes for Length of Stay Analysis: A Comparative Study Before and After COVID-19

**Author:** Yi-Chun Huang

**Degree:** Master of Science in Data Science

**Supervisor:** Dr. Nicola Rennie

**School:** School of Computing and Communications, Lancaster University

**Date:** September, 2023

## Abstract

- Explores evolving patterns in A&E inpatient demographics and healthcare utilization in the Wrightington, Wigan and Leigh Teaching Hospitals NHS Foundation Trust (WWL).
- Utilizes K-Prototypes clustering algorithm to examine Length of Stay (LoS) and identifies significant trends affecting healthcare delivery.
- Observes an increase in waiting times and LoS post-pandemic, with a stronger correlation between them.
- Patients tend to cluster around longer waiting times, posing challenges for emergency department throughput.
- Demographic shifts post-pandemic show an increase in average age and comorbidity scores.
- Shift in the dominant Healthcare Resource Group (HRG) Chapter suggests potential long-term effects of COVID-19.
- Calls into question the efficacy of existing acuity code systems and the need for further investigations into healthcare resource management.

## Acknowledgements

- Thanks healthcare professionals at WWL for their unwavering commitment.
- Special thanks to Thomas Ingram and Brian Wood for their guidance and expertise.
- Acknowledges Dr. Nicola Rennie for academic guidance.
- Gratitude to friends and family for their support.

## Contents

- Introduction
- Related Work
- Data
- Methodology
- Results
- Discussion
- Conclusion
- Appendix
- Project Specification
- References

## Introduction

### Company Background

- Wrightington, Wigan and Leigh Teaching Hospitals NHS Foundation Trust (WWL) is a medium-sized emergency and community foundation trust in Greater Manchester.
- WWL serves over 300,000 local residents and extends its expertise regionally, nationally, and internationally.
- The trust comprises multiple specialized medical centers with distinct healthcare domains.
- WWL operates within the framework of the UK's National Health Service (NHS) but as an NHS Foundation Trust, it has a degree of financial and operational independence.

### Research Background

- Recent research at WWL indicates a shift in patient demographics since 2016, characterized by older patients with longer hospital stays.
- There's a notable increase in Length of Stay (LoS) across all age groups, particularly post-COVID-19.
- Extended LoS is associated with worse patient outcomes and increased demand for hospital beds.

### Aims and Objectives

- The primary aim is to examine factors influencing changes in patient Length of Stay (LoS) before and after the COVID-19 pandemic.
- Objectives:
  - Analyze patient characteristics and demographics to identify LoS trends.
  - Evaluate the unique impact of the COVID-19 pandemic on LoS.
  - Use advanced clustering to categorize patients based on multiple variables.
  - Inform operational strategies to optimize bed capacity and patient outcomes in a post-pandemic environment.

## Chapter 2: Related Work

### 2.1 Factors Affecting Length of Stay

- Length of Stay (LoS) is a critical factor in healthcare, impacting resource allocation, patient outcomes, and costs.
- Factors affecting LoS include patient demographics, medical severity, and hospital-specific variables.
- Patient age, comorbidities, and initial illness severity influence LoS, with A&E admissions often resulting in longer stays.
- Hospital characteristics, such as hospital type and nursing staff levels, can also impact LoS.
- Overcrowding in A&E departments can lead to longer LoS and other adverse effects.

### 2.2 Medical Applications of Clustering

- Clustering techniques are increasingly used in healthcare data analytics to categorize patient groups.
- Clustering enables precise medical treatments, reduces patient burdens, and improves healthcare quality.
- Machine learning algorithms, including K-means and DBSCAN, have enhanced clustering in healthcare.
- Machine learning is invaluable in smart healthcare for its predictive utility.

## Chapter 3: Data

### 3.1 Data Collection

- Data collected from WWL is stored in a Qlik Sense environment in .qvd format.
- Four datasets were selected for analysis, including Inpatient Spells, Pathway, Patient Info, and A&E Flow.

### 3.2 Data Integration & Data Creation

- The Inpatient Spells dataset served as the primary table, and other datasets were integrated using unique patient IDs and dates.
- Columns like 'COVID Period' and 'Arrival to Admission (Hrs)' were added to facilitate analysis.

### 3.3 Data Pre-processing

- Data pre-processing involved removing columns with low variability and high missing data.
- Remaining missing entries were handled, and feature selection was performed using correlation analysis and ANOVA.

### 3.4 Redefining Data Type & Feature Selection

- Data type validation ensured appropriate interpretation of variables.
- Feature selection included retaining features with strong correlations to LoS and assessing the impact of categorical features on LoS.

### 3.5 Exploratory Analysis

- Exploratory analysis revealed trends in variables related to LoS.
- Visualizations and statistics provided insights into patient demographics, specialties, and other factors affecting LoS.

## Chapter 4: Methodology

### 4.1 Statistical Analysis: Analysis of Variance (ANOVA)
- Employed ANOVA for initial feature selection and assessing categorical variable impact on LoS.
- ANOVA tests for differences between group means.
- Null hypothesis (H0): Means of different groups are equal; alternative hypothesis (Ha): At least one group mean differs.
- Categorical variables were independent; LoS was dependent.
- Significance level: 0.05
- Analysis conducted using Python's SciPy library.

### 4.2 Correlation Analysis
- Pearson correlation coefficient used to measure linear relationships between continuous variables and LoS.
- Range: -1 (perfect negative correlation) to 1 (perfect positive correlation), 0 implies no linear correlation.
- Suitable for analyzing how continuous variable fluctuations affect LoS.

### 4.3 Clustering Technology

#### 4.3.1 K-Prototypes
- Utilized K-Prototypes algorithm to handle datasets with numeric and categorical attributes.
- Combination of K-Means for numeric attributes and K-Modes for categorical attributes.
- Used Euclidean distance for numeric attributes and matching dissimilarity measure for categorical attributes.
- Algorithm parameters, initialization methods explained.

#### 4.3.2 Pre- and Post-Pandemic Data Clustering
- Established baseline model with pre-pandemic data.
- Applied predefined centroids to post-pandemic data for cluster comparison.
- Aims to identify trends, deviations, and new patterns due to the pandemic.

#### 4.3.3 Evaluation Metric: Sum of Squared Errors (SSE)
- SSE used to assess clustering model performance.
- Measures clustering compactness.
- Determined optimal number of clusters using elbow method.

## Chapter 5: Results

### 5.1 Model Training
- Optimal number of clusters: 5 based on SSE analysis.
- Clear "elbow point" observed in SSE vs. Number of Clusters plot.

### 5.2 Model Outcomes
- Cluster centroids and labels described.
- Shifts in patient characteristics and LoS observed post-pandemic.
- Notable changes in HRG chapter distribution, referral source, and arrival mode discussed.
- Impact on acuity codes and attendance type explained.

### 5.3 Cluster Comparison Before and After COVID-19
- Shift towards clusters with extended waiting times observed post-pandemic.
- Increase in average age and comorbidity scores post-pandemic.
- Musculoskeletal conditions becoming more prevalent in high-LoS clusters.
- Changes in acuity codes and attendance type analyzed.
- Waiting assessment times increased for patients with higher acuity codes post-pandemic.

## Chapter 6: Discussion

In this paper, we conducted a comprehensive analysis of inpatients admitted to the emergency department at Wrightington, Wigan and Leigh Teaching Hospitals NHS Foundation Trust (WWL), both before and after the COVID-19 outbreak, utilizing the K-Prototypes clustering algorithm to scrutinize patient features and behavioral shifts across clusters.

- **Increase in LoS and Waiting Time:** Post-COVID-19, there was a significant increase in both the average Length of Stay (LoS) and waiting times for admission. The relationship between these two variables strengthened. The shift towards clusters characterized by extended waiting times for admission suggests that challenges in the post-outbreak environment may be related more to throughput issues in the emergency department than LoS, supporting the idea that increased LoS results from emergency department overcrowding.

- **Age and Comorbidity:** Post-outbreak data revealed a rise in the average age of patients and comorbidity scores. High-LoS clusters saw an increase in patients with musculoskeletal conditions, potentially indicating the long-term impact of COVID-19 on this domain and an increased demand for healthcare resources.

- **Acuity Codes:** While initial severity of conditions leading to admissions remained relatively stable pre- and post-outbreak, there was a notable increase in patients classified as 'Majors' and a decline in the 'Minors' category across all clusters. This raises questions about the effectiveness of acuity codes in optimizing healthcare resource allocation.

- **Waiting Assessment Times:** Post-outbreak, waiting times for initial patient assessments increased significantly. Patients with higher acuity codes experienced longer waiting times. These observations highlight the need for healthcare management to enhance patient experience and maintain the standard of care.

**Limitations:**
- The application of ANOVA to skewed data might affect result precision, suggesting the use of non-parametric statistical methods in future research.
- Determining the number of clusters based on pre-pandemic data limits the understanding of how the clustering structure evolved due to the pandemic, recommending a re-assessment of cluster numbers in a post-pandemic context.
- The analysis was based on data from a single healthcare trust, limiting generalizability. Multi-center studies could provide more universally applicable insights.

## Chapter 7: Conclusion

This study analyzed A&E inpatient characteristics at WWL hospitals before and after the COVID-19 outbreak, using K-Prototypes clustering to categorize patients by LoS and investigate behavioral shifts.

- **Post-Outbreak Trends:** The study revealed significant post-outbreak trends, including increased LoS, waiting times, patient age, and comorbidity scores. Musculoskeletal conditions became more prevalent in high-LoS clusters.

- **Acuity Codes and Waiting Times:** Acuity codes showed no significant change in initial condition severity, but 'Majors' assignments increased post-outbreak. Waiting times for initial assessments rose substantially.

The study recommends action points for the NHS, including establishing a Rapid Assessment Team, reassessing acuity code criteria, reviewing community support for the elderly, and investing in specialized care for musculoskeletal conditions.

The COVID-19 pandemic has led to operational challenges, demanding adaptations in healthcare processes and resource allocation. These findings contribute to understanding the broader impact of the pandemic on healthcare systems.

## References
[1] Bahrmann, Anke et al. (2019). “The Charlson Comorbidity and Barthel Index predict length of hospital stay, mortality, cardiovascular mortality and rehospitalization in unselected older patients admitted to the emergency department”. In: Aging Clinical and Experimental Research 31, pp. 1233–1242.

[2] Benesty, Jacob, Jingdong Chen, and Yiteng Huang (2008). “On the importance of the Pearson correlation coefficient in noise reduction”. In: IEEE Transactions on Audio, Speech, and Language Processing 16.4, pp. 757–765.

[3] Buttigieg, Sandra C, Lorraine Abela, and Adriana Pace (2018). “Variables affecting hospital length of stay: a scoping review”. In: Journal of health organization and management 32.3, pp. 463–493.

[4] Chaturvedi, Anil, Paul E Green, and J Douglas Caroll (2001). “K-modes clustering”. In: Journal of classification 18, pp. 35–55.

[5] Chudasama, Yogini V, Kamlesh Khunti, and Melanie J Davies (2021). “Clustering of comorbidities”. In: Future Healthcare Journal 8.2, e224.

[6] Cohen, Israel et al. (2009). “Pearson correlation coefficient”. In: Noise reduction in speech processing, pp. 1–4.

[7] Daghistani, Tahani A et al. (2019). “Predictors of in-hospital length of stay among cardiac patients: a machine learning approach”. In: International journal of cardiology 288, pp. 140–147.

[8] El-Darzi, Elia et al. (2009). “Length of stay-based clustering methods for patient grouping”. In: Intelligent patient management, pp. 39–56.

[9] Dickson, Jon M, Suzanne M Mason, and Andy Bailey (2017). “Emergency department diagnostic codes: useful data?” In: Emergency Medicine Journal.

[10] Disser, Nathaniel P et al. (2020). “Musculoskeletal consequences of COVID-19”. In: The Journal of bone and joint surgery. American volume 102.14, p. 1197.

[11] Freitas, Alberto et al. (2012). “Factors influencing hospital high length of stay outliers”. In: BMC health services research 12, pp. 1–10.

[12] Gong, Xuran et al. (2022). “Managing hospital inpatient beds under clustered overflow configuration”. In: Computers & Operations Research 148, p. 106021.

[13] Hartigan, John A and Manchek A Wong (1979). “Algorithm AS 136: A k-means clustering algorithm”. In: Journal of the royal statistical society. series c (applied statistics) 28.1, pp. 100–108.

[14] Hassan, Mahmud et al. (2010). “Hospital length of stay and probability of acquiring infection”. In: International Journal of pharmaceutical and healthcare marketing 4.4, pp. 324–338.

[15] Higgins, Thomas L et al. (2003). “Early indicators of prolonged intensive care unit stay: Impact of illness severity, physician staffing, and pre–intensive care unit length of stay”. In: Critical care medicine 31.1, pp. 45–51.

[16] Huang, Z. (1997). “Clustering Large Data Sets with Mixed Numeric and Categorical Values”. In: Proceedings of the 1st Pacific-Asia Conference on Knowledge Discovery and Data Mining, (PAKDD), pp. 21–34.

[17] Iwase, Shinya et al. (2022). “Prediction algorithm for ICU mortality and length of stay using machine learning”. In: Scientific reports 12.1, p. 12912.

[18] Klein, Rudolf (2004). The first wave of NHS foundation trusts.

[19] Lauks, Juliane et al. (2016). “Medical team evaluation: effect on emergency department waiting time and length of stay”. In: PloS one 11.4, e0154372.

[20] Liu, Yingxin, Mike Phillips, and Jim Codde (2001). “Factors influencing patients’ length of stay”. In: Australian Health Review 24.2, pp. 63–70.

[21] McDermott, Christopher and Gregory N Stock (2007). “Hospital operations and length of stay performance”. In: International Journal of Operations & Production Management 27.9, pp. 1020–1042.

[22] Mentzoni, Ida, Stig Tore Bogstrand, and Kashif Waqar Faiz (2019). “Emergency department crowding and length of stay before and after an increased catchment area”. In: BMC health services research 19, pp. 1–11.

[23] Moisoglou, Ioannis et al. (2019). “Nursing staff and patients’ length of stay”. In: International Journal of Health Care Quality Assurance 32.6, pp. 1004–1012.

[24] Ogbuabor, Godwin and FN Ugwoke (2018). “Clustering algorithm for a healthcare dataset using silhouette score value”. In: Int. J. Comput. Sci. Inf. Technol 10.2, pp. 27–37.

[25] Panchami, VU and N Radhika (2014). “A novel approach for predicting the length of hospital stay with DBSCAN and supervised classification algorithms”. In: The Fifth International Conference on the Applications of Digital Information and Web Technologies (ICADIWT 2014). IEEE, pp. 207–212.

[26] Qualls, Munirih, Daniel J Pallin, and Jeremiah D Schuur (2010). “Parametric versus nonparametric statistical tests: the length of stay example”. In: Academic Emergency Medicine 17.10, pp. 1113–1121.

[27] Quan, Hude et al. (2005). “Coding algorithms for defining comorbidities in ICD-9-CM and ICD-10 administrative data”. In: Medical care, pp. 1130–1139.

[28] Ramani, Santhoshini Leela et al. (2021). “Musculoskeletal involvement of COVID-19: review of imaging”. In: Skeletal radiology 50, pp. 1763–1773.

[29] Salway, RJ et al. (2017). “Emergency department (ED) overcrowding: evidence-based answers to frequently asked questions”. In: Revista Medica Clinica Las Condes 28.2, pp. 213–219.

[30] St, Lars, Svante Wold, et al. (1989). “Analysis of variance (ANOVA)”. In: Chemometrics and intelligent laboratory systems 6.4, pp. 259–272.

[31] Tennison, Imogen et al. (2021). “Health care’s response to climate change: a carbon footprint assessment of the NHS in England”. In: The Lancet Planetary Health 5.2, e84–e92.

[32] Thinsungnoena, Tippaya et al. (2015). “The clustering validity with silhouette and sum of squared errors”. In: learning 3.7.

[33] UK Government (2023). COVID-19 Deaths in the UK. Accessed on: September 1, 2023. url: https://coronavirus.data.gov.uk/details/deaths.

[34] Virtanen, Pauli et al. (2020). “SciPy 1.0: Fundamental Algorithms for Scientific Computing in Python”. In: Nature Methods 17, pp. 261–272. doi: 10.1038/s41592-019-0686-2.

[35] Vos, Nelis J. de (2021). kmodes categorical clustering library. https://github.com/nicodv/ kmodes.

[36] Vranas, Kelly C et al. (2017). “Identifying distinct subgroups of intensive care unit patients: A machine learning approach”. In: Critical care medicine 45.10, p. 1607.
