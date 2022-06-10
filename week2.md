# 05/31 Day 6 Tue

Testing the models

Trying to understand probability testing

Building the hypothesis for the covid19 model

A meeting with Lorraine

* Maintain the Fieldglass-timesheets
* Complete the training which is about 2 hrs.
* set up LexisNexis email id

sent a status update to the Roger

Built two hypothesis:

1. The effect of vaccination on testing positive for covid 19 again.
2. the effect of weather on covid 19.

Team Meeting with Roger and Z.Shen

* checked the working of the setup in my machine
* hypothesis for covid 19 dataset was discussed and H1 has been discarded. H2 has been approved.

## Hypothesis 1

* Vaccination and secondary testing result data is not available
* Vaccination data has few information only.

So hypothesis 1 has been discarded.

## Hypothesis 2

* can consider variables like temperature, humidity, wind speed, month and latitude
* breakdown seasonality by month (discrete) and latitude (continuous variable).
* R is a function of latitude and week of the year
* include the delay of 2-3 weeks in the model as the R value is delayed by test result time.

# 06/01 Day 7 Wed

Read 4 Research Paper for the Hypothesis Proposal.

Submitted Hypothesis Proposal.

Testing the model in the Causal hypothesis.

Got few doubts in the results of testing the Causal discovery of a model.

# 06/02 Day 8 Thu

Working towards the suggestion on the Causal Hypothesis Proposal.

Team meeting 1130-1245

* find a way to test the relationships??
* keep some particular intervention queries
* find a method for validating the model, type of causal metrics
* look at other dataset -- house pricing dataset, so we can build on at least one of the hypothesis.

Decided to keep only week number,country (or latitude, can ignore longitude as it won't affect much) and R in the dataset.

I have received the access to the covid19 dataset. But not able to spray it into my cluster.

Started filtering out the countries based on the data availability.

If some causal relation found, we can continue with other data (temperature, county level).

built a sample causal model for the above hypothesis.

![covid-causalHypothesis](imgs/covid-causalHypothesis.png)

# 06/03 Day 9 Fri

Sprayed the covid19 dataset into the cluster.

Dataset Analysis & Inferences:

* each country has 115 entries.
* **ANTARTICA** has only 15 entries, so this will not be considered.
* **BELIZE** has 115 entries but it starts from 20200323 instead of 20200322.
* **BOTSWANA** has no entry (114 total) for the date range 20200322-20200324 & 20200325-20200329 (but 20200330-20200331 is available).
* **BURMA** has no entry (114 total) for the date range 20200322-20200324 & 20200325-20200326 (but 20200327-20200331 is available).
* **BURUNDI** has no entry (114 total) for the date range 20200322-20200324 & 20200325-20200330 (but 20200331-20200331 is available).
* **KOSOVO** has no entry (114 total) for the date range 20200322-20200324 & 20200325-20200325 (but 20200326-20200331 is available).
* **LIBYA** has 115 entries bur it starts from 20200324 instead of 20200322.
* **MALAWI** has no entry (113 total) for the date range 20200322-20200324 & 20200325-20200331 & 20200401-20200401 (but 20200402-20200407 is available).
* **MALI** has no entry (114 total) for the date range 20200322-20200324.
* **Sierra Leone** has no entry (114 total) for the date range 20200322-20200324 & 20200325-20200330 (but 20200331-20200331 is available).
* **SOUTH SUDAN** has no entry (112 total) for the date range 20200322-20200324 & 20200325-20200330 & 20200401-20200404 (but 202000405-202000407 is available).
* **US** has 116 entries. One extra for 20200315-20200317 & 20200318 - 20200324 (instead of 20200322-20200324).
* **WEST BANK AND GAZA** has no entry (114 total) for the date range 20200322-20200324, but 20200326-20200331 is available.

![filteredCountriesAnalysis](imgs/filteredCountriesAnalysis.png)

Found the Boston housing dataset. <https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data>

## Hypothesis 1: The effect of month on the selling price of the house

In which month the house is sold the price is the highest? and in which month the price is the lowest? Can we observe the trend in the selling price of the house in a year?

## Hypothesis 2: The number of rooms and the location has a positive effect on the selling price of the house

As the number of rooms increases, the selling price of the house increases. It may also be the case that the location of the house increases the selling price.
