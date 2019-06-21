# RHS-ED-Visit-Forecasting
To forecast ed visits at RHSl using Denodo as a data source, LM as the algorithm, and RMarkdown as the report generator.

For reference, see: https://github.com/nayefahmad/2019-06-19_lgh_ed-visits-by-day-of-week-and-month/tree/master/src 

The goal here is not to produce a highly accurate *predictive* algorithm, but rather to: 

* Find how much of the variance in daily ED visits can be explained with weekday, year, month, and lagged values as predictors. If, for example, only 30% of variance is explained, then it is misleading to display only the averages by day of week in a graph. This would give the impression of precision where it is not justified. 
* Fest for interactions between weekday and month variables. If there is no interaction, there is no point in "slicing" data in this way to try to find e.g. whether Mondays in February are different from Mondays in September. There just isn't enough data to support these inferences. 

# Proposed file structure for R scripts 

1. *data-pull-and-cleaning.R*: Script for connecting to denodo, pulling in daily ED visits data, and cleaning it up. Final result should be a dataframe with the following columns: 

* $ date : Date, 
* $ years_from_2017: int
* $ month : Factor: 1, 2, 3, ...
* $ year : Factor: "2017", "2018", ...
* $ weekday : Factor: "Monday", ...
* $ ed_visits : int  
* $ lag_ed_visits : int  
