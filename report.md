# Report

## Introduction

In educational research, understanding the disparities in academic achievement between children and young people residing in different town sizes has been a longstanding inquiry. This project seeks to address the question: why do children and young people in smaller towns tend to exhibit better academic performance compared to those in larger towns?

To unravel this phenomenon, we utilize a comprehensive dataset derived from the Longitudinal Education Outcomes (LEO) collected by the Department for Education (DfE). This dataset encapsulates various demographic and educational variables pertinent to understanding educational attainment across different towns and cities in England.

Key variables in the dataset include town geography codes, population size, regional classifications, coastal status, travel-to-work area classifications, and indicators of income deprivation. Additionally, educational metrics such as key stage attainment levels, proportions of pupils achieving specific qualifications, and post-education activities are included.

By analyzing these variables, we aim to shed light on the intricate relationship between town characteristics, socioeconomic factors, and educational outcomes. Through this exploration, we endeavor to provide insights into the factors contributing to the observed differences in academic achievement across town sizes.

## Question 1: How do the patterns of educational attainment among young people in English towns vary based on the types of activities they engage in at age 19, and what role do socio-economic factors play in shaping these patterns?

### Introduction

By delving into the variation of the educational attainment among young people in different English towns and socio-economic situations, this question has the potential to unravel the dynamics shaping of the educational activities. In reality, it is clear that the activities that people perform will podisparitiessitively or negatively influence the quality of the education attainment, indicating that examining how different activities such as full-time higher education or employment will affect the educational outcomes can provide us insights into the diverse pathways of individuals. Furthermore, the socio-economic factors such as income levels and job density also play a crucial role in analyzing the systematic barriers and opportunities that young people may encounter. Understanding these patterns not only help us to come up with countermeasure strategies to support educational attainments but also highlight the areas for targeted intervention to reduce disparities and foster educational environments where all individuals can thrive and reach their full potential.

### Approach for the correlation of students activities and educational attainments

The underlying purpose of this questions is aimed to understand the correlation between the activities of students and the overall educational attainments. In the dataset, there are certain activities that are recorded based on the proportion of students in the town performing those activities. For this questions, the variables regarding activities that we chose to consider are `activity_at_age_19_full_time_higher_education`, `activity_at_age_19_out_of_work`, `activity_at_age_19_employment_with_earnings_above_10_000`.

- For the "Activity at Age 19: Full-Time Higher Education", it is clear that higher education is a significant milestone for many young people and can have a profound impact on their future opportunities and socio-economic status. Understanding the factors influencing participation in higher education can shed light on disparities in access and opportunities among different demographic groups within English towns.
- Being out of work at age 19 can have implications for an individual's economic well-being, social integration, and long-term prospects. Therefore, we believe that examining the proportion of young people who are out of work at age 19 allows for an assessment of youth unemployment rates and potential challenges in transitioning from education to employment.
- The "Activity at Age 19: Employment with Earnings Above £10,000" allows us to discover a specific threshold for employment earnings, offering insights into the financial stability and economic self-sufficiency of young people. Understanding the relationship between employment earnings and educational attainment can reveal patterns of social mobility and economic inequality within English towns.

In order to analyze the activities record efficiently, there are some certain evaluations features regarding educational attainments that we could process, such as Proportion of pupils that achieved level 4 or above (expected level) in key stage 2 in English and Maths in the 2007 to 2008 school year, or the proportion of pupils that achieved 5 GCSE. As the main target of the question lies on the students at the age 19, we decided to choose `level_3_at_age_18` as the measure to evalute the educational attainments. Typically, at age 18, individuals complete their secondary education and may pursue further qualifications such as A-levels or vocational diplomas, which are classified as Level 3 qualifications in the UK education system. By examining the proportion of young people in English towns who achieve Level 3 qualifications at age 18, we gain insights into their academic achievements and preparedness for higher education or the workforce.

