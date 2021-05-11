# World Happiness Data Visualization: (Martin Alvarez-Kuglen)

## Intro & Background ##
Hi and welcome to my page! My name is Martin (pronounced Mar-teen) and I am interested in understanding the internal relationships between the data collected in these reports. When doing research for this project, I came across the World Happiness Report (WHR) dataset and found myself asking so many questions: What were the categories of data collected? How did these categories get chosen? What can they reveal about our society? Are there ways the data may be biased towards particular cultures?

As it turns out, this particular dataset has categories that are meta-analysis of more specific questions. Some questions are directly taken from response data, but it appears the positive/negative affect columns are derived from data not accessible to the public. The dataset is relatively simple, with columns corresponding to country sorted by year. For each of these categories data is displayed for the following: "Life Ladder",	"Log GDP per capita",	"Social support",	"Healthy life expectancy at birth",	"Freedom to make life choices",	"Generosity",	"Perceptions of corruption",	"Positive affect" and	"Negative affect".

To understand the kinds of questions addressed in this report, let's focus on the big one: "Life Ladder." To determine this, the WHR takes data from Gallup, wherein respondents are asked a simple question: 
"Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?"
The answers from all respondents of a particular country are then gathered and the ladder is given as their average. As is clear, these questions are quite open ended, leaving much up to the respondent's perception. This makes sense, however, as happiness itself is a subjective measure. Therefore this technique powerfully captures the subjective experience of the people.

We all have assumptions about what the data will show. I think most people assume high GDP will be linked to high happiness. But is this true? If so, why is it true? Are there more internal relationships we can pull out of the data to gain a better understanding?

For my first visualization I have created a scatter plot of Life Ladder and Social Support (here I call them 'General Life Enjoyment' and 'Social Support Evaluation' as those seem like more informative descriptions).

{% include_relative Visualizations/SocSupport_v_LifeLadder.html %}

[Find all my visualizations here](Visualizations)


Initially I found this graph very interesting. It seems to reveal something that I think is not surprising -- that is, the higher the General Life Enjoyment the higher the Social Support Evaluation. Now, the immediate answer most would come to is 'well, social support must increase happiness!' While I find this a compelling explanation, I am curious if we can dig deeper. Could there be an underlying factor that may be illuminated by further analysis of the data?

## Refined Individual Area of Analysis

During this project I will analyze the internal relationships between each variable in the WHR. Read along with me as we see how many nuances can be teased out of the WHR data. We will investigate questions of correlation and lackthereof, we will challenge our assumptions about common conceptions of wealth and happiness, and open our eyes to the visualization of these statistical analyses.

## Can We Trust This Data?

To begin our investigation we must first question the data itself. How do we know it is what WHR claims it to be? Because of the integrety of Gallop and the other professional sources used in WHR, and due to the scope of this analysis, we won't dig into the polling methods of each source. Instead, we will visualize the data wholistically and attempt to find areas of weakness. To begin, let's examine the number of countries included:

{% include_relative Visualizations/Number_of_countries.html %}

