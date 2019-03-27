[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> 
resp = nsfg.ReadFemResp()

num_kids_pmf = thinkstats2.Pmf(resp.numkdhh)
thinkplot.Hist(num_kids_pmf, label='actual')
thinkplot.Config(xlabel='Children',
                ylabel='Probability')
                
biased_num_kids_pmf = BiasPmf(num_kids_pmf,label='observed')
thinkplot.Hist(biased_num_kids_pmf)
thinkplot.Config(xlabel='Children',
                ylabel='Probability')

num_kids_pmf.Mean() #1.024

biased_num_kids_pmf.Mean() #2.404
