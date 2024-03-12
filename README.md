# Data Visualization Project 1

## Member

- Dinh Van Thanh
- Nguyen Tiet Nguyen Khoi
- To Ba Son

## Dataset

Dataset name: Educational attainment of young people in English towns.

The dataset we are using comes from [The UK Office for National Statistics](https://www.ons.gov.uk/). It was explored in the July 2023 article ["Why do children and young people in smaller towns do better academically than those in larger towns?"](https://www.ons.gov.uk/peoplepopulationandcommunity/educationandchildcare/articles/whydochildrenandyoungpeopleinsmallertownsdobetteracademicallythanthoseinlargertowns/2023-07-25) which focuses on the educational attainment of young people in English towns. The dataset suggestion is credited to [Andrea Carpignani](https://github.com/acarpignani).

It contains information on various socio-economic indicators, educational outcomes, and demographic characteristics of towns across England. It includes variables such as town name, population, size category, region, coastal indicator, travel-to-work area, job density, income deprivation, university presence, and various educational attainment metrics.

| variable                                                          | class     | description                                                                                                                              |
| :---------------------------------------------------------------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| town11cd                                                          | character | Town/city geography code (2011)                                                                                                          |
| town11nm                                                          | character | Town/city geography name (2011)                                                                                                          |
| population_2011                                                   | numeric   | Measure of the usual resident population in the town/city                                                                                |
| size_flag                                                         | character | Size category of the built-up area or built-up area subdivision based on resident population (from Census 2011)                          |
| rgn11nm                                                           | character | English region name                                                                                                                      |
| coastal                                                           | character | Variable used to describe towns as coastal or non-coastal                                                                                |
| coastal_detailed                                                  | character | Coastal towns split by size and by seaside towns and other coastal (non-seaside) towns                                                   |
| ttwa11cd                                                          | character | Travel-to-work area code (Census 2011 version)                                                                                           |
| ttwa11nm                                                          | character | Travel-to-work area name (Census 2011 version)                                                                                           |
| ttwa_classification                                               | character | Travel to work area classification                                                                                                       |
| job_density_flag                                                  | character | Variable used to describe towns as working, residential or mixed.                                                                        |
| income_flag                                                       | character | Variable used to describe towns as lower income deprivation, mid income deprivation or higher income deprivatio                          |
| university_flag                                                   | character | Variable used to describe whether the town/city has a university                                                                         |
| level4qual_residents35_64_2011                                    | character | Proportion of the town/city residents aged 35-64 with a Level 4 qualification or above.                                                  |
| ks4_2012_2013_counts                                              | numeric   | Count of pupils in the town/city in the 2012/13 Key stage 4 cohort                                                                       |
| key_stage_2_attainment_school_year_2007_to_2008                   | numeric   | Proportion of pupils that achieved level 4 or above (expected level) in key stage 2 in English and Maths in the 2007 to 2008 school year |
| key_stage_4_attainment_school_year_2012_to_2013                   | numeric   | Proportion of pupils that achieved 5 GCSE or more, including English and Maths, with grades A\*-C in the 2012 to 2013 school year        |
| level_2_at_age_18                                                 | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort that achieved level 2 qualifications at the age 18.                             |
| level_3_at_age_18                                                 | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort that achieved level 3 qualifications at the age 18.                             |
| activity_at_age_19_full_time_higher_education                     | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort in full time higher education at the age 19.                                    |
| activity_at_age_19_sustained_further_education                    | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort in sustained further education at the age 19.                                   |
| activity_at_age_19_appprenticeships                               | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort in an apprenticeship at the age 19.                                             |
| activity_at_age_19_employment_with_earnings_above_0               | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort in sustained employment at the age 19.                                          |
| activity_at_age_19_employment_with_earnings_above_10_000          | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort in sustained employment earning £10,000 or above at the age 19.                 |
| activity_at_age_19_out_of_work                                    | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort claiming out-of-work benefits at the age 19.                                    |
| highest_level_qualification_achieved_by_age_22_less_than_level_1  | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort with less than a Level 1 qualification at age 22.                               |
| highest_level_qualification_achieved_by_age_22_level_1_to_level_2 | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort with a level 1 or level 2 qualification at age 22.                              |
| highest_level_qualification_achieved_by_age_22_level_3_to_level_5 | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort with level 3, level 4 or level 5 qualification at age 22.                       |
| highest_level_qualification_achieved_by_age_22_level_6_or_above   | numeric   | Proportion of the town/city's 2012/13 key stage 4 cohort with level 6 or above qualification at age 22.                                  |
| highest_level_qualification_achieved_b_age_22_average_score       | numeric   | Town/city highest qualification average score based on highest levels of qualifications achieved of the 2012/13 KS4 cohort.              |
| education_score                                                   | numeric   | Town/city education score based on attainment levels of the 2012/13 Key stage 4 cohort.                                                  |

## Reason for Choosing the Dataset:

This dataset provides a comprehensive view of the factors influencing educational attainment among young people in English towns. It allows for exploration of how socio-economic conditions, regional characteristics, and other factors contribute to educational outcomes.

In this project, we aim to answer two main questions:

- How do socio-economic factors, such as income deprivation and job density, correlate with the educational outcomes of young people in English towns?
- What are some potential underlying reasons for the observed differences in educational attainment among young people across coastal and non-coastal towns in England?

## Plan for Answering the questions:

**Question 1: How do socio-economic factors, such as income deprivation and job density, correlate with the educational outcomes of young people in English towns?**

- Variables included:
  - Income-related variables: `income_flag`, `population_2011`.
  - Job density: `job_density_flag`.
  - Level of education of residents aged 35-64: `level4qual_residents35_64_2011`
- Additional variables: educational outcomes: `key_stage_2_attainment_school_year_2007_to_2008`, `key_stage_4_attainment_school_year_2012_to_2013`, `highest_level_qualification_achieved_by_age_22_average_score`
- Tentative approach: By creating aggregated variables or perform transformations to analyze the data, we will examine the relationship between educational outcomes and socio-economic factors.

**Question 2: England is known as a country in which coastal towns are considered left behind in socio-economy compared to non-coastal towns. What are some potential underlying reasons for the observed differences in educational attainment among young people across coastal and non-coastal towns in England?**

- Variables included:
  - Coastal indicator: `coastal`
  - Size of the town: `size_flag`
  - Presence of universities: `university_flag`
  - Socio-economic factors: `income_flag`, `job_density_flag`, `population_2011`
  
**Tentative approach**: We'll compare the educational outcomes between coastal and non-coastal towns. Additionally, we'll explore the potential mediating or moderating effects of town size and university presence on the relationship between coastal indicators and educational attainment.

- Some potential approaches are:
  - Box plot and bar plot with comparisons between coastal and non-coastal towns on different attributes including `income_flag`, `job_density_flag`.
  - Data transformation: calculate the income per person based on `income_flag` and `population_2011`, average `education_score` comparison between coastal and non-coastal towns (aggregation).
  - Other plots such as geometry-based plot (if possible), etc. Different visualizations will be tested and applied to this dataset.
