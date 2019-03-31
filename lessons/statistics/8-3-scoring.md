[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---

>> 
```
def VertLine(x, y=1):
    thinkplot.Plot([x, x], [0, y], color='0.8', linewidth=3)

def SimulateGames(lam, m):
    estimates = []
    for game in range(m):
        L = SimulateGame(lam)
        estimates.append(L)
    
    print('RMSE L: ', RMSE(estimates, lam))
    print('Mean Error L: ', MeanError(estimates, lam))
    
    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    stderr = RMSE(estimates, lam)
    VertLine(ci[0])
    VertLine(ci[1])
    print('Confidence Interval: ', ci)
    
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='estimate of goals',
                     ylabel='CDF')
```
Results for SimulateGames(2, 1000):
* RMSE / Standard error: 1.38 # should these be different?
* Mean error: -0.029
* Confidence interval: (0, 5)

The higher the 'm' (number of estimates), generally, the lower the Mean Error, so I believe the process is unbiased. 
The higher the 'lam', the higher the RMSE / standard error, but the error did not increase proportionately to the lam value.

---
