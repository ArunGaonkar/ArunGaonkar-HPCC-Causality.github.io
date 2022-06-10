---
title: week 3
---

# 06/06 Monday Day 10

Sent the Weekly report to Roger.
The dataset that I found has only 1460 rows, which seems less for causality analysis. So I started to look at other datasets.

So I found another [dataset](https://www.kaggle.com/datasets/austinreese/usa-housing-listings) which has 384977 listings with 22 columns, which includes

* price data
* latitude
* longitude
* number of bedrooms
* number of bathrooms
* square footage of the house
* state
* type of house (apartment, condo, house etc.)

But change in the hypothesis is not required, as it also applies to this dataset. [original hypothesis was intuition based]

I started learning to write code in ECL. Also started ECL training from LexisNexis - Introduction to Enterprise Control Language.

# 06/07 Tuesday Day 11

continued tutorials from LexisNexis on ECL.

Team meeting :1130-1230

1. Include square footage in the hypothesis of Housing dataset, as it is a function of number of bedrooms and bathrooms.
2. Send the updated hypothesis of both the dataset.
3. Prioritize on ProAgrica Scheme as it may take some time to get the data.
4. Roger Cleared the doubt on Causal Discovery of the model.
5. Find a way to include week number ranging from 1 to 52 for the covid19 dataset.
6. instead of country code, include the discretized latitude. If I can find that in the dataset, include it otherwise have to do it manually.

Updated the hypothesis for both the dataset and sent it to Roger.

# 06/08 Wednesday Day 12

Continued tutorials from LexisNexis on ECL.

When I tested synthTest, I got this error,
Code 1303,System error: 1303: RoxieMemMgr: Unable to create heap

![error-Synth](imgs/errorSynthTest.png)

I started coding and read the data from the dataset.

Since the file size is 30 Mb, I am not able to get all the rows.
Default size is 4MB, and hard limit is 10 MB. Si I should find a way to read 30 Mb file.

# 06/09 Thursday Day 13

I have received ProAgrica Data and I was asked to find 3-10 variables that can be used to build a causal model and apply the toolkit on AgX dataset.

I have received the latitude and longitude data for countries(world.flat) and US counties(us.flat). But in the World file, there are multiple latitude and longitude entries for the same country, having entries for multiple states. So I have got the doubt of which entry to consider for the causal model.

When I tried to upload the file into my cluster, uploading was getting failed because of less disk space. I am seeing 100% usage on thor, hthor, roxie, etc. clusters. Is it because of low memory? I have downloaded the dataset on my VM, which consumed all the disk space, due to which I was not able upload file.

I have Started analyzing ProAgrica scheme as they (ProAgrica.com) might need some time to release the data that we asked. So this was considered to be of higher priority.

There was an event "Intern Chat" organized by Lorraine for the interns to meet each others.

1. It was a privilege's to meet other interns and few LexisNexis employees as well.

2. Getting to know what is happening at 'HPCC Systems' and what other interns are working on was a great experience.

Later in the team meeting I had discussed the issues that I found with Roger.

1. For the COVID-19 dataset, with multiple values of latitude and longitude, we discussed multiple ways to get a single value latitude. Taking the first entry was not ideal choice and so median. Hence, we have decided to use the mean of the latitude of different states of the country for an entry date.

2. Regarding uploading the files to the cluster and failing the SynthTest, Roger helped me to find the issue. It was the disk space issue. So, I tried to increase the disk size of VM. It took around 2 hours to resolve the issue of expanding the disk. Now I have expanded the disk from 13GB to 52GB.

3. In-order to reduce complexity in the Causal model for the housing dataset, we decided to ignore the dependency of Housing type on the number of bedrooms and bathrooms and also the square footage.

When reading the level1.csv (COVID-19 dataset) file, I have decided to reach out to Hugo for the additional instructions. I also wanted to ask which is the most suitable file type (flat vs csv) for playing with the data.

# 06/10 Friday Day 14

