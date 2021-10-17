# POLICE SHOOTING IN THE US : FACT VS MYTH

# Introduction
For the MSDS Practicum 1, I wanted to dive deeper into the issue that has been in the news quite frequently and been a concerning topic: police shooting. There was also in incident earlier this year where a military officer was harassed by a policeman. This was a first time I had heard of such incident. In this case, the military officer was a person of a color, which led me to this project and dive deeper into whether people of color are impacted the most by police shooting.

# Agenda
- Problem description
- Datasets
- Data prepping
- Exploratory data analysis
- Visualizations
- Correlation
- Forecasting
- Conclusion

# Problem Description
Here are the questions I want to answer in this project:
- Are people of color being impacted the most?
- Are there any other socio-economic factors Tied to shooting?
- How does the shooting trend will look like in the future?

Datasets
- Primary shooting dataset (Washington Post)
  - Shooting dataset
  - Contains descriptive information for Shooting from 2015- 2021
  - Close to 6k records
  - Name
  - Age
  - Gender
  - Race
  - Location
  - Victim Armed?

- Secondary [Census.gov]
  - Mobile house rate
  - Vehicle ownership rate
  - Bachelor’s degree rate
  - Median income
  - Poverty rate

# Data Prepping and Tools
- Jupiter notebook and Python
- Custom columns: Month Year, year, Age Banding: under 10, 10-19, 20-29, etc.
- Using state name dataset to join multiple datasets

# Exploratory Data Analysis
Here is a high-level view of the shooting represented for all sates from 2015- 2021.

![1](https://github.com/biplobgauli/MSDS692/blob/main/1%20Scatter%20plot.png)

And here is the same data for shooting broken down by states.

![1](https://github.com/biplobgauli/MSDS692/blob/main/2%20count%20by%20state.png)

And now we look at a table that breaks down this number by race and year. From the numbers below, it actually looks like white people were shot more than any other race. In fact, almost double that of black people.

![1](https://github.com/biplobgauli/MSDS692/blob/main/3%20count%20by%20race%20and%20year%20table.png)

This becomes more evident, when we look at it in a bar char that is grouped by race. For all the years, while people have been shot more than any other races.

![1](https://github.com/biplobgauli/MSDS692/blob/main/4%20bar%20chart%20by%20race%20and%20year.png)

Now let’s look at if the victims were armed when they were shot. From the table, below, it looks like on average, victims were not armed 90 % of the time.

![1](https://github.com/biplobgauli/MSDS692/blob/main/5%20Victims%20armed.png)

Looking at the type of people they had, it was primarily gun or a knife. But we also see some interesting one like a hammer and a machete!

![1](https://github.com/biplobgauli/MSDS692/blob/main/6%20weapon%20cloud.png)

From another perspective, it looks like people in their 20s and 30s happen to be shot the most, followed by people in their 50s and then teens.

![1](https://github.com/biplobgauli/MSDS692/blob/main/7%20age%20band.PNG)

When we compare shooting by states, California, Texas and Florida seems to be the top 3 states.

![1](https://github.com/biplobgauli/MSDS692/blob/main/7%20top%2010%20states.PNG)

Now let’s add in the secondary datasets to see if we find a correlation between the shooting and income level, education level, poverty rate, access to vehicle, mobile home rate. From the chart below, it doesn’t look like there is a similarity in the chart in the middle, that represents police shooting, and other socio-economic factors.

![1](https://github.com/biplobgauli/MSDS692/blob/main/8%20compare%20maps.PNG)

Let’s put them all in a correlation plot and see if we get a different result. However, doesn’t look like there is a strong correlation between the shotting count and the 5 socio economic factors.

![1](https://github.com/biplobgauli/MSDS692/blob/main/9%20corr.PNG)

Let’s plot all this information in a combination chart and see if we get a tend, in hopes of finding correlation. However, it doesn’t seem to be the case.

![1](https://github.com/biplobgauli/MSDS692/blob/main/10%20combo%20chart.PNG)

Now lets’s get population count by state and see if that helps explain any of this. As soon as we add the population dataset, we now see a strong correlation between shooting count and population. Almost close to +1. This makes sense that where there are more people, there will be more shootings.

![1](https://github.com/biplobgauli/MSDS692/blob/main/11%20corr%202.PNG)

Similarly, in the combination chart, we see that the black line (population) closely follows the brown line (shooting count).

![1](https://github.com/biplobgauli/MSDS692/blob/main/12%20combo%202.PNG)

With that being said, let’s do a before an after comparison for the shooting count with the shooting count as is and calculate a per million count per race and see if we see a difference. This is important so that we remove the population distribution disparity by race and get a standardized rate.

![1](https://github.com/biplobgauli/MSDS692/blob/main/13%20compare%20table.PNG)

Once we do so, it becomes evident that people of color are being impacted the most. Although in volume, while people have more instances because there are close to 4 times more white people than black in the US.
Similarly, once we do a before and after for the shooting count in a bar chart, it is really cleat that people of color are hurt more. This answers our first question that people of color are impacted the most by police shooting in the US.

![1](https://github.com/biplobgauli/MSDS692/blob/main/14%20compare%20bar.PNG)

# Forecasting
I used Facebook Prophet for my forecasting and with the data we have, it doesn’t look like the trending is going to change much. In fact, it is very similar to the historical data.

![1](https://github.com/biplobgauli/MSDS692/blob/main/15%20prophet.PNG)

This makes sense because the shooting count has stayed pretty consistent around the 900s mark. However, for until August 2021, the count seems to be a third of the past years, so it is a little promising. 

![1](https://github.com/biplobgauli/MSDS692/blob/main/16%20historical%20trend.PNG)

# Obstacle
One of the obstacles I see for the shooting trend now lowering is because the use of body cams has stayed the same throughout the years. Maybe use of body cams would encourage policemen from using appropriate level of action and deter form resolving to unnecessary shooting and violence.

![1](https://github.com/biplobgauli/MSDS692/blob/main/18%20obstacle.PNG)

# Summary
- Are people of color being impacted the most?
  - Not at first glance. But yes, black and Hispanic seem to be impacted the most once we calculate the per misslion shooting count by race. 
- Are there any other socio-economic factors tied to shooting?
  - There doesn't seem to be a strong corelation between the different socio-economic factors. However, there was a strong corelation between population size and shooting count.
- How does the shooting trend will look like in the future?
  - The trend seems to continue at a similar pace compared to the past five years. 
