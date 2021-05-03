# World Happiness Data Visualization (Linnea Nygren)

I'm interested in how mental health plays a role in a country's happiness. I would have to guess that countries that have a higher ladder score would potentially have lower rates of depression/suicide, or at least more support for mental health. For this, I'll be looking at a secondary dataset alongside the world happiness dataset.
This dataset from [Our World in Data](https://ourworldindata.org/mental-health) shows the prevalence of depression as recorded by the World Health Organization. 

**Encountered Issues**
Since these datasets are not standardized in any way, I have run into a couple of problems so far. In the world happiness ranking dataset, there are lots of missing entries in the beginning couple of years data is recorded as well as missing entries for 2020 most likely due to the pandemic. On the mental health dataset,
many years are included that have no data whatsoever, such as years in the 1960's and 70's. For the latter issue, I have simply chosen to not include those years with no actual recorded prevalence data, as they contribute nothing to begin with. On the other hand,
the world happiness ranking dataset is a bit more complicated, as some countries have recorded data for a year while others do not. Going off of Nick's idea, I will be starting that dataset from 2011 onwards since that is when the data starts to become more consistent.

{% include_relative Visualizations/mentalhealth_boxplot.html %}
After dropping the columns with no prevalence data, here is the worldwide distribution of depression prevalence. Looking at this data, the recorded prevalence of depression seems to be lower in comparison to estimates by the [National Institute of Mental Health (NIMH)](https://www.nimh.nih.gov/health/statistics/major-depression).
This is expected since depression often goes undiagnosed; however this is likely to cause issues as countries with less mental health support may falsely show lower levels of depression. In order to combat this issue, I dropped the columns that don't have the estimated prevalence recorded instead. This time, only data for 2015 shows up. For now, this means I will be focusing solely on data from 2015, possibly widening my scope if I find a more suitable dataset.

{% include_relative Visualizations/ladder_extremes.html %}

Denmark has the maximum ladder score recorded and has a pretty steady score that doesn't fluctuate too much. Afghanistan on the other hand, has the lowest recorded ladder score,
and you can see that its ladder score has fluctuated quite heavily over the years, with its highest score being two points above its lowest. This might suggest a trend that countries
with higher scores might fluctuate less as they are mostly stable, however at this point it requires more digging into before any sort of conclusion is made.

{% include_relative Visualizations/freedom_correlation.html %}

Freedom score is measured with the national average of binary responses (0 or 1) to the question "Are you satisfied or dissatisfied with your freedom to choose what you do with your 
life?". 0 means dissatisfied while 1 means satisfied. From this visualization it seems there is a positive correlation between the country's freedom score and their ladder score.
This suggests that freedom to do what one wants is correlated with a higher happiness score. 

