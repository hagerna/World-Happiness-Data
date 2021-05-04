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

[Find all my visualizations here](/Martin_Alvarez-Kuglen/Visualizations/)


Initially I found this graph very interesting. It seems to reveal something that I think is not surprising -- that is, the higher the General Life Enjoyment the higher the Social Support Evaluation. Now, the immediate answer most would come to is 'well, social support must increase happiness!' While I find this a compelling explanation, I am curious if we can dig deeper. Could there be an underlying factor that may be illuminated by further analysis of the data?

## Refined Individual Area of Analysis

During this project I will analyze the internal relationships between each variable in the WHR. Read along with me as we see how many nuances can be teased out of the WHR data. We will investigate questions of correlation and lackthereof, we will challenge our assumptions about common conceptions of wealth and happiness, and open our eyes to the visualization of these statistical analyses.

## Can We Trust This Data?

To begin our investigation we must first question the data itself. How do we know it is what WHR claims it to be? Because of the integrety of Gallop and the other professional sources used in WHR, and due to the scope of this analysis, we won't dig into the polling methods of each source. Instead, we will visualize the data wholistically and attempt to find areas of weakness. To begin, let's examine the number of countries included:

{% include_relative Visualizations/Number of countries.html %}

As we can see in this graph, after 2005 the number of countries steadily rises to ~140 and remains there until 2020, where the number of countries drops to 95. This was almost certainly because of COVID, as the WHR notes that [the COVID pandemic has hindered the ability to collect data](https://worldhappiness.report/ed/2021/)

The next question I would like to answer is "Which countries are these, exactly?" It is often the case that Western/developed countries are massively over-represented and it is worth investigating if that is the case here.

{% include_relative Visualizations/WHR_World_representation_choropleth.html %}

This choropleth reveals an unfortunate situation with the data. As is the case with many other datasets, reporting for African countries is significantly less than the rest, with several large countries having ony 2-4 years of representation. Fortunately, it appears that almost all of the Americas is covered, and most of Europe and Asia as well. Overall it appears this data does in fact represent (most) of the world, with Africa yet again being underrepresented.

Finally, I would like to ask "how does this data look? How does it spread?" To answer this question, we can look at violin-box plots of each variable. These plots are useful in indersanding spread, as they have an internal boxplot (representing the 4 quartiles) and an overlayed 'violin' which beautifully visualizes the mass of the data.

For the sake of space I will only include the Life Ladder violin, but please check out [this file for the rest of them!](https://github.com/hagerna/World-Happiness-Data/tree/gh-pages/Martin_Alvarez-Kuglen/violins.md)

{% include_relative Visualizations/WHR_stats_Life Ladder_violin.html %}

Here we can see that the data mostly surround the median of 5.386, and spread out from there to the finer extremes. This indicates a healthy spread of data, as they show a clear somewhat unimodal curve as we would expect from this kind of data. Interestingly, the Log-GDP per capita data appears to show a pronounced bimodal distribution. All data analyzed seems to follow this same patter of unimodal smooth curves with mean and mode approximately matching. This smoothness and bell-like shape indicated these data are in fact taken from a large population of independent individuals.

## Coming Soon!

For the next step of the project correlations will be calculated for each variable and plotted as a heat map. We will choose some strong positive/negative correlations, as well as some un-correlated variables, and visualize these relationships. Depending on what we find, we may seek out additional data or resources to explain our findings. In the end, we will reveal these internal relationships via visualizing statistical analyses and reading primary sources.
