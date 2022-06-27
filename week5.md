---
title: Week 5
---

[HOME](https://arungaonkar.github.io/HPCC-Causality/) |
[Timeline](https://arungaonkar.github.io/HPCC-Causality/index.html#timeline) |
[Previous Week](https://arungaonkar.github.io/HPCC-Causality/week4.html) |
[Next Week](https://arungaonkar.github.io/HPCC-Causality/week6.html)

---

# Monday 06/20

A fantastic morning to start with. In a meeting with Roger and Gordon, we discussed how to visualize the graphs. We have also discussed on Observable JavaScript and ECL notebook and visualizing graphs there. After that meeting, Roger and I have decided to for the time being, let's focus on only type of house in the 'housing' dataset and continue the analysis. To convert the 'Type' of housing dataset to numeric data format, Roger suggested me to use LabelEncoder from ML_Core. I have reported the error that I have faced in 'ContinuousTest.ecl' of HPCC_Causality bundle.

I have started analyzing the probability distribution and dependency of variables in the 'housing' dataset. I have found that 75% of the *house*s have the price in the range from $500-$1700. And only 4% of the houses lie in the range from $3000-$10000. Some of the probability observations have been made.

Expectation Value testing:

![HousingProbE](imgs/HousingProbE.png)

Some Probability and conditional probability observations have been made.
![HousingProbP](imgs/HousingProbP.png)

And I am unable to visualize the probability distribution of variables.

# Tuesday 06/21

I have continued to analyze the dependency of variables in the 'housing' dataset. For the dependency testing between *price* and *sqfeet*, the execution took 3hr35mins. Other variables like, *Beds* and *Baths* are found to be highly dependent on each other with the confidence of *0.99*. *Bath* and *Beds* are dependent on *sqfeet* as well with the confidence of 0.63 and 0.59 respectively.

After that I have tried Independence testing for each variable respectively which took about 4 hrs. to complete. And result says that all are dependent on each other.

# Wednesday 06/22

I have asked Roger that why dependence test and independence test is taking longer time. Then we decided to debug the issue in python. We resolved the issue by making some changes in the *because* module.

After that I have done the conditional independence testing, where I have chosen one variable for conditioning. Looking at the results I have made 2 inferences.

Since *price* and *baths* conditionally independent given sqfeet, it has to follow either *chain* model or *inverted V* model as shown.

![HousingInf1](imgs/HousingInf1.png)

Similarly for *beds* and *baths* conditioned on *sqfeet*.

![HousingInf2](imgs/HousingInf2.png)

A conflict in the conditional independence results have been found.

1. *beds* and *price* are independent given *sqfeet*. [confidence is 0.054]
2. *price* and *beds* are dependent given *sqfeet*. [confidence is 0.589]

In this case how to draw conclusions from the results?

# Thursday 06/23

I have tested the dataset for conditional independence and found these results. Using 'prob' test methods,  I found that there is no symmetry in the results. 

![HousingCondDepTest](imgs/HousingCondDepTest.png)

This was the updated inference from the above table.

![HousingInf3](imgs/HousingInf3.png)

Conditionally (A, B | C) should be same as (B, A | C), this was violated in the conditional dependency tests. So In the team meeting, it was discussed, and later we pair programmed to add the 'rcot' testing method to the HPCC_Causality bundle. We faced a issue, in *because* module, which was asked Zheyu to solve it.

I have raised a Pull request to the HPCC_Causality bundle for including the *rcot* method for testing conditionality dependencies.

# Friday 06/24

I have tested conditionality dependencies using *rcot* method and found out the following results.

![HousingCondDepTestRcot](imgs/HousingCondDepTestRcot.png)

I have tested conditionality independencies for variables of housing dataset conditioned on 2 variables using both *prob* and *rcot* methods. I have found some interesting results like, both methods are giving different results for few queries.

Using *rcot* method I have found that all are dependent but using *prob* method few are not.

---

[HOME](https://arungaonkar.github.io/HPCC-Causality/) |
[Timeline](https://arungaonkar.github.io/HPCC-Causality/index.html#timeline) |
[Previous Week](https://arungaonkar.github.io/HPCC-Causality/week4.html) |
[Next Week](https://arungaonkar.github.io/HPCC-Causality/week6.html)