Additionally, to further see the trends of the educational attainments between various towns without any certain bias, we will add facet to our visualization, categorizing the towns to different sizes. By this way, we will clearly see the affects of students activities without any coincidences with the characteristics of other variables.

For the type of chart, we decided to use scatter plot. As the main part of the question is to analyze the correlation between two entities, representing the data in the points format could help us gain the insight quickly.

### Analysis

First let's examine the effect of the activities of pursuing full time higher educations on educational attainments. We will first draw the chart:

```{r}
library(ggplot2)

ggplot(data, aes(x = level_3_at_age_18,
                           y = activity_at_age_19_full_time_higher_education)) +
  geom_point(color = "steelblue") +
  facet_wrap(~size_flag) +
  labs(title = "Educational Attainment vs. Activities at Age 19",
       x = "Key Stage 4 Attainment",
       y = "Proportion in Full-time Higher Education") +
  theme_minimal()
```

![Screenshot 2024-04-09 at 22 43 56](https://github.com/clarissdev/data-visualization-project-1/assets/110231356/94dcbfcc-1473-4edc-973b-d07d84f09776)

In the images above, we could clearly see the pattern. Except the city and the BUAs that we do not have enough evidences to conclude the trend, generally, there is a positive correlation between Key Stage 4 attainment and the proportion of young people in full-time higher education, as indicated by the upward trend of the data points. It is clear that the higher educational attainments at the age 2012/13 is closely proportional to the proportion of the town/city's 2012/13 key stage 4 cohort in full time higher education at the age 19.

In constrast, we can see an opposite trend in the proportion in Full-time Out Of Work

```{r}
ggplot(data, aes(x = level_3_at_age_18,
                           y = activity_at_age_19_out_of_work)) +
  geom_point(color = "steelblue") +
  facet_wrap(~size_flag) +
  labs(title = "Educational Attainment vs. Activities",
       x = "Proportion of pupils achieving level 3 at age 18",
       y = "Proportion in Full-time Out Of Work") +
  theme_minimal()
```

![Screenshot 2024-04-09 at 22 41 37](https://github.com/clarissdev/data-visualization-project-1/assets/110231356/7033cf2f-679c-4a42-8a0a-c0c40d810b54)

There appears to be a negative correlation between the proportion of young people in full-time employment (out of work) at age 19 and the proportion of pupils achieving Level 3 at age 18, as indicated by the downward trend of the data points in most town types.

Finally, we could analyze the correlation of the students earning more than £10000 at the age 19.

```{r}
ggplot(data, aes(x = level_3_at_age_18,
                           y = activity_at_age_19_employment_with_earnings_above_10_000)) +
  geom_point(color = "steelblue") +
  facet_wrap(~size_flag) +
  labs(title = "Educational Attainment vs. Activities",
       x = "Proportion of pupils achieving level 3 at age 18",
       y = "Proportion in Full-time Out Of Work") +
  theme_minimal()
```

![Screenshot 2024-04-09 at 22 42 04](https://github.com/clarissdev/data-visualization-project-1/assets/110231356/5a840fdc-cb71-4321-8330-f010e128d0dd)

There appears to be a slight negative correlation between the proportion of young people earning more than £10000 at age 19 and the proportion of pupils achieving Level 3 at age 18 across most town types. This suggests that areas with higher rates of youth unemployment tend to have lower educational attainment levels at age 18.

### Approach for socio-economic factors

For the second part of the question, we focus on addressing the correlation of the socio-economic to the educational attainments of students. In this project, we focus on two areas of socio-economic that we believe it could matters: income flag and town sizes.

In order to measure the attainment score, since we are not focusing specifically on the students at age of 19, we need the measure to be closely related to the overall evaluation of the town. Therefore, the `education_score` is the variable that we chose.

For the purpose of visualization, we decided to use strip chart and box plot. In this case, the entity that we take into account is only the socio-economic factor(income flag or town sizes). Therefore, a proper distribution of the data crucial to measure the central tendency, spread, and variability. While box plots summarize data using summary statistics such as quartiles and outliers, strip charts display individual data points along an axis. Both techniques allow for the visualization of individual observations within the dataset.

### Analysis

First we have to analyze the income flag regarding the overall education score.

```{r}
filtered_data <- data[data$income_flag %in% c("Higher deprivation towns", "Mid deprivation towns", "Lower deprivation towns"), ]

ggplot(filtered_data, aes(x = income_flag, y = education_score)) +
  geom_boxplot() +
  labs(x = "Income Flag", y = "Education Score") +
  ggtitle("Key Stage 4 Attainment by Income Flag")
```

![Screenshot 2024-04-09 at 22 42 23](https://github.com/clarissdev/data-visualization-project-1/assets/110231356/06160b57-fc97-4acb-affb-2f1a76299b68)

The box plot categorizes towns into three groups based on income deprivation levels: Higher deprivation towns, Lower deprivation towns, and Mid deprivation towns. These categories provide insights into how educational attainment varies across different socio-economic conditions. There are several intepretations from the chart:

- At the first look, we can clearly see that the median of educational score of the lower deprivation towns is the highest, followed by mid deprivation towns, and higher deprivation town.
- The variance of the lower deprivation towns is higher compared to mid deprivation towns and higher deprivation towns. This could be a result of the fact that the number of lower deprivation towns is much larger compared to higher and mid deprivation towns.

From the chart, we can conclude that the lower deprivation, the better the educational score is.

For the town size, we have a similar approach with strip chart.

```{r}
# Filter the data for the selected town size categories
data_filtered <- subset(data, size_flag %in% c("Small Towns", "Medium Towns", "Large Towns"))

# Calculate average educational score for each town size category
average_scores <- data_filtered %>%
  group_by(size_flag) %>%
  summarise(avg_education_score = mean(education_score, na.rm = TRUE))

# Plot the jitter plot with average line segments and annotations
ggplot(
  data_filtered,
  aes(x = size_flag, y = education_score)
) +
  geom_jitter(alpha = 0.5, color = "steelblue") +
  geom_segment(data = average_scores,
               aes(x = as.numeric(factor(size_flag)) - 0.5, y = avg_education_score,
                   xend = as.numeric(factor(size_flag)) + 0.5, yend = avg_education_score),
              size = 0.5) +
  annotate("text", x = 0.4, y = -6.2,
           label = paste("Average Attainment Score"),
           size = 3, hjust = -0.2) +
  geom_segment(aes(x = 0.55, xend = 0.55, y = -5.5, yend = average_scores$avg_education_score[1]),
               arrow = arrow(type = "closed", length = unit(0.1, "inches")), size = 0.1) +
  labs(
    x = "Town Size Category", y = "Attainment Score",
    title = "Educational Attainments in different town sizes"
  ) +
  theme(axis.text.x = element_text(hjust = 1))
```

![Screenshot 2024-04-09 at 22 42 47](https://github.com/clarissdev/data-visualization-project-1/assets/110231356/7014aa6d-ec8e-4ffe-aba7-6cfbd07a95ec)

The scatter plot categorizes towns into three groups based on their size: Large Towns, Medium Towns, and Small Towns. These categories provide insights into how educational attainment varies across different town sizes. The scatter plot displays individual data points for each town, allowing for a visual assessment of the distribution of educational attainment scores within each town size category. The spread of data points provides information about the variability in educational attainment across towns of different sizes. The horizontal line across the plot represents the average attainment score across all towns included in the analysis. This line serves as a reference point for comparing the educational attainment scores of individual towns to the overall average.

There are certain intepretations that we can draw from the visualization:

- In average, the attainment score of small towns is largest, followed by medium towns and large towns.
- The variance of small towns seems to be largest, followed by medium towns and large towns. This also helps to indicate that the number of small towns are much larger compared to medium towns and large towns.
- Only the small towns has average educational score above 0, in contrast to the large towns and medium towns.

In conclusion, we can conclude that smaller towns have better attainment.

## Question 2: England is known as a country in which coastal towns are considered left behind in socio-economy compared to non-coastal towns. What are some potential underlying reasons for the observed differences in educational attainment among young people across coastal and non-coastal towns in England?

![image](https://github.com/clarissdev/data-visualization-project-1/assets/53163183/614861eb-3d50-4908-b3dd-a09e9917b739)

This box plot visualizes the comparison of educational scores across three categories of towns: coastal, non-coastal, and those with unspecified status (NA). The plot shows the median, interquartile range (IQR), and outliers for educational scores in each category. Through this, we can observe that:

- The median educational score for non-coastal towns is above that of coastal towns, suggesting that, on average, non-coastal towns have higher educational attainment.

- The spread of scores, as indicated by the IQR (the box), is larger for non-coastal towns than for coastal towns, implying more variability in the educational outcomes for non-coastal towns.

- Both coastal and non-coastal towns have outliers, which are the data points displayed as individual dots outside the whiskers of the box plot. These outliers indicate towns with exceptionally high or low educational scores compared to the rest of their group.

Overall, this visualization highlights potential disparities in educational attainment between coastal and non-coastal towns, with non-coastal towns appearing to have a higher median educational score. However, the presence of outliers suggests there are exceptions to the general trend. These insights can help guide further investigation into the factors contributing to these differences, such as economic opportunities, access to educational resources, and other socio-economic factors specific to coastal and non-coastal regions.

![image](https://github.com/clarissdev/data-visualization-project-1/assets/53163183/3be673c7-9ed9-4073-bdd9-0d7f627affc8)

This violin plot illustrates the distribution of education scores across three job density categories—Mixed, Residential, and Working—for both coastal and non-coastal towns. From this plot, we can see that:

- Width of Violins: The width of each violin represents the density of data points at different education score levels. Wider sections of the violin indicate a higher concentration of towns with similar education scores.

- Distribution Shape: The shape of the violins for the coastal towns is quite distinct from those of the non-coastal towns. Coastal towns appear to have a narrower distribution, especially in the 'Mixed' and 'Working' job density categories, suggesting less variability in education scores compared to non-coastal towns.

- Education Score Range: Both coastal and non-coastal towns show a wide range of education scores, as evidenced by the length of the violins, but non-coastal towns seem to have a slightly broader range, implying more variation in education outcomes.

Comparing Coastal vs. Non-Coastal education scores, we can also observe additional insights:

- In the 'Mixed' category, coastal towns have a more pronounced peak around the lower end of the education score spectrum, while non-coastal towns have a more even distribution.

- In the 'Residential' category, both town types show similar patterns, but non-coastal towns have a slightly higher density of scores in the middle range.

- In the 'Working' category, non-coastal towns show a peak at a higher education score level than coastal towns.

This visualization would be valuable for stakeholders interested in the relationship between economic activity (as indicated by job density) and educational attainment, potentially informing targeted interventions in areas with lower education scores. We can see that the overall spread and central density of education scores are visibly different between coastal and non-coastal towns across the job density categories. There may be an underlying relationship between job density and education scores that varies with coastal status, which could be influenced by various factors such as the availability of educational resources, economic opportunities, or demographic characteristics. This plot suggests that, in general, non-coastal towns may have a more varied educational performance compared to coastal towns, but further analysis would be needed to understand the causes and implications of these patterns.

## Conclusion

In conclusion, there are certain insights we have gained from analyzing the dataset to answer the two questions. From the correlation between activities and the educational attainments, the educational institutions could take into account the ones that are beneficial to educational outcomes. The correlation regarding socio-economic factors (income flag, town sizes) also play a crucial roles in shaping the educational outcomes, helping the large and higher deprivation towns realizing the areas to improve. Finally, non-coastal towns might exhibit a more diverse range of educational outcomes in contrast to coastal towns. Understanding these difference can promote further research to improve this inequality.
