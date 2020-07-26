# Kickstarting with Excel

## An Analysis of Kickstarter Campaigns for US Plays

### Purpose

Louise is a playwright who is fundraising for her play, *Fever*.  She has a budget of over $10000.  She would like to use the crowdfunding site Kickstarter, and needs more information to help her create a successful campaign.  I analyzed Kickstarter data to discover any factors that would contribute to the success of Louise's campaign.

## Analysis and Challenges
I began by formatting the data to make it easy to read.  This also required creating a few more columns to convert dates and separate parent and subcategories.  In order to get a better understading of the data, I analyzed the success of campaigns in each parent category.  The Theater category was very successful in relation to other categories.  Drilling down, I found that Plays were successful in relation to other Theater subcategories.  Next, I needed to determine which factors contributed to a successful campaign overall.

### Analysis of Outcomes Based on Launch Date

In order to determine if the launch date of a campaign contributed to its success, I began by converting the Date Created and Date Ended columns to a standard format by breaking down the Unix Timestamps and using the 'DATE' function.  Then I used the '=YEARS' function to extract the year the campaign began for more in-depth analysis. 

I created a pivot table to view the outcomes of campaigns started at different times.  I added a filter for Parent Categories.  By assigning Dates Created and Years as rows and Outcomes to columns I was able to create a [line chart](Resources/Theater_Outcomes_vs_Launch.png) to show the success of campaigns throughout the year. 

I determined that May seemed to be an ideal time to launch a Theater campaign.  The number of successful campaigns showed a steady decline over the Summer months.

### Analysis of Outcomes Based on Goals

When I looked at descriptive statistics as they related to outcomes related to goals and amounts pledged, there seemed to be a correlation between the goal and the success.  To analyze this further, I created a sheet that broke down the Goals into twelve ranges.  I then used the '=COUNTIFS' function to pull the number of campaigns for each outcome within each goal range.  This data was specific to plays.  Then I used '=SUM' to find the total number of campaigns for each goal range.

I then created a [line chart](Resources/Outcomes_vs_Goals.png) to visualize the percentage of successful campaigns in each goal range.  There was no need to create a Pivot Table here as the data I needed was already in tabular form and specific to my needs.

### Challenges and Difficulties Encountered
While creating the pivot table and chart for the Outcomes Based on Launch Date, I encountered a couple of difficulties.  I noticed that there was an extra field created called \"YEARS2"\.  Somehow there was a row for both YEARS and YEARS2.  After I deleted YEARS2 from the rows of the table layout, both the table and the chart were easy to understand and filter.

As I was creating the table for Outcomes Based on Goals, I noticed that the numbers in the Successful and Failed columns were very similar for every row.  I also noticed that my line chart was pretty straight.  I looked back at the function and referenced my notes to be sure I had written it correctly, but didn't notice any errors.  I opened the function builder to check again that I had the correct information in each section.  To check the calculations, I returned to the Kickstarter sheet and filtered on Plays and a goal range to check the count.  I noticed the numbers my functions were returning greatly differed from the actual counts.  I again checked my function and noticed I had referenced the Pledged column instead of the Goals column. I fixed the error, but still did not get the output I was looking for.

I again referenced my notes and the video clip for creating '=COUNTIFS'.  I paused at a certain point and checked my arguments against his.  I still did not notice the mistake I made, so I turned to Google.  Eventually I notice that my arguments were asking for less than the lower limit and greater than the upper limit.  After flipping the inequalities I once again checked my outcomes against a filtered count on the Kickstarter sheet and confirmed my calculations were correct.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
Campaigns that begin in May are more likely to be successful that any other time of year.  The percentage of successful campaings steadily declines over the summer months and shows a dramatic dip in December.

- What can you conclude about the Outcomes based on Goals?
A capaign with a goal under $20000 is more likely to be successful.

- What are some limitations of this dataset?
There is not a standard currency for goals and pledges.  This makes it difficult to compare outcomes unless the data is filtered to a specific country.  I also wonder about the tier of the productions.  For instance a play being funded for community theater versus a Broadway or London stage, or a film being funded by a student versus a side project directed by Matt Damon.

- What are some other possible tables and/or graphs that we could create?
I would be interested to see the success of campaigns based on the length of the campain.  Does a campaign go stale after a certain time period?  If your campaign is too short, do you run the risk of not being fully funded?
Should a campaign with a larger goal have a longer duration?  Would allowing for more time contribute to the success of a campaign with a larger goal?  For this I would examine length of campaign versus goal amount.

