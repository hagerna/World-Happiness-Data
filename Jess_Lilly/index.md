# World Happiness Data Visualization Set (Jess Lilly)



The Global World Happiness Ranking Gallup publishes yearly is based on a single data indicator: life ladder scores determined through something known as the Cantril Index. The Cantril Index is used to rank countries in terms of happiness. Countries are ranked in based on survey responses to a single question: “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?” Countries are ranked by mean life ladder score, with the highest score denoting the happiest country globally, and the lowest score denoting the least happy country globally. I am interested in investigating the validity of the Cantril Index in determining the happiness of a country.

### Statement of Interest

I grew up in Germany, but my first understandings of the United States were shaped though the narrative of my American parents. I was told that the US was the "strongest country in the world, and "the freest country in the world" and that I was lucky to be an American. With so many apparent social and economic assets, the United States should fall pretty high up the happiness ladder, and indeed, the United States does. The United States is admittedly not the _pinnacle_ of happiness on Gallup’s scale, but at 18/153, the United States still fall in the top 12% of countries worldwide.

As I grew older I was exposed to a German perspective on American life — the rest of the world doesn’t see Americans as being as lucky or successful as the narrative my parents fed me as a child would suggest. To the outsider, the United States can seem like a sad, judgmental, dangerous, and divided place. In fact, the American way of life is so seemingly tumultuous and fascinating that what happens in the United States populates German media almost as much as what happens in Germany does. For many Germans, observing the American way of life is a guilty pleasure that I would equate to rubbernecking a train wreck. The day Donald Trump was elected president a German radio station sent reporters into my international school classroom to interview “Die Amerikaner,” the Americans.  For the next hour we answered questions about what it felt like to be an American on the heels of Trump’s election. Our subsequent narrative provided mild morning radio entertainment for middle-aged businessmen on their way to work as we, the Americans, privately contemplated setting our passports on fire. Two years later every single one of us started college in Europe. By the time I left Europe, many of my formerly American classmates had traded in their American citizenship for German citizenship because they saw the best possible life for themselves higher up the Cantril ladder in the EU than in the US.

Now, I don’t say this to imply that Germany is perfect or that the United States is inherently a bad country. A simple glance in a history book will reveal that Germany has a host of its own problems, many of which have had long-lasting social and cultural consequences that continue to negatively affect the country; and in my 18 months in the States I have had plenty of experiences that have made me glad that I did not, in fact, set my American passport on fire; however, my  empirical observation of the dichotomy between how Americans perceive the United States, and how the rest of the world sees the United States makes me question the validity of the Cantril ladder as a measure of happiness. How are we supposed to objectively compare our lives to the lives of the rest of the world? Does thinking we are better off than the rest of the world really mean we are happier, or so we simply _think_ we are comparatively less miserable? Most of us learn about the rest of the world through the knowledge we glean from sensationalized news stories, fictional and reality TV, and, if we’re lucky, limited travel experience to highly specific tourist locations that likely capitalize on the glorification of other cultures as a more primitive “other” than our own to make us feel better about our own position in life. Thus, I would argue that most people are neither well-informed nor objective in gauging their happiness in relation to people in other countries.

Now let’s say the Cantril ladder has validity. As the World Happiness Index gains popularity and media coverage, can the Cantril ladder _continue_ to effectively measure happiness? Finland has received the top spot in the Happiness Ranking for the last 4 years running. While I don’t speak Finnish or frequent Finnish news cites, if I could hazard a guess I would say that Finland’s status as the happiest country in the world probably made local news. Let’s say you live in Finland. You’ve read articles and seen news stories about Finland’s status as the happiest country in the world. You receive phone call from Gallup World Poll data collectors asking you to place your life position relative to the rest of the world on a ladder. Wouldn’t you be inclined to place yourself high on the ladder? Sure, you may be miserable, but misery is relative, so what’s to say the rest rest of the world isn’t just more miserable? After all, data says you live in the happiest country in the world.

Maybe I’m being cynical, but I’m very skeptical of Gallup World Happiness Rankings after reading up on the ranking methodology. Thus, I am interested in exploring other potential indicators of happiness (and misery) to gain a better understanding of whether the Gallup World Happiness Ranking are really measuring happiness, or just perceived happiness.

I will be looking at the correlation between the Gallup World Happiness Ranking and suicide rates, depression rates, and emotional wellbeing of the countries included in our dataset.

I will further attempt to find data about different media styles, freedoms, and narratives globally. I am very interested to see if there is a correlation between the types of media narratives people consume about their country, and their perceived happiness.



## Part A: Can an Individual Objectively Gauge Relative Happiness?

Firstly, I must address the ambiguity of the question asked to construct the Life Ladder Score: “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?”

