[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
Approximately 34% of the U.S. male population is in the range of 5'10" to 6'1".

Code:

'# 5'10" = 178.80 cm
'# 6'1" = 185.42 cm
min_height = dist.cdf(177.8)
max_height = dist.cdf(185.42)
eligible_blue_men_percentage = max_height - min_height
eligible_blue_men_percentage
