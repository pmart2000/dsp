[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

>> Correlation Code:

mother_ages = live.agepreg

birth_weights = live.totalwgt_lb

Corr(mother_ages, birth_weights) # 0.0688

SpearmanCorr(mother_ages, birth_weights) # 0.0946

>> Scatter Plot Code:

thinkplot.Scatter(mother_ages, birth_weights)

thinkplot.Show(xlabel="Mother's Age (Years)",
               ylabel='Birth Weight (lbs)')
               
>> Percentile Plot Code:

bins = np.arange(13, 43, 3)

indices = np.digitize(mother_ages, bins)

groups = live.groupby(indices)


ages = [group.agepreg.mean() for i, group in groups]

cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups]


for percent in [75, 50, 25]:

    weights = [cdf.Percentile(percent) for cdf in cdfs]
    
    label = '%dth' % percent
    
    thinkplot.Plot(ages, weights, label=label)
    
    
thinkplot.Config(xlabel="Mother's Age (Years)", ylabel='Birth Weight (lbs)')
