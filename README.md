# Communicate-data-Findings

## Introduction

The goal of this project was to conduct and exploratory data analysis of the Ford GoBike dataset which can he found [here](https://www.kaggle.com/victorinoeng/fordgobike20172019?select=Clean_FordGoBike_2017_2019.csv). It is too big so I couldn't attach it in the repository. There is also a complimentary .csv file which links station ID to station name. First, the data is assessed and cleaned, then a univariate, bivariate and multivariate exploration are done. 

## Assessment and Cleaning 

The main issues identified with the station data was incorrect data types. In GoBike dataset, categorical data were not labeled in a clear way. Finally, to make things clearer the two tables should be joined. 

## Univariate exploration of data

In this section, simple questions regarding the Ford GoBike dataset are answered. 

### 1. What are the months during why bikes are rented the most

From the histogram, we see that the months in wich the most bike trips are made are March and April, and those with the least bike trips are May and June. 

### 2. What are the days of the week during which bikes are rented the most? 

We notice that bike trips are made at a significantly higher rate during the week than on week-ends. This made me wonder if these bikes are mostly used for work trips. This issue is explored in greater detail later. 

### 3. What is the distribution of the Gobike user age

On the first histogram in this section, we noticed that the data is skewed to the left because of extreme ages like 140. It is visible on the plot that most users are aged 20-40 with a mean of 35. 

### 4. What is the bike trip duration distribution like? 

This problem was a bit tricky, due to the fact that the trip duration distribution is very heavily skewed to the left which makes it impossible to see on a classic graph scale. By applying a log transform, I was able to visualise the data more easily. On a log scale, the bike trip duration distribution looked somewhat normal with a mean of about 10min. 

## Bivariate exploration of data 

In this section, more questions are answered and we delve deeper into problems which stemmed from the univariate analysis. 

### 1. Do subscribers take longer trips than non subscribers on average?

On the two boxplots, we can see that on average, subscribers take shorter trips than occasional users. 

### 2.Do younger users make longer trips than older users on average? 

Because of the copious amount of rows contained in the dataset, I decided to a sample from the original dataset. However, even after having done that there was still a massive concentration of observations in one area. By using a 2D histogram of heatmap, it became apparent that most trips are done my users in the 20-40 bracket and last between 5-20min. 

### 3. Do we have evidence to support the claim that Ford GoBikes are used mostly for work commute? 

By comparing the number of bike trips made per hour of the day to the number of trips made per day of the week, we saw an interesting trend: mos trips were made on Mondays, Tuesdays, Wednesdays, Thursdays and Fridays between 8-10AM and 5-7PM which are the start and end of usual work hours. We can therefore say that overall, the data indicates that Ford GoBikes are mainly used for work commute. 

## Multivariate exploration of data

In this part, the relationship between average trip speed, user age and gender is examined. 

The first step was to convert the start and end coordinates to distance on the surface of the earth. To do this, I created a function that uses the Haversine formula to find this value. I then created a new column which contained the trip speed. Then, I made a set of age intervals to plot a histogram. On the graph, it is apparent that the average the averge trip speed for men is slightly higher than for women over all age brackets. We also see that the fastest riders are in the age bracket 25-50 years. Finally, we observe that overall, travel speed declines from the age of 50 onwards for both genders.

