# World Happiness Data Visualization (Linnea Nygren)

I'm interested in how mental health plays a role in a country's happiness. I would have to guess that countries that have a higher ladder score would potentially have lower rates of depression/suicide, or at least more support for mental health. For this, I'll be looking at a secondary dataset alongside the world happiness dataset.
This dataset from [Our World in Data](https://ourworldindata.org/mental-health) shows the prevalence of depression as recorded by the World Health Organization. 

{% include_relative Visualizations/ladder_extremes.html %}

Denmark has the maximum ladder score recorded and has a pretty steady score that doesn't fluctuate too much. Afghanistan on the other hand, has the lowest recorded ladder score,
and you can see that its ladder score has fluctuated quite heavily over the years, with its highest score being two points above its lowest. This might suggest a trend that countries
with higher scores might fluctuate less as they are mostly stable, however at this point it requires more digging into before any sort of conclusion is made.

{% include_relative Visualizations/freedom_correlation.html %}

Freedom score is measured with the national average of binary responses (0 or 1) to the question "Are you satisfied or dissatisfied with your freedom to choose what you do with your 
life?". 0 means dissatisfied while 1 means satisfied. From this visualization it seems there is a positive correlation between the country's freedom score and their ladder score.
This suggests that freedom to do what one wants is correlated with a higher happiness score. 

