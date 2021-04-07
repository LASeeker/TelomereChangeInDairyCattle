# TelomereChangeInDairyCattle
This repo contains data and code discussed in Seeker et al. 2021, "Telomere attrition rates are associated with weather conditions and predict productive lifespan in dairy cattle", Scientific Reports. 

Abstract

Telomere length is predictive of adult health and survival across vertebrate species. However, we currently do not know whether such associations result from among-individual differences in telomere length determined genetically or by early-life environmental conditions, or from differences in the rate of telomere attrition over the course of life that might be affected by environmental conditions. Here, we measured relative leukocyte telomere length (RLTL) multiple times across the entire lifespan of dairy cattle in a research population that is closely monitored for health and milk production and where individuals are predominantly culled in response to health issues. Animals varied in their change in RLTL between subsequent measurements and RLTL shortened more during early life and following hotter summers which are known to cause heat stress in dairy cows. The average amount of telomere attrition calculated over multiple repeat samples of individuals predicted a shorter productive lifespan, suggesting a link between telomere loss and health. TL attrition was a better predictor of when an animal was culled than their average TL or the previously for this population reported significant TL at the age of 1 year. Our present results support the hypothesis that TL is a flexible trait that is affected by environmental factors and that telomere attrition is linked to animal health and survival traits. Change in telomere length may represent a useful biomarker in animal welfare studies.

Full text available here: 
https://www.nature.com/articles/s41598-021-84984-2


# About the data

The main data file containing telomere data is LongTelomereDataCattle.csv 

This dataset includes:\
recoded_id = anonymous animal ID\
dob = date of birth\
birth_year = year of birth\
genetic_group = C for control, S for select\
feed_group = 1 low forage 2 high forage\
amp_305_lactation = average productivity calculated over the first 305 days of lactation (standard in the dairy industry)\
cull_date = date of culling\
cull_reason = reason for culling\
cull_category = summarised reason for culling\
herd_life = days between dob and cull date\
sample_date	= date of blood sampling\
rltl= relative leukocyte telomere length \
tel_sample_no	= number of telomere samples within the animal (is it the first or a follow up sample? numeric 1- maximal sample number)\
residual_rltl_t = rltl corrected for qPCR plate and row\
residual_rltl_tminus1	= rltl corrected for qPCR plate and row at the previous measurement time\
diff_rltl_res	= residual_rltl_tminus1 - residual_rltl_t\
sample_interval = days between sampling \
change_at_t_1	= change in previous sample interval (between rltl at t-1 and rltl at t-2)\
abs_diff_rltl_res = absolute difference in rltl between t and t-1	\
age_d	= age in days at sampling\
age_m	= age in months at sampling\
age_y	= age in years at sampling\
live_wgt = weight in kg\
cond_score = body condition score\
health_event_2week = TRUE/ FALSE for was there any kind of health event recoreded within 2 weeks of blood sampling\
health_event_fertil_all = accumulative number of fertility events. Not all were negative. A confirmed pregnancy or an inseminaton may be recorded as well\	health_event_mastitis_all = accumulative number of mastitis (inflammation of the udder) events	\
health_event_lame_all = accumulative number of lameness events	\
sample_year = year of blood sampling	\
average_resid = mean rltl across all of the animal's rltl measurements\
rltl_change	= mean change in rltl across all of the animal's rltl measurements\
abs_rltl_change	= mean absolute change in rltl across all of the animal's rltl measurements\
AgeGroup = young vs. old\
av_rltl_1_res = rltl at the approximate age of 1 year, corrected for qPCR plate and row\
SamplesPerAnimal = number of telomere measurements per animal\	
Animal_No = another animal identifyer\	
atrr_rate_per_year = rltl change rate per year


I opted for preparing different input data outside of the main .Rmd file to make it less confusing. 

Survival data can be found in cox_data.csv.

The main weather data file is eskdalemuirdata_red_sampleYear.csv.

Datasets were not simply sub-setted but mean lifelong relative leukocyte telomere length) measures (mean RLTL, mean RLTL change, mean absolute RLTL change) had to be calculated again for the subsetted dataset excluding those time points that were not sought to be considered.

