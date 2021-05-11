# A Critical Analysis of The *Gallup World Happiness Report*
### *Jess Lilly*




Every year, a country makes headlines for being the "[happiest country in the world](https://www.bbc.com/news/world-europe-56457295)." However, articles about *why* certain countries counsistently occupy the top spots are few and few and far between. The World Happiness Ranking, included in the yearly *[Gallup World Happiness Report](https://worldhappiness.report/ed/2021/),* is based on a single data indicator: Life Ladder Scores determined through something known as the [Cantril Scale](https://news.gallup.com/poll/122453/understanding-gallup-uses-cantril-scale.aspx). The Cantril Scale is used to rank countries in terms of happiness. Countries are ranked in based on survey responses to a single question: “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?” Countries are ranked by mean life ladder score, with the highest score denoting the happiest country globally, and the lowest score denoting the least happy country globally. I am interested in investigating the validity of the Life Ladder Score in determining the happiness of a country. I am further interested in critically investigating the associations between measures of physical and emotional-well-being and the Life Ladder Scores that form the basis of the Gallup World Happiness Rankings.


    



## Statement of Interest

I grew up in Germany, but my first understandings of the United States were shaped though the narrative of my American parents. I was told that the US was the "strongest country in the world, and "the freest country in the world" and that I was lucky to be an American. With so many apparent social and economic assets, the United States should fall pretty high up the happiness ladder, and indeed, the United States does. The United States is admittedly not the *pinnacle* of happiness on Gallup’s scale, but at 18th place out of 153, the United States still fall in the top 12% of countries worldwide.

As I grew older I was exposed to a German perspective on American life — the rest of the world doesn’t see Americans as being as lucky or successful as the narrative my parents fed me as a child would suggest. To the outsider, the United States can seem like a sad, judgmental, dangerous, and divided place. In fact, the American way of life is so seemingly tumultuous and fascinating that what happens in the United States populates German media almost as much as what happens in Germany does. For many Germans, observing the American way of life is a guilty pleasure that I would equate to rubbernecking a train wreck. The day Donald Trump was elected president a German radio station sent reporters into my international school classroom to interview “Die Amerikaner,” the Americans.  For the next hour we answered questions about what it felt like to be an American on the heels of Trump’s election. Our subsequent narrative provided mild morning radio entertainment for middle-aged businessmen on their way to work as we, the Americans, privately contemplated setting our passports on fire. Two years later every single one of us started college in Europe. By the time I left Europe, many of my formerly American classmates had traded in their American citizenship for German citizenship because they saw the best possible life for themselves higher up the Cantril ladder in the EU than in the US.

Now, I don’t say this to imply that Germany is perfect or that the United States is inherently a bad country. A simple glance in a history book will reveal that Germany has a host of its own problems, many of which have had long-lasting social and cultural consequences that continue to negatively affect the country; and in my 18 months in the States I have had plenty of experiences that have made me glad that I did not, in fact, set my American passport on fire; however, my  empirical observation of the dichotomy between how Americans perceive the United States, and how the rest of the world sees the United States makes me question the validity of the Cantril ladder as a measure of happiness. How are we supposed to objectively compare our lives to the lives of the rest of the world? Does thinking we are better off than the rest of the world really mean we are happier, or so we simply _think_ we are comparatively less miserable? Most of us learn about the rest of the world through the knowledge we glean from sensationalized news stories, fictional and reality TV, and, if we’re lucky, limited travel experience to highly specific tourist locations that likely capitalize on the glorification of other cultures as a more primitive “other” than our own to make us feel better about our own position in life. Thus, I would argue that most people are neither well-informed nor objective in gauging their happiness in relation to people in other countries.

Now let’s say the Cantril ladder has validity. As the World Happiness Index gains popularity and media coverage, can the Cantril ladder _continue_ to effectively measure happiness? Finland has received the top spot in the Happiness Ranking for the last 4 years running. While I don’t speak Finnish or frequent Finnish news cites, if I could hazard a guess I would say that Finland’s status as the happiest country in the world probably made local news. Let’s say you live in Finland. You’ve read articles and seen news stories about Finland’s status as the happiest country in the world. You receive phone call from Gallup World Poll data collectors asking you to place your life position relative to the rest of the world on a ladder. Wouldn’t you be inclined to place yourself high on the ladder? Sure, you may be miserable, but misery is relative, so what’s to say the rest of the world isn’t just more miserable? After all, data says you live in the happiest country in the world.

Maybe I’m being cynical, but I’m very skeptical of the *Gallup World Happiness Report*, and the supsequent rankings after reading up on the ranking methodology. Thus, I am interested in exploring other potential indicators of happiness (and misery) to gain a better understanding of whether the *Gallup World Happiness Report* is really measuring happiness, or just perceived happiness based on a limited number of factors.




## Introduction


I will begin my exploration with a brief look at the implication of the spread of Life Ladder Scores, by country. I will further be looking at the association between the Life Ladder Score and six happiness indicators that are highlighted in the *Gallup World Happiness Report*: log GDP per capita, healthy life expectancy, social support, freedom to make life choices, generosity, and perceptions of corruption. I will further be drawing off of two 2017 datasets with global depression rates, and global suicide rates, to determine the association between the Life Ladder Score and emotional wellbeing. Finally, I will try to determine whether the Gallup World Happiness Report becomes increasingly less effective over time, as respondents become influenced by media coverage of their country's happiness.






## Datasets

I use 5 different Datasets for my investigation:

**[2020 World Happiness Report Dataset](https://worldhappiness.report/ed/2020/)** (see "Data for Figure 2.1 for dataset download)

The 2020 World Happiness Report Dataset, contains data exclusively from the year 2019, the most recent pre-pandemic year.

**[Longitudinal World Happiness Report Dataset](https://worldhappiness.report/ed/2021/)** (see "Data Panel" for dataset download)

The Longitudinal World Happiness Report Dataset includes data from 2005 to 2020. The columns are more limited than the 2020 World Happiness Report Dataset, but the range of years allows for longitudinal investigation, while the inclusion of the year 2017 in this dataset allows the data to be merged with the 2017 Global Depression Rates and Suicide Rates datasets with a consistent year used for all data.

**[2017 Global Depression Rates Dataset](https://worldpopulationreview.com/country-rankings/depression-rates-by-country)**

The 2017 Global Depression Rates Dataset includes data about the depression rate in countries around the globe, with country names in Alpha-3 ISO format.

**[2017 Global Suicide Rates Dataset](https://worldpopulationreview.com/country-rankings/suicide-rate-by-country)**

The 2017 Global Suicide Rates Dataset includes data about the suicide rate in countries around the globe, with country names in Alpha-3 ISO format.

**[Alpha-3 ISO Country Code Dataset](https://www.kaggle.com/juanumusic/countries-iso-codes)**

This dataset contains a column that includes full country names, alongside columns with coded country names, including Alpha-3 ISO country codes.

\*\* I made minor alteration to the original CSV file so that all of the counrty names woul merge with theLongitudinal World Happiness Report Dataset, which can be accesses [here](Datasets/Country_Codes.html)

## Part 1: Can an Individual Objectively Gauge Relative Happiness?


The Life Ladder Score question does not explain the “the best possible life” and “the worst possible life” in relation to reality. The best and worst possible life could well exist only as dystopian or utopian figments of participants' imaginations. However, Gallup uses Life Ladder Scores to rank countries' happiness. The country with the highest mean Life Ladder Score ranks the highest in terms of happiness, whilst the country with the lowest mean reported Life Ladder Score, ranks the lowest in terms of happiness. Thus, the *Gallup World Happiness Report* happiness ranking, relies on respondents' self-awareness to objectively report their happiness relative to the rest of the world. 


## Figure 1.1
### 2020 World Happiness Report Happiness Ladder Score Distributions


My preliminary investigation looks at the spread of Life Ladder Scores reported globally. If respondents' can objectively measure their happiness, a histogram of the global spread of Life Ladder Scores should be centered at 5.

{% include_relative Visualizations/Figure1_1.html %}

The above histogram suggests that respondents are not accurate gauges of their relative happiness. The mean Life Ladder globally, with country score weighted equally, is 5.47. Based on the histogram above, respondents are overestimating their happiness by an average of 0.47 out of 10, or about 4.7%.

However, the histogram does not take population size into account. If the histogram was weighted by populations size, the mean would likely be skewed even farther to the right, because, of the 10 most populous countries in the world, only India has a 2020 ladder score below 5.0. The 3.1 billion people in the the other 9 most populous countries in the world would significantly pull the mean above 5.0.

Why are people overestimating their happiness? I have no idea. If the reason is universal, then the happiness index maintains its integrity. Given vast global differences in culture, lifestyle, education, and media, I’m fairly confident that the overestimations are not evenly distributed across all countries. Thus, Figure 1.1 provides evidence to suggest that the *Gallup World Happiness Report* is a poor reflection of the relative happiness of countries.




## Part 2: Correlates of Happiness and Unhappiness


The "Life Ladder" question does not include the word "happiness." Happiness’ is an ambiguous term. I can’t outright validate or invalidate the Life Ladder Score because there is no concrete measure of happiness. However, I am interested in whether there are associations between the Life Ladder Scores of countries and conventional western ideas of happiness. Merriam Webster defines [happiness](https://www.merriam-webster.com/dictionary/happiness) as "a) a state of well-being and contentment : JOY" and  "b) a pleasurable or satisfying experience." Notice, Merriam Webster used one subjective term, "joy," to describe another, "happiness." So, of course, I also had to look up the definition of [joy](https://www.merriam-webster.com/dictionary/joy): "a) the emotion evoked by well-being, success, or good fortune or by the prospect of possessing what one desires : DELIGHT" and "b) the expression or exhibition of such emotion : GAIETY." I quickly realized that if I looked up every word used to describe "happiness" I would be stuck definition-for days. 

Nonetheless, my short definition-dive gave me a good springboard to investigate correlates of the Gallup World Happiness Ranking -- the western idea of 'happiness' includes components of well-being, contentment, pleasurable experiences, (positive) emotion, success, good-fortune, and possessing what one desires.


## Section 2A: Happiness and Positive Emotions


The term happiness carries emotional connotations. Thus, I would expect an effective measure of world happiness to correlate strongly with the positive and negative emotional experiences or survey respondents. I therefore, visualized the association between the Life Ladder Scores of countries and the positive and negative affect scores of countries ([affect](https://www.merriam-webster.com/dictionary/affect): *noun* "the conscious emotion that occurs in reaction to a thought or experience"). 

Gallup collects positive and negative affect scores in the same survey used to collect Life Ladder Scores. The positive and negative affect scores are based on responses to questions asked about the emotions respondents experienced “yesterday.”


## Figure 2.1
### Life Ladder Scores and Positive and Negative Affect Scores


{% include_relative Visualizations/Figure2_1.html %}


The visualization suggests there is a very weak association between the Life Ladder Score, and Positive and Negative Affect. Thus, the Life Ladder Score is likely only weakly correlated to the emotional experience of happiness. However, if happiness is not an emotion in the context of the Life Ladder happiness ranking, what is the ‘happiness’ being measured?




## Section 2B: Life Ladder Scores and Gallup Correlates of Happiness


The *Gallup World Happiness Report* identifies six prominent correlates of happiness: log GDP per capita, healthy life expectancy, social support, freedom to make life choices, generosity, and perceptions of corruption. The 2020 World Happiness Report includes data on each correlate for countries included in the dataset. I wanted to visualize the associations between the six correlates of happiness that Gallup identified, and the Life Ladder Score of countries. Thus, I created scatterplots of the data associations, with Life Ladder Scores along the x-axis, and correlate scores along the y-axis. The correlates are each reported on a different scale, so direct numerical comparisons cannot be made. Nonetheless, the shape and spread of the points of each scatterplot provides insight into the strength and direction of associations.


## Figure 2.2
### Life Ladder Scores and Gallup Correlates of Happiness
#### *2020 World Happiness Report Data*


{% include_relative Visualizations/Figure2_2.html %}


The strength of the association between Life Ladder and Gallup Correlate of Happiness in order from strongest to weakest are roughly as follows:

1. Logged GDP per Capita (strong positive association)
2(T). Healthy Life Expectancy (moderate positive association)
2(T). Social Support (moderate association)
4. Freedom to Make Life Choices (weak positive association)
5. Perceptions of Corruption (weak association)
6. Genorosity (no association)

The strongest association appears to be the positive association between Logged GDP per Capita and Life Ladder Score, while the weakest association appears to be the lack of an association between Logged GDP per Capita and Generosity. While the six Gallup orrelates of happiness appear to have some association to the Life Ladder Scores, most of the associations are moderate, at best. Looking at the data, I noticed that GDP, a capitalistic value, appears to have the highest correlation to Life Ladder Scores. Generosity, which defies western individualism has the lowest correlation to Life Ladder Scores. The stronger association I observed between what I would consider to be western values, and the Life Ladder Score, prompted a couple of questions for further investigation: 1) Is the Life Ladder Score a better measure of western ideas of happiness, or are capitalistic values just more likely to make people happier? 2) Is wealth just a better indicator of happiness than other less economically-driven factors or does the method of Life Ladder Scoring just result in GDP carrying a heavier weight in constructing a happiness ranking? 

In the 2020 World Happiness Report Dataset, Gallup published information about the strength of the association between the Ladder Score and the six gallup correlates of happiness. The Gallup correlates were selected to provide some insight into why some countries ranked where they did on the World Happiness Ranking. It is important to note however, that the correlates had no influence on the Life Ladder Score. The correlates were simply used to conjecture explanations for differences in ladder scores between countries. 

Gallup assigned correlates an "explained" value, which can be taken out of the overall Ladder score of a country to determine the proportion of the Ladder Score explained by the correlate. I was interested in how geographical region and culture affected the proportion of a countries' Ladder Score explained by the Gallup happiness correlates. Thus, I decided to create a choropleth to model the proportion of the Life Ladder Score explained by Gallup correlates of happiness, by country.

I started by determining the proportion of each countries' Life Ladder Score explained by Gallup correlates of happiness in 2019. The proportions were added to the df_happiness_2020 dataset. I then merged the df_happiness_2020 dataset with a dataset of country codes, so that each country name was also given an Alpha-3 country code. The Alpha-3 country code is used by plotly to create a choropleth map. Each country code corresponds to a country's location on the generated map. 

Not all country names were identical in the merge. I thus, used pandas to determine which countries from the df_happiness_2020 dataset failed to merge, and I went into the csv file and changed their names manually to facilitate the merge.

Once the merge was complete, I used plotly express to create a chorpleth map of the proportion of a country's ladder score explained by Gallup's Correlates of Happiness.


## Figure 2.3
### Mapping the Proportion of Ladder Score Explained by Gallup Correlates of Happiness
#### *2020 World Happiness Report Data*


{% include_relative Visualizations/Figure2_3.html %}

The six Gallup correlates of happiness are fairly good predictors of the Life Ladder Scores of most North America, Southern Asia, European, and Australian, countries. The Gallup Correlates are far less predictive of the Ladder Scores of South American, North Asian, and African countries.

I would theorize that the geographical pattern identified may stem from the fact that Gallup is an American company. Thus, the western-centricity of the correlations found make sense if Gallup is trying to explain American happiness data. North America, Southern Asia, Europe, and Australia generally tend towards more western values and more capitalistic systems. Thus, if the World Happiness Index methodology and correlations were devised in the United States, or for the United States, the findings would likely be more compelling for cultures and economies similar to the Unites States.


## Section 2C: Life Ladder Scores and Emotional Well-Being

In light of my theory that the data might disproportionately reflect western wealth-driven ideas of happiness, I decided to do some digging into the mental health of respondents in various countries. I was hoping to further investigate whether the Life Ladder method of Happiness Ranking disproportionately represented the role of wealth on happiness. Therefore, I looked at the association between Life Ladder Score and depression and suicide rates. I could only find complete datasets with depression and suicide rates per country for the year 2017, so I extracted the 2017 data from the Longitudinal Happiness data set so that the year was consistent for a data used.


## Figure 2.4
### Life Ladder Score and Depression Rates
#### *Uses 2017 Data from the 2020 World Happiness Report Data and 2017 Global Depression Data*


{% include_relative Visualizations/Figure2_4.html %}


I once again merged datasets using Alpha-3 country codes as my reference. I used the merged datasets to create dot plots of the association between Life Ladder Score and suicide and depression rates.


## Figure 2.5
### Life Ladder Score and Suicide Rates
#### *Uses 2017 Data from the 2020 World Happiness Report Data and 2017 Global Suicide Data*


There is no evident correlation between Life Ladder Scores and depression or suicide rates. The absence of an association would suggest that the 'happiness' measured by the Life Ladder is very economically driven, and less grounded in mental health of emotional happiness. This theory is further supported by the lack of a strong association between Life Ladder Score and affect. The Life Ladder Score seems to be a fairly good measure of physical and material well-being. The Life Ladder Score is strongly correlated with GDP per Capita and Life Expectancy. However, the Life Ladder scoring falls short in predicting the mental health and the emotional happiness of a country. 




## Part 3: The Longevity of the Efficacy of the World Happiness Index


I suspect that as the World Happiness Index becomes more broadly publicized, the efficacy of the Cantril ladder to produce a Life Ladder as a measure of happiness, will decrease. The Life Ladder Score relies on human judgement. Media and popular discourse influence human judgement. Generally, I would expect countries that score particularly low, and countries that score particularly high to experience more media coverage with more memorable results. I would imagine that over time, the variability in the happiness score of some of the highest ranked countries will decrease, as knowledge about previous scores begins to influence responses.

While I would expect knowledge of ladder scores to similarly affect countries that make the news for having some of the lowest happiness scores, I will not be looking at the lowest scoring countries in the data set – The countries that rank the lowest on the index show incredible levels of score volatility over time often because of resolving, new, or ongoing conflict, and political and economic instability that would introduce further significant uncontrolled variables into my investigation.

To test my hypothesis, I created lists with the top 5, top 10, top 25, and all countries, from the 2019 World Happiness Ranking. I used the Longitudinal Dataset to determine the change in Ladder Score over time, to see if the ladder scores of the top scoring counrties varied less, on average, than the average variation for all countries. I started by visualizing the Life Ladder Scores over time.

{% include_relative Visualizations/Figure3_1.html %}

{% include_relative Visualizations/Figure3_2.html %}

{% include_relative Visualizations/Figure3_3.html %}

{% include_relative Visualizations/Figure3_4.html %}

The preliminary visualization suggested that the top-scoring countries became increasingly less variable in score, over time, while the average change for all countries remained relatively stable. However, I needed more visualization to verify my observation. I decided to visualize the absolute value in change in life ladder from the previous year for each of my top-country lists, and for all of the countries in the dataset. To do so, I needed to fill in missing values in my dataset. I  converted the Longitudinal Happiness Dataset into a pivot table to assign missing values the value of 'NaN'. I then used interpolation to populate the 'NaN' data with values that could be visualized. I then used the .diff(periods=1) function to calculate the difference in Ladder Score from the previous year for a given country. I converted my data back into an unindexed dataframe and took the absolute value of my differences. I then visualized the absolute change in life ladder from previous year over time.


{% include_relative Visualizations/Figure3_5.html %}

{% include_relative Visualizations/Figure3_6.html %}

{% include_relative Visualizations/Figure3_7.html %}

{% include_relative Visualizations/Figure3_8.html %}


## Figure 3.9
### Average Change in Life Ladder From Previous Year, Over Time


{% include_relative Visualizations/Figure3_9.html %}

My visualizations again, suggested that the top-scoring countries became increasingly less variable in score, over time, while the average change for all countries remained relatively stable. I wanted to understand the differences numerically, so I calculated the slope of a linear regression line for the average absolute change in life ladder from previous year, over time.


## Figure 3.10
### Linearly Modeling the Difference in Change in Life Ladder From Previous Year, Over Time


{% include_relative Visualizations/Figure3_10.html %}


As evidenced by the above visualization, the top scoring countries became increasingly less variable in score over time, while the mean variability in score for the average of all countries in the dataset remained at roughly zero. The highest scoring countries on the Cantril Ladder, show the lowest levels of year-to-year score variability. While I cannot draw-cause-effect conclusions, I would suspect that the decrease in year-to-year variability of the top 5 and top 10 countries over time (and less significantly the top 25 over time) is in part due to an increased awareness of ranking influencing participant responses.

## Conclusion

The Gallup World Happiness Index is undoubtedly flawed. Firstly, the Gallup World Happiness Index constructs happiness rankings based on a question that relies on respondents being self-aware enough to place themselves on a ladder relative to the rest of the world. We as humans, have proven time and time again that we are terrible judges of our own position in life. For example, [we can’t all be better and yet, we somehow think we are](https://bobsullivan.net/gotchas/illusory-superiority-everyone-cant-be-above-average-where-are-your-blind-spots/). Why would our personal gauge of our life position be a good judge of *anything*? Especially considering many people have never left their home country and who only know “the rest of the world” from limited access to media or history books. I have shown through a simple distribution of Happiness Index Scores by country, that our judgement is off. If average is 50%, 54% of the world can’t have a life that’s better than average. Once population size is considered, we would be looking at 60-70% of the world thinking their life was above average.

However, I will admit, perhaps the Life Ladder Scale is not supposed to be a measure of average or relativity. The Cantril Ladder question asks for people to pick a number on a scale of 1-10 on a ladder where 10 represents the best possible life. In theory, if everyone had a perfect life, everyone would be able to say 10 with no qualms. But ‘best’ has no ceiling, and some people will always have more than other people, so I will default again to the concern that Life Ladder Scores that form the basis of country world happiness rankings rely on people having a self-awareness of how their lives compare to other people’s lives for an effective comparison to work.

Next, I would argue that the World Happiness Index is not reporting happiness, at least not in the emotional satisfaction sense. All of the emotional and mental-health indicators of happiness in this investigation showed little to no correlation with Life Ladder Score. The economic and physical well-being indicators such as GDP and life expectancy however, were strongly or moderately correlated with Life Ladder Scores. Additionally, factors Gallup consider to be important in shaping the Ladder Scores are far more correlated with western countries, than with non-western countries suggesting that the Gallup World Happiness Index is distinctly Eurocentric in design.

Finally, the Gallup World Happiness Index is only effective as long as the results remain poorly disseminated. Increased awareness of ranking may be influencing participant responses, as suggest by the increasingly homogenous Life  Ladder scores of the top 5, 10, and 25 countries over time.


