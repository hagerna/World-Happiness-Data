# World Happiness Data Visualization (Linnea Nygren)

I'm initially looking at the countries with the lowest and highest subjective happiness/well-being scores (called ladder score in the dataset) and looking at correlations
between that ladder score and other variables. The ladder score is measured from 0 to 10, 10 being the best possible life you could imagine and 0 being the worst possible life you 
could imagine. 

{% include_relative Visualizations/ladder_extremes.html %}

Denmark has the maximum ladder score recorded and has a pretty steady score that doesn't fluctuate too much. Afghanistan on the other hand, has the lowest recorded ladder score,
and you can see that its ladder score has fluctuated quite heavily over the years, with its highest score being two points above its lowest. This might suggest a trend that countries
with higher scores might fluctuate less as they are mostly stable, however at this point it requires more digging into before any sort of conclusion is made.

{% include_relative Visualizations/freedom_correlation.html %}

Freedom score is measured with the national average of binary responses (0 or 1) to the question "Are you satisfied or dissatisfied with your freedom to choose what you do with your 
life?". 0 means dissatisfied while 1 means satisfied. From this visualization it seems there is a positive correlation between the country's freedom score and their ladder score.
This suggests that freedom to do what one wants is correlated with a higher happiness score. 

