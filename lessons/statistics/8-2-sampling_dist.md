[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (sampling_dist)

>> Code for simulating the sample:
```
def SimulateSample2(lam=2, n=10, iters=1000):
    estimates = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        estimates.append(L)
    
    stderr = RMSE(estimates, lam)
    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('Standard Error: ', stderr)
    print('Confidence Interval: ', ci)
    
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='Estimate',
                     ylabel='CDF')
    
```
Standard error when n = 10: 0.87

90% confidence interval when n = 10: (1.26, 3.58)

Table of n versus standard error:

| n | stderr |
|---|--------|
| 10|    0.87|
| 20|    0.54|
|100|    0.20|
