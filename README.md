# Kickstarting with Excel

## Overview of Project

### Purpose
  For this project, our client has just come off of a succesful run of the play *Fever* where fundraising goals were met quickly. They want to understand how their play performed compared to others, and identify any indicators of success for future endeavors. The purpose of this analysis is to understand how different campaigns fared in relation to their launch dates and their funding goals. Visualizations were used to further understand and summarize campaign outcomes based on their launch dates and funding goals.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
This analysis was fairly straightforward. A pivot table was created and then filtered by Parent Category and Years. Outcomes defined the columns and Created/Launch date defined the rows. The calculated values were to count of the outcomes.

![image](https://user-images.githubusercontent.com/103475613/163698391-b9121ef6-ed08-49d1-915b-81b51d701f4b.png)

The next steps were to filter on the relevant Parent Category (theater), filter out live outcomes, and group the launch dates by Month. This leaves us with the below  pivot table which was used to generate the graph that visualizes the outcomes.

 ![image](https://user-images.githubusercontent.com/103475613/163698353-b7ec6b04-eca2-47ce-a6c5-15fdb0bec27a.png)

### Analysis of Outcomes Based on Goals
The first step of this analysis was to create the ranges. To do this, two new columns were added (pictured below). The concatenate function to create the goal categories.

![image](https://user-images.githubusercontent.com/103475613/163698569-780f8ea6-e2fc-468d-ab6f-eb6ef012aadc.png)

The next step was to create a series of countif statements (i.e. =COUNTIFS(Kickstarter!$F:$F,D$1,Kickstarter!$D:$D,">="&$B3,Kickstarter!$D:$D,"<="&$C3,Kickstarter!$R:$R,"plays"). The new range columns and a new row (pictured below) were used to make it possible to lookup up the less than value, the greater than value, and the outcome so those did not have to be typed. The condition of the subcategory being "plays" was typed as that did not change accross the ranges or outcomes - but it easily could be programmed in the same way. 

![image](https://user-images.githubusercontent.com/103475613/163698586-f8adc3ae-c43b-4d83-b122-6e746075bfbf.png)

After the count was completed, it was simple to sum the number of projects by range and set up a simple calculation to determine the percentage successful (#successful / total projects) and percentage failed (#failed / total projects). All that remained to do was create and format a simple line graph to display these percentages and how they related to the goal amount. 

### Challenges and Difficulties Encountered
  For the analysis of Outcomes Based on Launch Date, the primary challenge was in regards to formatting. It was important that the launch date was formatted properly so it displayed properly in the pivot table and corresponding graph. This analysis was focused on the launch month, so it was important, and challenging, to set the pivot table up with that in mind. It was also important to filter out results that were not associated with the Parent Category of "Theater" and those that were currently live.

  For the analysis of Outcome Based on Goals, the primary challenge was in the number of ranges that were to be compared. It was important to set up the analysis in a way that was not highly manual and used formulas as much as possible - instead of typing out the values associated with the ranges. There were also several elements in the countifs statements so it was important to check the results to make sure they were reasonable. I did this by doing some quick totals and comparing them to quic totals done using filters and the raw data.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

    May is the most popular month for play launches, with June coming in a close second. These months also had the highest rate of success. December had the fewest number of launches and the highest rate of failure. 

- What can you conclude about the Outcomes based on Goals?

     Most of the time, a smaller goal leads to a higher chance of a successful outcome. The excseption is the 9 plays that have a budget between $35,000 and $44,999 which show a much higher rate of success. This might warrant further investigation. You can also conclude that the majorities of plays had a goal of $1,000 to $4,999 with 85% of plays having goals of less than $10,000. 

- What are some limitations of this dataset?

     There is a wide array of data (countries, dates, budgets, categories) in this dataset. It may be valuable to find and focus on a dataset that is more focused on plays and theater. There may also be additional data points that are relevant to plays and theater, like ticket sales, marketing, or attendance, that would be valuable to explore but are not included in this dataset.

- What are some other possible tables and/or graphs that we could create?

     To expand the analysis of Outcome Based on Goals, It would be interesting to bring in the pledged data to better understand the outcomes quantitatively and not just whether the play was successful. You could update the table to have average % pledged (compared to goal) and have that on the y axis with a separate line for failed and successful. It would also be valuable to combine these two analysis and visualize Pledged or Goal amount vs Launch date.   
