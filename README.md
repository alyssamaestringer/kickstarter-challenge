# Kickstarter Challenge for Module 1 
## Overview of Project
##### Louise is working on a play, *Fever*, which came close to its fundraising goal in a short amount of time. To understand how her fundraising efforts fared compared to other theatre campaigns, I broke down fundraising outcomes based on when a theatre campaign was launched and the funding goals, specifically for plays so Louise can compare apples to apples. This information will give Louise a clear picture of *Fever's* campaign performance.

## Analysis and Challenges
##### First Step: Creating a pivot table
We first want to look at what time of year theatre campaigns performed the best. To do this, I created a pivot table with the kickstarter data in order to see the number of successful, failed, and canceled theatre campaigns based on what month they were launched. In order to do this, I used the campaign created date as the data point for rows, narrowing down to month. For the columns, I filtered by outcomes to get the count of outcomes per month. 

Although I could see right off the bat from the pivot table that May had the highest number of successful outcomes, I wanted to get a better idea of what that looks like throughout the year. I created the line chart below to map out successful, failed, and canceled campaigns throughout the calendar year.

![Theater outcomes vs launch month](/resources/Theater_Outcomes_vs_Launch.png)

Now that we can see the best time of year to launch a theatre kickstarter campaign would be in the summer, we can relay this information to Louise. 

##### Challenges
I did not face any challenges gathering the above data, however, possible challenges could arise if you do not filter the data properly. For example, if you do not filter the pivot table with parent category to specify "theatre" and year to specify all years, the count would be off. Filters are a big factor in pivot tables and if you have just one filter off it will completely skew the data.

##### Second Step: COUNTIFS() function
Now that we know the best time of year to launch a theatre kickstarter campaign, we wanted to take it a step further by seeing what funding goal range had the highest level of success. Using the kickstarter data, we filtered out the percentage of successful, failed, and canceled campaigns using the COUNTIFS function. This function populates the number campaigns based on three factors; outcome (successful, failed, canceled), the funding goal, and specifically counting plays only.

Once this data was gathered in a table, I was able to create a line chart to visualize the relationship between goal-amount ranges and successful, failed, or canceled projects. The results are below.

![Outcomes vs goals](/resources/Outcomes_vs_Goals.png)

##### Challenges
I ran into issues when gathering the data using the COUNTIFS function. I realized I was not including the end number for the ranges. 

   What my formula originally looked like:

    =COUNTIFS('kickstarter'!D:D,">=1000",'kickstarter'!F:F,"successful",'kickstarter'!R:R,"plays")

   I changed it to:

    =COUNTIFS('kickstarter'!D:D,">=1000",'kickstarter'!D:D, "<5000",'kickstarter'!F:F,'successful",'kickstarter!R:R,"plays")

Once the formula was fixed, my line chart matched the assignment!

## Results
##### Theater Outcomes by Launch Date Conclusions:
1. May is a hot month for theater. The highest number of theater campaigns launched are in May, majority are successful but May is also the month with the highest number of failed campaigns as well. 
2. Since May has both the highest number of successful and failed campaigns, this tells me it's a competitive month to launch a theater campaign. I would conclude that the summer months (May-July) is the best time for Louise to launch her campaign.

##### Outcomes based on Goals:
Looking at what percentage of campaigns were successful based on their goals, this data suggests that campaigns with funding goals of $1000 or less are most likely to become successful campaigns. However, the $1000-$4999 was a close second for successful campaigns. In conclusion, the cheaper the funding goal for plays, the more likely the campaign will be successful. 

##### What are some limitations of this dataset?
We are looking at theater campaigns based on launch date but I think we should filter it down even further to plays to see if May is still the best time of year for a play campaign to launch. By measuring outcomes based on goals, we can't see how much was actually raised for successful campaigns. Although the funding goal is low for successful camapigns, the amount raised could tell us a different story. 

##### Other possible tables and graphs
We could create a bar chart for outcomes based on launch date in order to see a side by side comparison month over month. We could also create a multiple different graphs with the data collected for outcomes based on goal. We can create a bar chart to look at count of each outcome based on goal bracket instead of percentage. You could also do two pie charts, one for number of successful campaigns and the other for number of failed camapigns. The pie chart will show which range has the highest count of each outcome. 
