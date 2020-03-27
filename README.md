# Delayed-Flights-Exploration
## by Julia Lee


## Dataset

The data that we will be exploring in this notebook is originally from [The U.S. Department of Transportation's (DOT) Bureau of Transportation Statistics (BTS)](https://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp) that tracks performance of domestic US flights operated by large air transit companies. There consists of a number of on-time, delayed, cancelled etc. flights that were recorded for the 2008 year. This exploration will go through univariate, bivariate and multivariate exploration of this dataset.

Prior to exploration, I decided to clean the dataset to allow for easier analysis and manipulation when exploring. The original dataset at 30 columns but after cleaning, I've ended up with 23 as I have dropped some columns that I deemed were not necessary for our analysis. Most of the dataset was fairly manageable as most changes were in the datatype converting to integers, string, or categories etc. Once I was satisfied with data cleaning, I moved onto exploration. 
Note: Even once exploring I had to go back to make some cleaning changes and move on.

## Summary of Findings

I initially wanted to see the affects of cancelled flights throughout the months, and year so I first plotted some countplots of flights per month, and flights per weekday and saw that December had the highest number of flights in the US and out of the week, Friday had the highest number of flights. This was a predicted result. 

Next I plotted out the flights departing times. Most flights departed at the 5:00pm hour, the least amount of flights departing at 4:00am.

As my initial feature of interest was cancelled flights, I decided to plot a pie chart of cancelled and not cancelled flights to see what percentage of flights in the US 2008 were cancelled. Unfortunately for our analysis (not for the passengers of these flights), we were only able to see a 0.03% of flights were cancelled that year. We will see if we can come back to the cancelled/non cancelled variable later one.

Shifting to delays, we plotted a histogram of arrival delays. At first there were many outliers that caused the graph to not show a distribution, but a block instead. So we shortened the limits and used smaller bin sizes to see a better result. We found out that most flight arrival delays were about 0-25 minutes long. There were some extreme outliers with 2 delays of more than 2000 minutes (33.3 hours).

Moving on to our last univariate exploration, we plotted out the counts of flight for each unique airline carrier. We saw that Southwest Airlines flew the most flights out of the whole year almost doubling the second airline (American Airlines). Hawaii Airlines and Aloha Airlines flew the least.

For our first bivariate plot, I wanted to revisit the cancelled/non cancelled variable and see if there was any interesting result when plotted with the time variables. First I tried month, then day of the week and lastly departure time. Due to the extremely low number of cancelled flights, again we were not able to garner any valuable information. This is when I started to shift focus to delays instead.

I plotted types of delays against month and saw that carrier delays and late aircraft delays were the two delays that had the most minutes of delay throughout the year. 

Seeing as how the carrier and late aircraft delay were both related to unique airline carrier, I next plotted these averages against the unique airline carriers on the x-axis in a barplot. Mesa Airlines has the longest average carrier delay and AirTran Airways had the longest average late aircraft delay. 

Lastly, I moved onto multivariate exploration which looked at 3 or more variables. I wanted to first see a high level graph of all the numeric variables of choice. I used a heat map which showed the correlation between multiple variables. We saw that all the different types of delays were correlated with arrival delays, but unfortunately not with each other. This made it difficult for any other type of analysis.

I plotted two PairGrids of scatter plots, one of all the numeric variables, and the second honing in on 'ArrDelay', 'CarrierDelay', 'WeatherDelay', 'NASDelay', 'LateAircraftDelay'.

Lastly, a scatter plot of the four delay types in the second PairGrid plotted against arrival vs departure delay graphs. 


## Key Insights for Presentation

For my presentation, I decided to include 6 figures that I felt were necessary to flow throughout the exploration smoothly. I chose to include 2 univariate relationships, one of flights per month/ day of the week, and one of the distribution of arrival delays. 
For bivariate relationships I also included 2 figures, one of all the types of delays per month, which leads into the second plot of unique carriers and the mean of carrier delay and late aircraft delay. The first plot shows the result that carrier delays and late aircraft delays were the two types that had the highest sum of minutes total in delays which leads to the second plot of seeing those types with respect to each unique airline carrier. 
Lastly for multivariate exploration, I also included 2 figures. Unfortunately, I felt I wasn't able to explore too much in this region as any investigation I looked into felt redundant. I ran into a lot of dead ends that did not provide any interesting or insightful result. In the end I decided to first see the overall correlation of the numeric values of interest in the form of a heat map which showed that weather delay, late aircraft delay, NAS delay and carrier delay had the highest correlation to arrival delay. So omitting security delay, I plotted some scatter maps of the 4 highest correlated types of delay against arrival delay on the x-axis and departure delay on the y-axis encoding the different types of delays by color. 

## Feedback 

I was advised to add commentary to select slides to help the reader understand easier as well as help the flow of my exploration.

## References
The dataset I chose was originally from the [The U.S. Department of Transportation's (DOT) Bureau of Transportation Statistics (BTS)](https://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp)

The [Bureau of Transporation Statistics](https://www.transtats.bts.gov/FieldInfo.asp?Field_Desc=Unique%20Carrier%20Code.%20When%20the%20same%20code%20has%20been%20used%20by%20multiple%20carriers%2C%20a%20numeric%20suffix%20is%20used%20for%20earlier%20users%2C%20for%20example%2C%20PA%2C%20PA%281%29%2C%20PA%282%29.%20Use%20this%20field%20for%20analysis%20across%20a%20range%20of%20years.&Field_Type=Char&Lookup_Table=L_UNIQUE_CARRIERS&Table_ID=264&SYS_Table_Name=T_SCHEDULE_T1&Sys_Field_Name=UNIQUE_CARRIER) had a list of the unique carrier codes and their respective airline.

`jupyter nbconvert Delated_Flights_Exploration_Slides.ipynb --to slides --post serve --template output_toggle` 
Terminal command code to view jupyter notebook as slides, as well as output_toggle.tpl template file provided to be used with nbconvert to view slides hiding the code used to produce the plots.

The original exploration notebook was a template the consisted of some questions to promote thinking about our analysis. These question and answers are present in the 'Delayed_Flights_Exploration_Analysis.ipynb' file but not present in the 'Delayed_Flights_Exploration_Slides.ipynb' (or html) file.
