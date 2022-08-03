# Analysis of Kickstarter Campaigns

## Overview of Project

Our client, Louise, seeks funding to stage her play, *Fever*. She has launched a Kickstarter campaign and quickly generated most of her funding. She wants to know if the time of year that she started her campaign and the amount of money she has budgeted for the production will affect the likelihood that the campaign will achieve success.

### Purpose

This analysis aims to investigate data from various theater-based Kickstarter campaigns to discern whether the parameters of the campaigns have an impact on their success rates. The focus of this investigation is the impact of the campaign launch dates and the funding goals set by each campaign.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

A table was created from the dataset which listed the total number of Kickstarter campaigns broken down by the month the campaign launched. The table was populated by using the pivot table function in Microsoft Excel to count the number of campaigns that fit the criteria for each cell in the table. The totals for each month were further divided into columns based on whether the campaign was successful, failed, or canceled. The campaigns were also filtered to include only theater-based campaigns. An option was included to also filter the results by a specific year.

![Table of campaign outcomes by launch month](https://github.com/tfish110/kickstarter-analysis/blob/main/Resources/Launch_month_table.png)

The breakdown of the the outcomes for theater campaigns by the month they were launched for all years in the dataset (2009-2017) is displayed in this graph:

![Graph of campaign outcomes by launch month](https://github.com/tfish110/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

A second table was created from the dataset which examined the relationship between the dollar amount goal set for the campaign and the resulting success rate:

![Table of campaign outcomes by goal amount](https://github.com/tfish110/kickstarter-analysis/blob/main/Resources/Goals_table.png)

While the previous table included all theater-based campaigns in the dataset, this table narrowed the focus even further to only include plays, as opposed to musicals or theater construction projects. Goals were broken into subsets starting with those seeking less than $1000, then those between $1000-4999, those between $5000-9999, with each group thereafter increasing the dollar range by another $5000. The groupings stopped at $49999, and the final group included all campaigns seeking $50000 or more. The total number of campaigns within each dollar amount grouping were summed, and broken into three categories based on outcome: successful, failed or canceled. The cells in this table were populated by using the COUNTIFS function within Microsoft Excel, wherein the parameters decribed above were used to direct Excel to which datapoints met the desired criteria for each cell.

Each of these outcome categories were also calculated as a percentage of the total number of play campaigns in that dollar amount range. These percentages were calculated by simply dividing the sum for the respective category (successful, failed, or canceled from columns B, C, and D) in each goal range by the total number of projects for the goal range (column E). Columns F, G, and H were populated with each repective outcome, and displayed as a percentage. A line graph was created to display the percentage success, failure, and cancelation rates across each goal amount range:

![Graph of campaign outcome percentages by goal amount](https://github.com/tfish110/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

While this was a relatively simple anaylsis, there were some challenges encountered in the process of constructing these tables and graphs. In the first table, I was a bit concerned that we were being asked to display the campaign launch month in each row, but that we had not created a column in the source data to list the month separately, as we had been asked to do for the year. After some trial and error, I realized that the options in Excel to create pivot tables were able to recognize the date format as separate components of day, month, year already, without having to isolate those components each in their own column. Thus, it seems that making a separate column for the campaign launch year may have been unnecessary; the program would likely be able to parse out the year alone from the full date without the extra work of making a new column. It was also worrying that the fact that there were no canceled projects in the October row, but rather than listing a zero, it is simply left blank. This also resulted in a gap in the line graph for canceled projects, which makes it seem incomplete, or as though some kind of error was made. Just because there is a zero as a data point, that doesn't make it meaningless, and so it should be labeled as a zero.

For the outcomes based on goal amounts, I found the editing of the COUNTIFS formula for each individual cell to be rather tedious. I suspect that there must be a way to automate this process, or at least to perform the same task in a more efficient manner; but, I suppose I will have to pay attention to learn what that is when it comes up in the coursework.  I also found it disconcerting that as I was editing the formulae in the "Number Canceled" column, each cell was being populated as 0. At some point I did actually go back to the source data, and scrolled through the outcomes there to see if I was making some error in my COUNTIFS formula, only to discover that there really were no cancelled projects for this category of Kickstarter campaigns. Once I realized this, I found that the whole exercise could have been simplified greatly if we knew we would only be comparing successes vs. failures, without any canceled or live campaigns; as can be seen in the graph, with a flat "canceled" line, the "success" and "failed" lines are just inverse/mirrored images of each other, which makes perfect sense when there are only two actual options in the dataset. It made calculating the percentages and the graph itself seem rather superfluous, because when the only other option is failure, just examining the success rate alone would have essentially given us the same information about the dataset.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

There seems to be a clear advantage in the success rate of projects that launched in May or June when compared to the other months. While the canceled and failed campaign lines are comparatively flat across the whole year, there is an obvious spike in successes for those months.

On the contrary, December seems to be the worst month to launch a campaign. There are clearly more successes than failures in every other month, but in December, the successes drop to have approximately the same number of campaigns as the failures.

- What can you conclude about the Outcomes based on Goals?

The major takeaway from this analysis is that campaigns seeking less than $5000 have a much greater chance of being successful than those asking for more. This is clear because the first two goal ranges (less than $1000, and between $1000-4999) are the only ones which have both a large sample size and a much higher success rate than failure rate. While there are some other ranges which have high percentages of successful campaigns, such as those between $35000-39999 and those between $40000-44999, the sample size for those categories is much too small to draw any meaningful conclusions about those campaigns.

- What are some limitations of this dataset?

One of the biggest limitations of this dataset is the lack of information about how any of these campaigns was marketed. It seems inherent to the design of crowdfunding that the number people who know about a campaign and the ways in which the might be incentivized to contribute would have a very significant impact on the success of the campaign. Without knowing this information, Louise is missing a big piece of the puzzle in determining ways to maximize the success of her campaign.

The other major limitation is the lack of data since 2017. The onset of a global pandemic unquestionably had a huge impact on the live entertainment industry starting in 2020, and still does today. Since live entertainment has had to undergo many changes to accomodate rules about large gatherings of people, it would be logical to assume that consumers' willingness to contribute to a crowdfunding campaign for live entertainment would be impacted as well. This would be a major factor in the way Louise might proceed to meet her campaign's goal. 

- What are some other possible tables and/or graphs that we could create?

While we addressed the lack of data since 2017 above, it would also be very interesting to see how campaigns may have changed over time in the data set that we do have. According to [Kickstarter's website](https://www.kickstarter.com/about?ref=global-footer), they were founded in late April 2009, the same year our dataset starts. So, since web-based crowdfunding was such a new approach to tackling projects like Louise's, it might be helpful to see if we can determine any changes over time in the way that goals were set and campaigns were launched. For example, would the conclusions that we made about May and June being good months to launch a campaign hold true for each individual year in the dataset? Is that data that accurately reflects a trend about Kickstarter campaigns? Or is the dataset perhaps front-loaded with datapoints from May and June of 2009 specifically, because the site had just launched prior to those months? If so, that might make any conclusions about launch month questionable if they no longer hold true in more recent years.

It would also be interesting to make better use of the location data. In previous exercises throughout this module, we were tasked with isolating data from the United States or Great Britain specifically. However, without knowing which country Louise is staging her play in, it makes it difficult to focus in on a specific population of interest for her to solicit for funding. It seems unlikely that she would have much success in getting patrons to fund a play that would be staged thousands of miles away, so narrowing her focus to analyzing local crowdfunding data might be a more helpful tool for her.
