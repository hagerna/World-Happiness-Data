# World Happiness Data Visualization Set

### Here we analyze and display the world happiness data from the [World Happiness Report (2021)](https://worldhappiness.report/ed/2021/).

Team members:
<!--
* [Jess Lilly](Jess_Lilly): Focused on critical analysis of the World Happiness Report data in regard to how they collected it and the actual effectiveness of the measurements that they used. Interested in the question, 'how did the World Happiness Report collect their data and how effective are the factors they chose in actually determining happiness?'
-->
* [Nick Hager](Nick_Hager): Focused on the question 'what is the best way to present as much of the data as possible to the viewer?' This naturally leads to broader comparisons of all countries for both the years and unique columns in the 2021 dataset described below.
* [Martin Alvarez-Kuglen](Martin_Alvarez-Kuglen): Focused on analysis and visualization of the internal relationships if each variable examined in the research. Interested in asking the questions 'what are these variables saying about each other? How do they interact and what information can we gain by looking at these interactions?'
* [Linnea Nygren](Linnea_Nygren): Focused on the interconnectedness between happiness and mental health, more specifically examing the similarities and differences between the World Happiness Report data and other data regarding depression collected by the World Health Organization. 

* Albert Schueller, test.

## World Happiness Data:


Our group will explore Gallup World Happiness Data, from the Gallup World Happiness Report 2021. The Gallup World Happiness Data is composed of select data taken from the Gallup World Poll: a survey conducted in over 160 countries globally, consisting of over 100 questions, with further regionally-based questions. The survey data represents 99% of adults globally, where adults are defined as residents over the age of 15. Country survey data is collected on at least 1,000 randomly selected individuals in most countries. For very sparsely populated countries or regions, Gallup reports a sample size with as few as 500 responses, while for very populous countries such as India and China Gallup reports upwards of 2,000 responses. The Gallup World Happiness Data we will use for our investigation consists of the questions in the Gallup World Happiness Data related to happiness.

We will be using two main datasets to frame our investigations. The first is a dataset that includes data from 2005 to 2020. The second is a 2021 dataset that includes the same indicators as the 2005-2020 dataset, but further includes the relative effect of happiness sub-indicators on the overall happiness score of a given country.



### World Happiness Ranking:


The first column in both our datasets contains a “life ladder score.” The life ladder score is used to rank countries in terms of happiness and forms the basis of world happiness rankings. Countries are ranked based on survey responses to a single question: “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?” Countries are ranked by mean life ladder score, with the highest score denoting the happiest country globally, and the lowest score denoting the least happy country globally.



### World Happiness Data: Explaining World Happiness:


The Gallup World Happiness Report further seeks to explain the observed differences in happiness between different countries and regions of the world. Thus, both datasets rely on six sub-indicators of happiness that are most strongly correlated with happiness:

1. GDP per Capita

1. Social Support

1. Healthy Life Expectancy

1. Freedom to make life choices

1. Generosity

1. Perceptions of Corruption



### 2021 Data, and Relative Effect


The relative impact of each sub-score is represented in the corresponding “explained” column of the 2021 data. The numerical “explained” value of the indicator can be divided by the life ladder score for a given country in a given year to determine the proportion of the life ladder score attributed to a given indicator.

The dystopia + residual column represents the remaining portion of a countries’ ladder score that cannot be explained using the identified sub-indicators of happiness.

### Other Information

_**Years Reported**_: Our primary dataset includes data between the years 2005 and 2020. The 2021 dataset includes only 2021 data.


_**Countries Included**_: The 2018-2020 dataset includes 149 different countries.


_**Missing Data**_: Both datasets have missing values for indicators or years where data is not available for a given country. Each of us will decide how to handle and analyze countries with missing values separately, in the context of our own investigations.
