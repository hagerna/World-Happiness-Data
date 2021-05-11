# World Happiness Data Visualization (Linnea Nygren)

I'm interested in how mental health plays a role in a country's happiness. I would have to guess that countries that have a higher ladder score would potentially have lower rates of depression/suicide, or at least more support for mental health. For this, I'll be looking at a secondary dataset alongside the world happiness dataset.
This dataset from [Our World in Data](https://ourworldindata.org/mental-health) shows the prevalence of depression as recorded by the World Health Organization and National Institute of Mental Health, as well as the [suicide data](https://ourworldindata.org/suicide). 

### Encountered Issues:

Since these datasets are not standardized in any way, I have run into a couple of problems so far. In the world happiness ranking dataset, there are lots of missing entries in the beginning couple of years data is recorded as well as missing entries for 2020 most likely due to the pandemic. On the mental health dataset,
many years are included that have no data whatsoever, such as years in the 1960's and 70's. For the latter issue, I have simply chosen to not include those years with no actual recorded prevalence data, as they contribute nothing to begin with. On the other hand,
the world happiness ranking dataset is a bit more complicated, as some countries have recorded data for a year while others do not. Going off of Nick's idea, I will be starting that dataset from 2011 onwards since that is when the data starts to become more consistent.

{% include_relative Visualizations/mentalhealth_boxplot.html %}

After dropping the columns with no prevalence data, here is the worldwide distribution of depression prevalence. Looking at this data, the recorded prevalence of depression seems to be lower in comparison to estimates by the [National Institute of Mental Health (NIMH)](https://www.nimh.nih.gov/health/statistics/major-depression).
This is expected since depression often goes undiagnosed; however this is likely to cause issues as countries with less mental health support may falsely show lower levels of depression. In order to combat this issue, I dropped the columns that don't have the estimated prevalence recorded. However, estimated depression only has data entries for 2015. Because I believe estimated data for depression would be more free from bias, I will be focusing solely on data from 2015.

### Analysis

{% include_relative Visualizations/recprev_ladder.html %} 

Looking at the recorded prevalence of depression vs the happiness ladder score, there seems to be no correlation. However, when we look at the estimated prevalence vs the happiness ladder score, there is strangely a positive correlation between depression prevalence and ladder score. 
Intuitively, one would expect lower levels of depression in countries with higher ladder scores, but this is not the case here. I have to wonder now if I should be looking at the recorded prevalence, as a positive correlation seems strange with happiness and depression. From here I want to see the distribution of the differences between estimated and recorded rates of depression.

{% include_relative Visualizations/prev_dif.html %}

The increase in prevalence seems to be centered around 1%; most country depression estimations increase by 0.5 to 1.5%. This makes the data seem a bit more reliable, since there seems to be an order to how they increased prevalence. 
For now, I will trust the estimated data rather than the data recorded by the countries, as I am very wary of under-reporting/diagnosing of depression. 

Something else strange is that suicide rates are very weakly correlated with depression rates, if at all. 

{% include_relative Visualizations/suicide_depression.html %}

Even when comparing suicide rates with both recorded prevalence and estimated prevalence show very weak correlations. It is also not correlated with the happiness life ladder. After looking at the positive correlation between depression rates and happiness, I wondered if social support affected any part of depression

{% include_relative Visualizations/social_support.html %}

Depression rates seem to stay relatively stable when social support increases. Estimated depression rates increase slightly with social support. Happiness on the other hand is strongly correlated with high social support.

### Conclusion

In regards to the strangeness of depression rates being positively correlated with higher happiness, it may be that higher levels of social support lead to more diagnoses of depression. Since suicide rates don't seem to correlate with depression rates, and depression rates correlate with social support, it may also follow that social support can decrease the rates of suicide. Overall, the general population may be happier, and people with depression may have a better outlook on life due to that social support. 
However, many of these correlations are so weak that no conclusion can be made about this. Other mental illnesses may play a factor in the happiness of a country, and it is hard to know how much of a population has a mental illness. One other explanation for high depression rates in happy countries is that people in that country only believe they are happier. They may have more resources that make them think they're happy, but in reality are struggling with the same or more 
internal problems that everyone around the world struggles with. Happiness and mental illness is hard to track and analyze, but this may provide some insight into happiness and mental health.