The question never explicitly explains what the "the best possible life" and "the worst possible life" mean in relation to reality. Based on how the question is asked, the best and worst possible life could well exist only as dystopian or utopian figments of the imagination. However, given a ranking is constructed from the collected responses, I am assuming the Gallup World Happiness Ranking relies on respondents having the self-awareness to objectively report their own happiness relative to the rest of the world. A simple visualization of the Life Ladder scores of all of the countries in the dataset reveal that respondents are most likely not effective gauges of their own happiness.

{% include_relative Visualizations/Figure1_1.html %}

If people could objectively measure their happiness, I would expect a roughly symmetrical bell curve centered at 5. However, as it stands, the happiness scores for a right-skewed distribution and  the mean happiness index score with countries weighted equally is 5.47. Now, it is important to note that the above histogram does not take population size into account. If the histogram was weighted by populations size, the mean would likely be skewed even farther to the right, given of the 10 most populous countries in the world, only India has a 2020 ladder score below 5.0.

Why are people overestimating their happiness? I have no idea. If the reason is universal, then the happiness index would maintain its integrity. Given the vast global differences in culture, lifestyle, education, and media, I'm fairly confident that, while I cannot pinpoint the cause of the overestimation, the overestimations are not evenly distributed across all countries. Thus, Figure 1.1 provides evidence to suggest that the Gallup World Happiness Index is a poor reflection of the actual relative happiness of countries.


## Part B: Correlates of Happiness and Unhappiness

'Happiness' is an ambiguous term. I can't really validate or invalidate a measure of an intangible idea, because there is no delineable or quantifiable measure of happiness. However, I am interested in which of the 'ideas' we broadly associate with happiness, strongly correlate with the World Happiness Index, to determine what the Happiness Ranking is really providing insight into.

Thus, I will be exploring the correlation between the Cantril Ladder scores per country and the positive and negative affect scores, the OECD Better Life Indicators, the suicide rates, and the depression rates, per country.

#### World Happiness Index vs. Positive and Negative Affect

I was interested in whether there was a strong relationship between the ladder score of countries, and their respective positive and negative affects. In the same survey that the Gallup data collectors collected Cantril ladder scores, the data collectors also collected positive and negative affect scores, based on responses to questions asked about the emotions respondents experienced "yesterday". 

{% include_relative Visualizations/Figure2_1.html %}

The visualization suggests there is a very weak association between the positive or negative affect experienced in a country, and the ladder score. Thus, the Cantril Ladder score is likely only weakly correlated to the experience of positive and negative emotions by participants in a given country. However, if happiness is not an emotion in the context of the Cantril ladder happiness ranking, what is the 'happiness' being measured?

#### COMING SOON: World Happiness Index vs. OECD Better Life Indicators

#### COMING SOON: World Happiness Index vs. Suicide and Depression Rates

## Part C: Efficacy Longevity of the World Happiness Index

I suspect that as the World Happiness Index becomes more broadly publicized, the efficacy of the Cantril ladder as a measure of happiness, will decrease. The Cantril ladder relies on human judgement. Media and popular discourse influences human judgement. Generally, I would expect countries that score particularly low, and countries that score particularly high to experience more media coverage with more memorable results. Thus, I would imagine that over time, the variability in the happiness score of some of the highest ranked countries will decrease, as knowledge about previous scores begins to influence responses. 

While I would expect knowledge of ladder scores to similarly affect countries that make the news for having some of the lowest happiness scores, I will _not_ be looking at the lowest scoring countries in the data set -- The countries that rank the lowest on the index show incredible levels of score volatility over time often because of resolving, new, or ongoing conflict, and political and economic instability that would introduce further significant uncontrolled variables into my investigation.

{% include_relative Visualizations/Figure3_1.html %}

{% include_relative Visualizations/Figure3_2.html %}

{% include_relative Visualizations/Figure3_3.html %}

{% include_relative Visualizations/Figure3_4.html %}

{% include_relative Visualizations/Figure3_5.html %}

{% include_relative Visualizations/Figure3_6.html %}

{% include_relative Visualizations/Figure3_7.html %}

{% include_relative Visualizations/Figure3_8.html %}

{% include_relative Visualizations/Figure3_9.html %}


### COMING SOON: Graph with linear regressions

The highest scoring countries on the Cantril Ladder, show the lowest levels of year-to-year score variability. While I cannot draw-cause-effect conclusions, I would suspect that the decrease in year-to-year variability of the top 5 and top 10 countries over time (and less significantly the top 25 over time) is in part due to an increased awareness of ranking influencing participant responses.

## COMING SOON: Part D: How Happy is the US, Really?

