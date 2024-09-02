<h1>Permutation Testing</h1>

<h2>Description</h2>

In a 2016 CBS article entitled ["What does beer have to do with mosquito bites?"](https://www.cbsnews.com/news/beer-and-other-reasons-zika-mosquitoes-may-want-to-bite-you/) by Mary Brophy Marcus, there was a growing concern of the Zika virus becoming widespread in the U.S. especially for those who are big on the great outdoors. 

In conversation with Grayson Brown, a mosquito scientist and the director of the Public Health Entomology Laboratory in the Department of Entomology at the University of Kentucky,  there are various suggested reasons as to why some people may be more likely to become mosquito bait compared to others - one of them is alcohol consumption.

To examine the validity of this relationship between drinking beer and mosquito bites, a study has been carried out and its statistical significance was tested to determine whether there is an association between beer consumption and attracttiveness to mosquitoes. 

The idea of this study is inspired by John Rauser during his talk about ["Statistics Without the Agonizing Pain"](https://www.youtube.com/watch?v=5Dnw46eC-0o) in the Strata Conference + Hadoop World 2014 in NYC.

<h2>Languages and Utilities Used</h2>

- <b>Pandas</b>
- <b>Matplotlib</b>
- <b>seaborn</b>
- <b>numpy</b>

<h2>Data Source</h2>

The data set of the experiment is appended to this repository. It shows the response of mosquitoes bites based on different treatment groups of beer drinkers vs water drinkers.

<h2>Part 1 - Drawing assumptions from observations</h2>

<p align="center">
Side-by-side boxplots for the number of mosquitos in each group (beer vs water): <br/>
<img src="https://i.imgur.com/7KuFKf9.png" height="50%" width="50%" alt="Pipelines and Workflow"/>
<br />
</p>

The graph shows the comparison of mosquitoes attractiveness between beer drinkers and water drinkers.

The total number of mosquitoes recorded for this experiment ranges between 12 and 31. For the beer drinking group, the response is noted between 17 and 31 which is higher than that for water drinkers, which is between 12 and 24. Therefore, based on initial inspection, this suggests that **there is an association between beer consumption and attractiveness to mosquitos** (i.e. mosquitoes are more attracted to beer drinkers).

To further support this statement, it can be seen that the median of the beer group is almost **in line** with the maximum value of their counterpart. In addition, its entire interquartile range is **higher** than the median of the water group. This shows that there are more mosquitoes attracted to beer drinkers than water drinkers.

<p align="center">
Descriptive statistics for each treatment groups: <br/>
<img src="https://i.imgur.com/NIYW5qe.png" height="50%" width="50%" alt="Descriptive statistics for each treatment groups"/>
<br />
</p>

Mean corresponds to the average of a data set. Therefore, based on the experiment, the average number of mosquitos attracted to beer drinkers is 23.6 and it is higher than that for the water drinkers, which is 19.2. This information provides an early/preliminary suggestion that mosquitoes are more attracted to beer drinkers than water drinkers.

Median corresponds to the middle value of the data set in ascending order. For beer drinkers, it is 24.0 whereas for water drinkers it is 20.0. Since the mean and the median for both groups are almost the same (23.6 vs 24.0 and 19.2 vs 20.0), their dataset is more or less evenly distributed from the lowest to highest values.

Standard deviation corresponds to the degree of dispersion of a data set relative to its mean. For the beer and water drinking groups, it is 4.13 and 3.67 respectively. Since the standard deviation of the beer drinker is higher, this indicates that their mosquitoes attractiveness are more spread out than water drinkers. The difference between the means of two treatments is around 4 mosquitos, which corresponds to the standard deviation of 4 mosquitos, for both treatment variables.

<h2>Part 2 - Permutation Testing</h2>

Permutation tests are non-parametric tests that require very few assumptions. So, when you don’t know much about your data generating mechanism (the population), permutation tests are an effective way to determine statistical significance. ["Adopted from "How to use Permutation Tests" by Michael Berk (Towards Data Science, September 2021)"](https://towardsdatascience.com/how-to-use-permutation-tests-bacc79f45749). In other words, the goal of permutation testing is to investigate whether these observations were to happen either by chance or not. 

<h3>Workflow:</h3>

- To estimate the sampling distribution of the test statistic we need many samples generated under the strong null hypothesis.
- If the null hypothesis is true, changing the exposure would have no effect on the outcome. By randomly shuffling the exposures we can make up as many data sets as we like.
- If the null hypothesis is true the shuffled data sets should look like the real data, otherwise they should look different from the real data.
- The ranking of the real test statistic among the shuffled test statistics gives a p-value

<p align="center">
Python code for data simulation: <br/>
<img src="https://i.imgur.com/SctSOVO.png" height="80%" width="100%" alt="Python code for data simulation"/>
<br />
</p>

<p align="center">
Permutation test result <br/>
<img src="https://i.imgur.com/uXR00JT.png" height="50%" width="50%" alt="Permutation test result"/>
<br />
</p>

<h3>Based on the results:</h3>

- Total number of simulations: 10000
- Total number of times simulated mean is higher than 4.4: 2 
- The probability of obtaining the experiment outcome: 0.02%

<h3>Conclusion:</h3>

- Since the calculated probability is too small, it can be concluded that it is very unlikely to get such an observation by chance and the skeptical ‘no association’ hypothesis can be rejected. 
- That means, these observations did not happen by chance and that drinking beer does affect the affinity of mosquito bites.





























