---
title: Week 10
---

[HOME](https://arungaonkar.github.io/HPCC-Causality/) **|**
[Timeline](https://arungaonkar.github.io/HPCC-Causality/index.html#timeline) **|**
[Previous Week](https://arungaonkar.github.io/HPCC-Causality/week9.html) **|**
[Next Week](https://arungaonkar.github.io/HPCC-Causality/week11.html)

---

# Monday 07/25

I have continued to analyze the dataset by plotting some more graphs. I thought of including the income variable in the hypothesis. And the diabetes depends on income, the plot is shown below. As the income goes high, the probability of diabetes goes low. They are negatively correlated.

![db_income](imgs/db_income.png)

In terms of causality, it is not clear that, whether diabetes is causing the income or higher income is causing to the cure of diabetes and thereby lower the diabetes. In order to find that, I have to control one variable and find the effect of other variables.

Some correlation between the age and income can be observed in the below plot. Even from bmi vs income and height vs income, the correlation can be found.

![age_income](imgs/age_income.png) ![bmi_income](imgs/bmi_income.png) ![height_income](imgs/height_income.png)

After a discussion with Roger, we were able to draw the following hypothesis model:

![obs2](imgs/obs2.png)

Height and Weight both causes BMI and BMI in turn causes Diabetes. Age is affecting both Height and Weight, and hence the above diagram. The effect of Age on income is not clear. Similarly the height and BMI on Income.

Dotted line indicates between height and income implies that there is a relation but not exactly sure about it. Arrow in the both direction indicates that the direction of relation is not clear.

# Tuesday 07/26

To draw the relationship between income and age, I tried to plot the expectation value of Income conditioned on Age, controlled for different variables. From the following figure we can infer that, there is a direct effect of age on the income.

![income_age](imgs/income_age.png)

To get the directionality between BMI and Age, I followed the same procedure as above.

![bmi_income_combined_part1](imgs/bmi_income_combined_part1.png)
![bmi_income_combined_part2](imgs/bmi_income_combined_part2.png)

My observation from this would be that weight has higher effect on BMI than the height. Controlling for Diabetes and age has no effect on BMI &#124; Income.

# Wednesday 07/27

To find the direction of relation between diabetes and income, I have decided to control one variable and find the effect of other variables.

The probability of diabetes conditioned on income is decreasing as the income increases.

![diabetes_income_combined_part1](imgs/diabetes_income_combined_part1.png)

![diabetes_income_combined_part2](imgs/diabetes_income_combined_part2.png)

From above plots, it is evident enough to draw a conclusive relationship between diabetes and income.

# Thursday 07/28 & Friday 07/29

I have done some more pre-processing for the dataset. such as,

1. I have removed 'unknown' values in variables in maritaldetails, employment etc.

2. Added **physicalactivity** column - yes, no [whether they are having physical activities after regular work hours?]

3. Added **insurance** column - yes, no [Are you enrolled in health coverage plan?]

4. Added **checkup** column - [ About how long it has been since they last visited a doctor for a routine checkup?] Values are : '1-in1-Year', '2-in2-Years', '3-in5-Years', '4-5orMore-Years'

5. Added **nohospitalcost** column - [Was there a time in the past 12 months when you needed to see a doctor but could not because of cost?]  [no, yes]

6. Resampled weight values to nearest 10th values.

After this preprocessing, the dataset is of size 290759 rows with 32 columns.

Some of the observations that I made from statistical analysis are as follows:

Looking at the distribution of variables,

* most of the people have no diabetes (around 87%)

* Most of the people are in the age between 55 and above (around 53%) in ageGroup (5,6)

* 1/3rd of surveyed people are overweight in nature. (around 36%)

* Most of the people in participated in survey are employed (around 44%)

* 37% of the surveyed people have income over 75000 per annum. (around 38%)

Looking at the pairwise relationship of variables with diabetes,

* As the income increased, the effect of conditioning the income on diabetes decreased.

* Students have lesser prone to diabetes, while the retired people and those who are unable to work are having higher chances of diabetes.

* People who are doing physical activity are 3% lesser chance of diabetes, while those who are not doing any physical activity are 9% more prone to diabetes.

* 22% of the people without physical activities are having diabetes.

* When conditioned on Age, the probability of diabetes decreased by 2.5%. And from the graph, they are positively corelated.

* When Conditioned on Weight, the probability of diabetes = yes is increased by 2%.

* The probability of diabetes is not affected by conditioning on Height.

* Diabetes and BMI are positively correlated. As BMI increases, the probability of diabetes increases. Conditioned on BMI, the probability of diabetes decreased by 2.4%

* Diabetes and Income are negatively correlated. As income increases, the probability of diabetes increases. Conditioned on Income, the probability of diabetes decreased by 2.3%

* Students have lesser prone to diabetes, while the retired people and those who are unable to work are having higher chances of diabetes.

* People who are not able to work are having 16% higher chances of diabetes.

* Retired people have 8% higher chances of diabetes.

* 22% of the people who are not doing any physical activities are having diabetes which is 12% more than the people who are doing physical activities.

* Doing physical activity reduces the chance of diabetes by 3%. and not doing it increases it by 9%.

I have also tried to observe the effect these variables on the diabetes.

* Expected Age of the people with diabetes is 64 and for those without diabetes, it is 53.

* The height difference between the people with diabetes and without diabetes is not significant. (0.17 inches)

* People with diabetes weigh 23 pounds more than those without diabetes.

* People with diabetes have higher BMI of 3.8 more than the people without diabetes.

* The difference between the average income of all people and that of average income of people with diabetes is quite significant.(0.7)

* The expected income of people without diabetes is above 50000 per annum.

* Most of the people with the diabetes are retired people, while employees cover most of surveyed people, it is that category of people where diabetes is not expected much.

* Physical activity seems like a biased data. Around 80% of surveyed people said they are doing some type of physical activity.

After that, I started to look at the pairwise conditioned effect of variables on diabetes. And for diabetes conditioned on Age, and the second variable is chosen on the fly, the probability of diabetes is as follows.

![db_ageX](imgs/db_ageX.png)

I have to follow similar approach and observe the effect of conditionalizing to the direct causal effect of variables on diabetes.

---
[HOME](https://arungaonkar.github.io/HPCC-Causality/) **|**
[Timeline](https://arungaonkar.github.io/HPCC-Causality/index.html#timeline) **|**
[Previous Week](https://arungaonkar.github.io/HPCC-Causality/week9.html) **|**
[Next Week](https://arungaonkar.github.io/HPCC-Causality/week11.html)
