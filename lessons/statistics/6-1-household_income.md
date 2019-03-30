[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

>> Mean(sample) = $74,278. Median(sample) = $51,226. Skewness(sample) = 4.95. PearsonMedianSkewness(sample) = 0.74.
>> 66% of households report taxable income below the mean. (This can be calculated by storing Mean(sample) as a variable,
>> 'mean', and then computing cdf[mean].) 
>> The assumed upper bound ($1 million) has a dramatic effect on the above calculations. For example, if we raised the
>> upper bound to $10 million, the median income stays the same, but the mean income and skewness increase significantly
>> (to $124,267 and 11.60, respectively), and 85.7% of households are below mean income. 
