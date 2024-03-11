# Data Visualization Project 1

## Dataset

Dataset name: Educational attainment of young people in English towns.

The dataset we are using comes from [The UK Office for National Statistics](https://www.ons.gov.uk/). It was explored in the July 2023 article ["Why do children and young people in smaller towns do better academically than those in larger towns?"](https://www.ons.gov.uk/peoplepopulationandcommunity/educationandchildcare/articles/whydochildrenandyoungpeopleinsmallertownsdobetteracademicallythanthoseinlargertowns/2023-07-25) which focuses on the educational attainment of young people in English towns. The dataset suggestion is credited to [Andrea Carpignani](https://github.com/acarpignani).

It contains information on various socio-economic indicators, educational outcomes, and demographic characteristics of towns across England. It includes variables such as town name, population, size category, region, coastal indicator, travel-to-work area, job density, income deprivation, university presence, and various educational attainment metrics.

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

**Question 2: What are some potential underlying reasons for the observed differences in educational attainment among young people across coastal and non-coastal towns in England?**

- Variables included:
  - Coastal indicator: `coastal`
  - Size of the town: `size_flag`
  - Presence of universities: `university_flag`
  - Socio-economic factors: `income_flag`, `job_density_flag`, `population_2011`
- Tentative approach: We'll compare the educational outcomes between coastal and non-coastal towns. Additionally, we'll explore potential mediating or moderating effects of town size and university presence on the relationship between coastal indicator and educational attainment.
