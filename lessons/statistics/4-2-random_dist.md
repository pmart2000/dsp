[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

random_1000 = np.random.random(1000)

random_1000_pmf = thinkstats2.Pmf(random_1000, label='random_1000')
thinkplot.Pmf(random_1000_pmf)
thinkplot.Config(xlabel='number', ylabel='PMF')

random_1000_cdf = thinkstats2.Cdf(random_1000, label='random_1000')
thinkplot.Cdf(random_1000_cdf)
thinkplot.Show(xlabel='number', ylabel='CDF')

Answer: The distribution is quite close to uniform.
