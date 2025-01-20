# PowerBI-Healthcare-Data-Analysis

I'm excited to share my latest data analysis project where I analyzed data related to the Healthcare domain for duration 1990 to 2019.

I'm excited to share my latest data analysis project where I analyzed data related to the Healthcare domain for duration 1990 to 2019.
 KEY FINDINGS:
•	2019 had the highest total of deaths and was 24.89% higher than 1990. 2019 accounted for 3.70% of the sum of total deaths.
•	The top 5 causes of death are cardiovascular disease, Neoplasm, Chronic Respiratory, Lower respiratory & Neonatal disorders which are related to lifestyle, genetic and chronic disorders.
•	The result of grouping and analyzing the data based on natural and sudden deaths shows Natural Deaths are 94.65% whereas sudden deaths are 5.35% of total deaths. Natural deaths increasing every year and there is a decline in the sudden death rate by 25.7%.  
•	Grouping is based on natural deaths (typically due to disease processes) and sudden deaths (often due to acute conditions, injuries, or external factors), and classified them as follows:
o	Natural Death (Typically Due to Disease Processes):
	Cardiovascular diseases
	Neoplasms (cancers)
	Chronic respiratory diseases
	Diabetes mellitus
	Alzheimer's disease and other dementias
	Chronic kidney disease
	Parkinson's disease
	Cirrhosis and other chronic liver diseases
	Alcohol use disorders
	Drug use disorders
	Tuberculosis
	HIV/AIDS
	Malaria
	Lower respiratory infections
	Meningitis
	Acute hepatitis
	Nutritional deficiencies
	Protein-energy malnutrition
	Maternal disorders
	Neonatal disorders
	Digestive diseases
	Diarrheal diseases
o	Sudden Death (Often Due to Acute Conditions, Injuries, or External Factors)
	Road injuries
	Self-harm
	Interpersonal violence
	Drowning
	Poisonings
	Fire, heat, and hot substances
	Conflict and terrorism
	Environmental heat and cold exposure
	Exposure to forces of nature
•	Compared to other countries Germany’s total number of deaths reduced in the 2000-2010 period. The reasons could be: 
o	 Public Health Policies: Effective public health policies and initiatives, including vaccination programs, health education, and preventive measures, helped reduce the incidence of diseases and improve overall public health.
o	 Aging Population Structure: While Germany has an ageing population, the age structure during this period might have been such that the largest cohorts had not yet reached the ages with the highest mortality rates. This demographic shift could temporarily reduce the number of deaths.
o	Environmental Factors: Improvements in environmental conditions, such as better air quality and reduced pollution, contributed to fewer health issues related to environmental factors.
•	All the countries are making good efforts to reduce the numbers of sudden deaths. Where external factors play a major role.
•	Maximum total numbers of deaths due to exposure to nature can observed in Asian countries like Indonesia, Bangladesh, Myanmar & China.
•	For deaths because of drug use disorders USA is at top by 38.47% lead by China at 34.62%.
•	A major concern for India is a disease related to the liver and lung.
Measures:
1.	NaturalDeath% = DIVIDE(SUM('Annual Deaths'[Natural Death]), SUM('Annual Deaths'[Total Deaths]))
2.	SuddenDeath% = DIVIDE(SUM('Annual Deaths'[Sudden Death]), SUM('Annual Deaths'[Total Deaths]))
3.	Cardiovascular diseases = CALCULATE(SUM('Annual Deaths'[ Cardiovascular diseases]))
4.	Chronic respiratory diseases = CALCULATE(SUM('Annual Deaths'[ Chronic respiratory diseases]))
5.	Lower respiratory infections = CALCULATE(SUM('Annual Deaths'[ Lower respiratory infections]))
6.	Neonatal disorders = CALCULATE(SUM('Annual Deaths'[ Neonatal disorders]))
7.	Neoplasms = CALCULATE(SUM('Annual Deaths'[ Neoplasms]))
8.	Total deaths = Table.RenameColumns(#"Sorted Rows1",{{" Poisonings", "Poisonings"}})
9.	Natural Death= Table.AddColumn(#"Sorted Rows", "Natural Death", each List.Sum({ [#" Meningitis"], [#" Alzheimer's disease and other dementias"], [#" Parkinson's disease"], [#" Nutritional deficiencies"], [#" Malaria"], [#" Maternal disorders"], [#" HIV/AIDS"], [#" Drug use disorders"], [#" Tuberculosis"], [#" Cardiovascular diseases"], [#" Lower respiratory infections"], [#" Neonatal disorders"], [#" Alcohol use disorders"], [#" Diarrheal diseases"], [#" Neoplasms"], [#" Diabetes mellitus"], [#" Chronic kidney disease"], [#" Protein-energy malnutrition"], [#" Chronic respiratory diseases"], [#" Cirrhosis and other chronic liver diseases"], [#" Digestive diseases"], [#" Acute hepatitis"]}), Int64.Type)
10.	Sudden Death = Table.AddColumn(#"Inserted Sum", "Sudden Death", each List.Sum({[#" Drowning"], [#" Interpersonal violence"], [#" Self-harm"], [#" Exposure to forces of nature"], [#" Environmental heat and cold exposure"], [#" Conflict and terrorism"], [#" Poisonings"], [#" Road injuries"], [#" Fire, heat, and hot substances"]}), Int64.Type)
