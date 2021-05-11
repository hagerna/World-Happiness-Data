# World Happiness Data Visualization (Nick Hager)


## First Look ##

My initial interest in the dataset is determining how much of the data is usable, for example, after an initial glance I could determine that some countries have entries dating back to 2005 but others do not. In order to accurately compare the data from different countries year to year, it is important to ensure that the countries actually have data to compare and that they have an equal baseline.


{% include_relative Visualizations/Countries_Per_Year.html %}


The data appears to reach a roughly consistent number of countries in 2011 which makes sense as on the [World Happiness Report (WHR) website](https://worldhappiness.report/archive/), the first report was released for 2012, examining the previous year. For this reason, when comparing all the countries together, 2011 will serve as a good baseline year for which all the countries involved have data. It is also worth noting that there is a noticeable drop in the number of countries with data for the year 2020. The authors of the [World Happiness Report (2021)](https://worldhappiness.report/ed/2021/) attribute the difficulties with collecting data to the COVID-19 global pandemic and as a result of this it would be reasonable to exclude the year of 2020 from the data or choose to examine it further separately. I have chosen to include it in my visualizations as they are not entirely oriented around change over time for which the lacking data would have the greatest impact.

\nTwo

## Diving Deeper: Visualizations ##

One question that I am personally interested in is "what is the best way to present as much of the data as possible to the viewer in a way that is both reasonable and helpful?" Continuing to work with the data from the 2021 World Happiness Report, there is a lot of information to manage: roughly 150 different countries, a range of 15 years, and the 9 unique columns with the various factors that contribute to happiness.
To start off, following my earlier observations, we will narrow the data down to 2011-2020 as these years have official published reports implying more consistent and reliable data. This also means the data includes a relatively consistent number of countries (aside from 2020) which can thankfully be displayed in the familiar fashion of global map using [plotly choropleths](https://plotly.com/python/choropleth-maps/). Global choropleths however require geojson codes to connect the data from the countries to the location of the countries on the map which the WHR data did not include. This issue was easily resolved however by merging the WHR with [another dataset](https://github.com/plotly/datasets/blob/master/2014_world_gdp_with_codes.csv) the included the codes and then simply dropping the unneeded columns from the other dataset. 
Using global choropleths, we can better visualize the rest of the data showing the change over time and also the other unique factors the WHR included. To once again clarify what these factors are, the 9 columns included in the WHR are as follows:

1. Life Ladder - Answer to the question: "Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?”
1. Log GDP Per Capita - Log of a country's economic output per person calculated by dividing the gross domestic production (GDP) of a country by its population.
1. Social Support - Measures binary responses (either 1-0) to the question "If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?"
1. Healthy Life Expectancy at Birth - Age based on the World Health Organization's Global Health Observatory data.
1. Freedom to Make Life Choices - Measures binary response to the question "are you satisfied or dissatisfied with your freedom to choose what you do with your life?"
1. Generosity - Based the on answer to the question "Have you donated money to a charity in the past month?" regressed with GDP per capita, capturing the residual of the regression.
1. Perceptions of Corruption - Measures binary responses to two questions: "Is corruption widespread throughout the government or not?" and "Is corruption widespread within businesses or not?"
1. Positive Affect & Negative Affect - two separate columns based on similar questions. Positive Affect measured the responses to the question "did you experience the following feelings during A LOT OF THE DAY yesterday?" with the feelings in question being happiness, enjoyment, and smiles or laughter. Negative Affect measured responses to the same question with the feelings mentioned in the question being worry, sadness, and anger.

In order to visualize this data in a reasonable yet meaningful way, I figured that the best method would be to display a single year and a single factor to the viewer at a time, yet give them control over which year and factor they could view. I planned to implement the years on slider and the factors on a dropdown menu to allow the viewer full control of which global choropleth they would be viewing. This proved to be remarkably more difficult than I had expected.

### Challenges & Difficulties

The major problem with combining sliders and dropdown menus in plotly graphs is the issue of visibility. Each graph can contain multiple traces and ideally a combination of 9 factors with 10 years would result in 90 traces that could theoretically all fit on the same graph. While this part is certainly feasible, the graph should only display the single correct trace at a given time and should be dependent on both the slider and the dropdown selection, for example looking at the Life Ladder Score of all the countries in 2011. However, to determine which trace should be visible, both the slider and dropdown selection rely on separate boolean masks that tell a certain trace to be visible and make all other traces disappear. The problem is that these masks are separate from one another, meaning that moving the slider would have no effect on what the dropdown selector "thinks" it should be displaying. Essentially, this means that instead of a single graph to display everything, we will instead rely on 19, one for each year and one for each factor.

### The Results

Despite our inability to fully compress all of the years and factors into a single visualization, that does not mean the visualizations we are left with are low quality or useless. The visualizations we have created will allow the viewer to look at all factors for a specific year or all the years for a specific factor, and we can further increase the quality of these graphs by taking into account the color and adding annotations. To help distinguish the factors I had each choropleth for a given factor be a distinct color so that the viewer would receive immediate visual feedback when switching between visualizations. The colorscales I chose for each choropleth was based on my own personal favorites that took into account distinct coloration from the other choropleths and also clearly distinguished the countries without data. Additionally, we can provide which country scored the highest and lowest for any particular factor as a helpful annotation for the viewer in the upper-right hand corner of the visualization. Below is where you can find all 19 visualizations sorted by their independent variable.

 Sorted by Year | Sorted by Factor
------ | ------
 [2011](data_by_year/index.md#2011) | [Life Ladder](data_by_factor/index.md#life-ladder) 
 [2012](data_by_year/index.md#2012) | [Log GDP per capita](data_by_factor/index.md#log-gdp-per-capita) 
 [2013](data_by_year/index.md#2013) | [Social Support](data_by_factor/index.md#social-support) 
 [2014](data_by_year/index.md#2014) | [Healthy Life Expectancy at Birth](data_by_factor/index.md#healthy-life-expectancy-at-birth) 
 [2015](data_by_year/index.md#2015) | [Freedom to Make Life Choices](data_by_factor/index.md#freedom-to-make-life-choices) 
 [2016](data_by_year/index.md#2016) | [Generosity](data_by_factor/index.md#generosity) 
 [2017](data_by_year/index.md#2017) | [Perceptions of Corruption](data_by_factor/index.md#perceptions-of-corruption) 
 [2018](data_by_year/index.md#2018) | [Positive Affect](data_by_factor/index.md#positive-affect) 
 [2019](data_by_year/index.md#2019) | [Negative Affect](data_by_factor/index.md#negative-affect) 
 [2020](data_by_year/index.md#2020) |           


## Diving Deeper: Analysis

While the visualizations above are a useful way to see all the data available, it is a lot of information to sort through and may require a significant amount of time and swapping between the different visualizations. In order to provide more useful information that I myself was curious about, I decided to find the overall change and improvement that each country underwent for all the unique factors that the WHR attributes to happiness. Considering what I had noticed previously about the year 2020 and the lack of data on a large number of countries, the year 2011 will serve as our benchmark and we will compare it with the data collected for 2019. In order to do this, we can merge the data from 2019 with the 2011 data and then add new columns that calculate the total change that took place over the 8 years. See the resulting visualization below:

{% include_relative Visualizations/WHR-total_change.html %}

### Issues
There were a few difficulties I encountered when creating this visualization. Deciding what would be the best way to calculate the change took some time as I was initially considering comparing the average across the 8 years to that of the 2011 data, but I decided to simply use the total difference between 2019 and 2011 which may not capture all the ups and downs in the years between but I believe is still useful information. Another issue was centering the colorbar at 0. While most of the graphs had 0 close to the center of the colorbar, Life Expectancy in particular had 0 near the bottom of the color bar which visually conveyed that a vast majority of countries appeared to have a decreasing Life Expectancy when this was not in fact the case.

### Observations
Notably when looking at all the different countries for each category, there is not a particular trend that stands out for the majority of the factors. Most appear to have a balance between countries that improved and countries with scores that decreased with the single exception of Life Expectancy. Looking at the visualization we can tell that Life Expectancy has generally increased for the majority of countries. Log of GDP per capita is another category which the trend shows as increasing. Looking at the data as a whole and what it is meant to convey, it would appear that for a majority of factors the visualizations do not depict a majority increase (or decrease in the case of Perceptions of corruption and Negative affect) that would indicate the world is happier in 2019 than it was in 2011, at least for the 112 countries included in this dataset. Of course, with so many different countries, it is not necessarily surprising that all the countries are not increasing or decreasing together, which could possibly lead to further credibility of the data.

### Further Analysis
While looking at the previous visualization, I realized it did not necessarily inform the viewer as to which countries showed the most improvement. For example, if Country A had a Life Ladder score of 2 and Country B had a Life Ladder score of 0.5, if both countries doubled their score Country A would appear to have increased more as Country B would only increase by 0.5 instead of by 2. While this may be a somewhat specific case, I also wanted to see the percent increase so that a viewer might better understand how much an increase actually meant for individual countries. In order to accomplish this, I repeated the same process as above except I calculated the percent increase by taking the increase, dividing it by the original value, and multiplying that by 100 (increase/original * 100). This visualization yielded some interesting results:

{% include_relative Visualizations/WHR-percent_change.html %}

### Issues & Observations
Many of the graphs show that the countries with the greatest or lowest improvement are the same for both total change and percent change. While the majority of the graphs are interesting yet not particularly striking, the graph for Generosity sticks out like a sore thumb with a maximum of an 8000% increase down to a -2300% decrease. Needless to say, I found this odd and decided to further investigate the two most notable countries in question, Latvia and Panama, to try and find clues as to what may have been resulting in this confusing data. Looking into these two countries, a few things came to my attention. Firstly, the Generosity data from the original dataset for those countries was remarkably noisy, in other words, changed orders of magnitude with no apparent trends and even varied between positive and negative numbers in the case of Panama. Additionally, seeing that Latvia's generosity scores were entirely negative made me question the category of Generosity more closely. You may remember from earlier that the Generosity score is determined by the 'answer to the question "Have you donated money to a charity in the past month?" regressed with GDP per capita, capturing the residual.' It seems obvious that the source of the noise for this data is due to it being "regressed with GDP per capita" as the other questions with binary answers did not have similar issues. Unfortunately, the "residual of a regression" is meaningless to me and so begs the question, why not simply use the answer to the question as was done with the other categories? I believe the reason for regressing it with GDP per capita balances the fact that those who make more money have more money to potentially donate yet it seems as though there may be a better way to analyze Generosity that is not solely based on charity. Regardless, this last visualization reminds us to be critical of our data and dig deeper when we find issues that don't seem to make sense.



If you are interested in further critically investigating the data provided by the [World Happiness Report](https://worldhappiness.report), be sure to check out [Jess Lilly's page](../Jess_Lilly).

If you would like to some other cool visualizations that analyze the individual factors and get a better understanding of the internal relationships of the data collected in the WHR, be sure to check out [Martin Alvarez-Kuglen's page](../Martin_Alvarez-Kuglen).

If you are curious to see how the data from the WHR interacts with data regarding mental health, i.e. depression and suicide rates, then you should check out [Linnea Nygren's page](../Linnea_Nygren).

Or you can return to the [Home Page](../index.md) to explore more yourself.


