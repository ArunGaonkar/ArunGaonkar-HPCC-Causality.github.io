---
title: Week 12
---

[HOME](https://arungaonkar.github.io/HPCC-Causality/) **|**
[Timeline](https://arungaonkar.github.io/HPCC-Causality/index.html#timeline) **|**
[Previous Week](https://arungaonkar.github.io/HPCC-Causality/week11.html) **|**
[Next Week](https://arungaonkar.github.io/HPCC-Causality/week13.html)

---

# Monday 08/08 & Tuesday 08/09

I made slides for the presentation and worked on finalizing it. After receiving the feedback from my mentor Roger, I incorporated those suggestions. I also did a few trials before presenting to the entire team of HPCC Systems on Tuesday. In the presentation, I talked about how I progressed in this internship. I also included the importance of the causality toolkit and how it can be applied to other problems. I spoke about how I applied the causality toolkit to the real-world datasets and ran briefly through a sample causal analysis of the dataset. It was a nice experience presenting to the team. Presentation slides can be found [here](https://arungaonkar.github.io/HPCC-Causality/Applying%20Causality%20toolkit%20to%20Real-world%20datasets.pdf).

# Wednesday 08/10 & Thursday 08/11

I had my final evaluation of my internship on this day. I was very happy with the work done by the team. The feedback from Lorraine and Roger was positive.

After that, I started to work on the model reduction part of the LLCP analysis.

# Friday 08/12

I applied the causality toolkit 'Because' to the Housing Dataset, which I tried with HPCC_Causality and ECL in the first few weeks. Even though I had considered very few columns like 'price', 'beds', 'baths', 'sqfeet' and 'type' as the variables, it seems that all of them are causally related to each other. Each variable is dependent on the other.

Some of the observations are:

* As beds increased, prices increased. Similarly for baths and Prices. Indicating a positive correlation between beds and prices, and baths and prices.

* Baths and beds are also positively correlated.

* A definite positive correlation can be observed between sqfeet and price.

* Sqfeet & beds and sqfeet & baths are also positively correlated.

* There seems to be a type of correlation between the type and the price as well.

---

[HOME](https://arungaonkar.github.io/HPCC-Causality/) **|**
[Timeline](https://arungaonkar.github.io/HPCC-Causality/index.html#timeline) **|**
[Previous Week](https://arungaonkar.github.io/HPCC-Causality/week11.html) **|**
[Next Week](https://arungaonkar.github.io/HPCC-Causality/week13.html)