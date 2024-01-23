---
title: World University Rankings 2012-2015
image: assets/img/portfolio/flags.png
alt: Python

caption:
  title: World University Rankings 2012-2015
  subtitle: Python
  thumbnail: assets/img/portfolio/flags.png
---



## About the Data

This dataset comes from The Center for World University Rankings (Kaggle), which provides information for top Universities in the World.
There are 14 columns and 2,220 rows of data.

This dataset revolves around the assessment and comparison of universities globally throughout the years 2012-2015.

The data contains multiple columns, both qualitative and quantitative, ranging from nominal, discrete, and continuous variable types.
Tools used: Jupyter Notebook, Python (Numpy, Pandas, Matplotlib, Seaborn), Excel, and PowerPoint.


## Research Questions

There are **two** main questions I would like to answer using this dataset: 
1. The first is to investigate whether higher-ranked universities provide better quality education than lower-ranked universities. 
2. The second is to explore whether higher-ranked universities have a greater number of publications than lower-ranked universities.

## Hypotheses

**Hypothesis 1** -  (Quality of Education): 
*Null Hypothesis (H0)*: There is no significant difference in the quality of education provided by higher-ranked and lower-ranked universities.
*Alternative Hypothesis* (H1): Higher-ranked universities provide better quality education than lower-ranked universities.

**Hypothesis 2** - (Number of Publications):
*Null Hypothesis (H0)*: There is no significant difference in the number of publications between higher-ranked and lower-ranked universities.
*Alternative Hypothesis (H1)*: Higher-ranked universities have a greater number of publications than lower-ranked universities.

## How will the data test the hypotheses?

The data will be used to test the hypotheses in the following ways:
- Statistical analysis to assess the relationship between the number of university publications/quality of education and university ranking.
- Pearson correlation coefficient to check correlation. 
- Independent t-test to check for average differences. 
- Visualizations: scatter plots, histograms, heatmap etc.

## How will the findings be used?Who will find it helpful?

1. University administrators can use the findings to gain insights into their own institution's performance and compare it with other universities worldwide. 
2. Government officials and education policymakers may use the findings to understand the factors that contribute to higher-ranking universities. 
3. Students and their parents may use the rankings and the analysis of different universities to make informed decisions about where to apply for higher education.

## Which features?

Using a heatmap with seaborn, we can determine the relationships between variables.
We can see there are strong relationships between the publication rank and the world rank (0, 92)

<p align="center">
  <br>
  <img src="/assets/img/portfolio/heatmap.png" alt="heatmap" width=600>
</p>

## Hypothesis 1

- The **difference in means**, which is negative and falls within a specific confidence interval, supports the idea that higher-ranked universities might indeed have a better quality of education compared to lower-ranked universities.
- The **Pearson correlation coefficient** of approximately -0.60 suggests a moderate to strong negative linear correlation. This means that as the quality of education increases, the score tends to decrease.
- The very low **p-value** indicates that the observed correlation is statistically significant, providing evidence against the null hypothesis of no correlation.

<p align="center">
  <br>
  <img src="/assets/img/portfolio/cifunction.png" alt="cifunction" width=600>
</p>

<p align="center">
  <br>
  <img src="/assets/img/portfolio/pearson.png" alt="pearson" width=600>
</p>

Given these findings, both the Pearson correlation coefficient and the difference in means at the confidence interval provide evidence that supports the alternative hypothesis (H1). Higher-ranked universities appear to provide better quality education than lower-ranked universities, and there is a negative relationship between the quality of education and the ranking scores.
Overall, we can *reject the null hypothesis* and conclude that there is a statistically significant difference between the two variables being tested.

<p align="center">
  <br>
  <img src="/assets/img/portfolio/quality.png" alt="quality" width=600>
</p>

## Hypothesis 2

- The **difference in means**, which is negative and falls within the confidence interval, goes against the alternative hypothesis (H1), that higher-ranked universities have a greater number of publications. The confidence interval suggests that the difference in the number of publications between higher-ranked and lower-ranked universities is negative, indicating that higher-ranked universities tend to have fewer publications than lower-ranked universities.
- The **Pearson correlation coefficient** of approximately -0.52 has a very low p-value, indicating a statistically significant correlation between the two variables. This suggests a moderate negative relationship between the number of publications and the ranking of universities and implies that as the ranking of universities increases, the number of publications tends to decrease.
- The very low **p-value** indicates that the observed correlation is statistically significant. This means that the observed correlation between the number of publications and university rankings is unlikely to have occurred by chance.

<p align="center">
  <br>
  <img src="/assets/img/portfolio/cifunction2.png" alt="cifunction2" width=600>
</p>

<p align="center">
  <br>
  <img src="/assets/img/portfolio/pearson2.png" alt="pearson2" width=600>
</p>

Given that the calculated difference in means and the correlation coefficient both suggest a negative relationship between university ranking and the number of publications, the results do not support the alternative hypothesis (H1). Higher-ranked universities tend to have a lower number of publications than lower-ranked universities, and there is a negative relationship between the publications and the ranking scores. This conclusion is consistent with both the Pearson correlation coefficient and the calculated difference in means.
Overall, we can *accept the null hypothesis* and conclude that there is a statistically significant difference between the two variables being tested.

<p align="center">
  <br>
  <img src="/assets/img/portfolio/scores.png" alt="scores" width=600>
</p>

## Project Summary

For **Hypothesis #1**, the investigation into the relationship between university ranking scores and the quality of education has shown evidence in favor of the alternative hypothesis (H1). 
- The negative correlation observed between educational quality and ranking scores underlines the significance of a robust education in shaping a university's standing. This robust evidence enables us to confidently reject the null hypothesis, affirming the pivotal role of education quality in the university rankings

Conversely, for **Hypothesis #2**, an analysis between university ranking scores and the number of publications has revealed that from both the calculated difference in means and the Pearson correlation coefficient, evidence reinforces the null hypothesis. 
- This suggests that while the number of publications and university rankings do exhibit a negative correlation, the relationship is complex. 

## Recommendations

**Focus on Quality of Education Alongside Other Factors:**
Although the publications are essential, universities should prioritize providing high-quality education. The analysis showed that world rank and education quality rank are not always directly related. This can be achieved by maintaining rigorous academic standards, investing in faculty development, promoting innovative teaching methods, and continuously assessing and improving educational programs.

**Emphasize the importance of Publications:**
The correlation between publication rank and world rank implies that universities should focus on improving their research output and publications. This can be achieved by investing in research facilities, supporting faculty members in their research, and collaborating with other institutions. 




