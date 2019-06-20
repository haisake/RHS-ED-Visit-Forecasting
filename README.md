# RHS-ED-Visit-Forecasting
To forecast ed visits at RHSl using Denodo as a data source, LM as the algorithm, and RMarkdown as the report generator.

For reference, see: https://github.com/nayefahmad/2019-06-19_lgh_ed-visits-by-day-of-week-and-month/tree/master/src 

The goal here is not to produce a highly accurate *predictive* algorithm, but rather to: 

* find how much of the variance in daily ED visits can be explained with weekday, year, month, and lagged values as predictors 
* test for interactions between weekday and month variables. If there is no interaction, there is no point in "slicing" data in this way to try to find e.g. whether Mondays in February are different from Mondays in September. There just isn't enough data to support these inferences. 