As we can see in this graph, after 2005 the number of countries steadily rises to ~140 and remains there until 2020, where the number of countries drops to 95. This was almost certainly because of COVID, as the WHR notes that [the COVID pandemic has hindered the ability to collect data](https://worldhappiness.report/ed/2021/)

The next question I would like to answer is "Which countries are these, exactly?" It is often the case that Western/developed countries are massively over-represented and it is worth investigating if that is the case here.

{% include_relative Visualizations/WHR_World_representation_choropleth.html %}

This choropleth reveals an unfortunate situation with the data. As is the case with many other datasets, reporting for African countries is significantly less than the rest, with several large countries having ony 2-4 years of representation. Fortunately, it appears that almost all of the Americas is covered, and most of Europe and Asia as well. Overall it appears this data does in fact represent (most) of the world, with Africa yet again being underrepresented.

Finally, I would like to ask "how does this data look? How does it spread?" To answer this question, we can look at violin-box plots of each variable. These plots are useful in indersanding spread, as they have an internal boxplot (representing the 4 quartiles) and an overlayed 'violin' which beautifully visualizes the mass of the data.

For the sake of space I will only include the Life Ladder violin, but please check out [ the rest of them!](violins)

{% include_relative Visualizations/WHR_stats_Life_Ladder_violin.html %}

Here we can see that the data mostly surround the median of 5.386, and spread out from there to the finer extremes. This indicates a healthy spread of data, as they show a clear somewhat unimodal curve as we would expect from this kind of data. Interestingly, the Log-GDP per capita data appears to show a pronounced bimodal distribution. All data analyzed seems to follow this same patter of unimodal smooth curves with mean and mode approximately matching. This smoothness and bell-like shape indicated these data are in fact taken from a large population of independent individuals.

## Final Analysis Section
### Finding Correlations
To begin this journey through our dataset we interrogated the integrity of the data, and visualized some key elements that will be expanded upon here.

Our first step to understanding internal relationships will be the plotting of [Pearson correlation values](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient) on a heatmap plot. This will allow a clean way to visualize the relationships between each variable. In short, Pearson correlation values provide a standard way to assess the strength of the relationship between two variables in a dataset. To do this we will need to utilize some python coding. For my code, I utilized the pandas DataFrame method .corr to create correlation values. By iterating through each variable, treating it as a column or row in a 2D array, I was able to constuct another pandas DataFrame. This was plotted via the plotly express .imshow visualization. This created the heatmap you see below:

{% include_relative Visualizations/WHRHeatmap_table.html %}

In this table, the darker the blue the greater the positive correlation, the darker the red the greater the negative correlation, and the more white/uncolored the less of any correlation. The dark blue diagonal represents the self-correlation line, where the Pearson coefficient is 1. 

According to the website [statisticssolutions.com](https://www.statisticssolutions.com/) a ['strong' Pearson coefficient value is anything of magnitude 0.5 or higher](https://www.statisticssolutions.com/pearsons-correlation-coefficient/#:~:text=High%20degree%3A%20If%20the%20coefficient,to%20be%20a%20small%20correlation.). Therefore, these analyses will use this threshold as the starting point for identifying stronger internal relationships in the data. Below you will find the summary of all internal relationships with greater than 0.5 magnitude Pearson coefficient:

Life Ladder and Log GDP per capita share a pearson correlation coefficient of 0.72.

Life Ladder and Social support share a pearson correlation coefficient of 0.62.

Life Ladder and Healthy life expectancy at birth share a pearson correlation coefficient of 0.66.

Life Ladder and Positive affect share a pearson correlation coefficient of 0.51.

Log GDP per capita and Social support share a pearson correlation coefficient of 0.56.

Log GDP per capita and Healthy life expectancy at birth share a pearson correlation coefficient of 0.78.

Freedom to make life choices and Positive affect share a pearson correlation coefficient of 0.56.

Interestingly, there are no negative correlations that appear to be in this category. The most notable negative correlations being:

Social Support and Negative affect share a pearson correlation coefficient of -0.28.

Negative affect and Positive affect share a pearson correlation coefficient of -0.30.

I found this very interesting, as I couldn't immediately think of any explanation as to why the statistics would favor positive relationships much more heavily than negative relationships. However, this actually does make sense. If you pay attention to the questions addressed by each column, they are are mostly positive measurements of variables we expect to be positively correlated with 'Happiness', With some exceptions of course. For instance, 'Social support', 'Healthy life expectancy', Log GDP per capita, 'Freedom to make life choices', and 'Generosity' are all a positive way of phrasing 'lack of social support', 'unHealthy life expectancy', 'Lack of freedom to make life choices', and 'Lack of generosity'. This explains the extrememly strong bias in that particular direction, and exposes how the questions data scientists ask are just as important as the correlations we find.

To drive this point home further, I created scatter plots to interrogate the data fully. These were generated via a for loop which automated the process of generating plotly express scatterplots. If you would like to see all of them, [please find them all here.](scatterplots) As an example, let's investigate the strongest correlation:

{% include_relative scatterplots/Visualizations/Life_Ladder_v_Healthy_life_expectancy_at_birth.html %}

This is a great example of a positive correlation. You see the data consistently has a positive trendline, but is scattered evenly around it. Interestingly, one of the correlations appears to have smaller lines that are emergent when graphed in this way. See the first graph below:

{% include_relative scatterplots/Visualizations/Log_GDP_per_capita_v_Social_support.html %}

Notice the small lines connecting the dots -- they aren't uniformly scattered around the line. That indicates that there may be some more complex relationship at play. Compare this to the graph below, which has the same variable on the X axis:

{% include_relative scatterplots/Visualizations/Log_GDP_per_capita_v_Healthy_life_expectancy_at_birth.html %}

Unfortunately for the scope of this class I won't have time to investigate this further. But we see, yet again, the importance of visualizing data and assessing it. From a mere R-value this would have gone completely unnoticed, yet here we can clearly see some complex internal relationships at play.

### Some New Data?
To complexify this analysis, let's pull in a new dataset and see if the variables we have identified above have any more interesting relationships. For this, we will use the dataset ["Country Statistics - UNData"](https://www.kaggle.com/sudalairajkumar/undata-country-profiles?select=country_profile_variables.csv) which directly collects data from the [UN's API (I didn't even know this was a thing! So cool that the UN has a public API for data collection.)](http://data.un.org/Host.aspx?Content=About) I used the merge method for pandas dataframes to combine the WHR dataset with the UN dataset. Unfortunately, this data was only for a single year. Therefore, we will have to treat these single data points as constant and won't be able to see changes over the years. This shouldn't hinder statistical analysis though.

Now let's go through the same process as above to create a new heatmap table of correlations, this time between the new variables and the strongly correlated variables found above. Using the exact same approach, we find the table below:

{% include_relative Visualizations/WHR_UN_merged_Heatmap_table.html %}

Using the same threshold value of 0.5 magnitude we find that the table above gives:

Life Ladder and GDP per capita (current US$) share a pearson correlation coefficient of 0.58.

Life Ladder and Economy: Agriculture (% of GVA) share a pearson correlation coefficient of -0.55.

Life Ladder and Economy: Services and other activity (% of GVA) share a pearson correlation coefficient of 0.57.

Life Ladder and Employment: Agriculture (% of employed) share a pearson correlation coefficient of -0.58.

Life Ladder and Employment: Services (% of employed) share a pearson correlation coefficient of 0.62.

Life Ladder and Urban population (% of total population) share a pearson correlation coefficient of 0.64.

Life Ladder and Fertility rate, total (live births per woman) share a pearson correlation coefficient of -0.55.

Life Ladder and Infant mortality rate (per 1000 live births share a pearson correlation coefficient of -0.58.

Life Ladder and Mobile-cellular subscriptions (per 100 inhabitants).1 share a pearson correlation coefficient of 0.62.

Life Ladder and Pop. using improved sanitation facilities (urban/rural, %) share a pearson correlation coefficient of -0.5.

Social support and Employment: Services (% of employed) share a pearson correlation coefficient of 0.51.

Social support and Infant mortality rate (per 1000 live births share a pearson correlation coefficient of -0.54.

Notice the even mix of negative and positive correlations. I think this ties in very nicely with our finding earlier, and shows that when the 'questions' aren't biased in one direction or the other, we end up with a random mix of positive and negative correlations.

Let us again peer into these relationships by visualizing them on scatterplots, taking the strongest correlation as an example:

{% include_relative scatterplots/Visualizations/Life_Ladder_v_Urban_population_(_of_total_population).html %}

This is another great example of a positive correlation. You see the data consistently has a positive trendline, but is scattered evenly around it. This indicates that the trend is real and that the data are, at this stage, looking good. Interestingly, some plots showed pretty significant outliers/discontinuity in the data. For example, look at this graph below

{% include_relative scatterplots/Visualizations/Log_GDP_per_capita_v_Social_support.html %}

Notice the outliers at the top right of the graph. And again in the graph below, look at the bottom left:

{% include_relative scatterplots/Visualizations/Life_Ladder_v_Employment_Services_(_of_employed).html %}

Here we are seeing signs of the data being suspicious. If we wanted to be sure this data is clean, we would need to interrogate how the API was responding to these pull requests. It is often the case that APIs will fill in data or give weird errors when not programmed properly. I suspect the first outliers are due to incredibly high earning countries which just blow away the rest in the GDP. As for the bottom, I don't have a good explanation as to what the source of the outliers is.

### Conclusions
Now that we have fully assessed the relationships, what are the final conclusions we can draw? One way to draw conclusions from data such as this is through R-squared values. These take Pearson correlation coefficients and turn them into percentages [which can roughly answer "How much of the variation in variable X does variable Y explain?"](https://statisticsbyjim.com/basics/correlations/)

Life Ladder and Log GDP per capita share a R-squared value of 52%.

Life Ladder and Social support share a R-squared value of 38%.

Life Ladder and Healthy life expectancy at birth share a R-squared value of 44%.

Life Ladder and Positive affect share a R-squared value of 26%.

Log GDP per capita and Social support share a R-squared value of 31%.

Log GDP per capita and Healthy life expectancy at birth share a R-squared value of 60%.

Freedom to make life choices and Positive affect share a R-squared value of 31%.

Life Ladder and GDP per capita (current US$) share a R-squared value of 34%.

Life Ladder and Economy: Agriculture (% of GVA) share a R-squared value of 30%.

Life Ladder and Economy: Services and other activity (% of GVA) share a R-squared value of 32%.

Life Ladder and Employment: Agriculture (% of employed) share a R-squared value of 34%.

Life Ladder and Employment: Services (% of employed) share a R-squared value of 38%.

Life Ladder and Urban population (% of total population) share a R-squared value of 41%.

Life Ladder and Fertility rate, total (live births per woman) share a R-squared value of 30%.

Life Ladder and Infant mortality rate (per 1000 live births share a R-squared value of 34%.

Life Ladder and Mobile-cellular subscriptions (per 100 inhabitants).1 share a R-squared value of 38%.

Life Ladder and Pop. using improved sanitation facilities (urban/rural, %) share a R-squared value of 25%.

Social support and Employment: Services (% of employed) share a R-squared value of 26%.

Social support and Infant mortality rate (per 1000 live births share a R-squared value of 29%.


If we hone in on the top results we find: 

1) 60% of the variation in Healthy life expectancy at birth can be explained by changes in Log GDP per capita.

2) 52% of the variation in Life Ladder can be explained by Log GDP per capita.

3) 44% of the variation in Life Ladder can be explained by Healthy life expectancy at birth.

It is important to note that correlation does not equal causation. That is, R-squared can tell you how much you can expect one variable to change based on another, but it can't tell you why. Regardless, it is clear from the results above that GDP per capita massively affects the happiness of countries, as measured by the World Happiness Report. We see that it is directly a variable in the first and second strongest links, and it is directly related to the third via the first. Therefore, I think it is safe to say money doesn't buy happiness, but it is correlated with it.