# World Happiness Data Visualization (Nick Hager)


## First Look ##

My initial interest in the dataset is determining how much of the data is usable, for example, after an initial glance I could determine that some countries have entries dating back to 2005 but others do not. In order to accurately compare the data from different countries year to year, it is important to ensure that the countries actually have data to compare and that they have an equal baseline.


{% include_relative Visualizations/Countries_Per_Year.html %}


The data appears to reach a roughly consistent number of countries in 2011 which makes sense as on the [World Happiness Report (WHR) website](https://worldhappiness.report/archive/), the first report was released for 2012, examining the previous year. For this reason, when comparing all the countries together, 2011 will serve as a good baseline year for which all the countries involved have data. It is also worth noting that there is a noticeable drop in the number of countries with data for the year 2020. The authors of the [World Happiness Report (2021)](https://worldhappiness.report/ed/2021/) attribute the difficulties with collecting data to the COVID-19 global pandemic and as a result of this it would be reasonable to exclude the year of 2020 from the data or choose to examine it further separately. I have chosen to include it in my visualizations as they are not entirely oriented around change over time for which the lacking data would have the greatest impact.


## Diving Deeper ##

One question that I am personally interested in is "what is the best way to present as much of the data as possible to the viewer in a way that is both reasonable and helpful?" Continuing to work with the data from the 2021 World Happiness Report, there is a lot of information to manage: roughly 150 different countries, a range of 15 years, and the 9 unique columns with the various factors that contribute to happiness.
To start off, following my earlier observations, we will narrow the data down to 2011-2020 as these years have official published reports implying more consistent and reliable data. This also means the data includes a relatively consistent number of countries (aside from 2020) which can thankfully be displayed in the familiar fashion of global map using [plotly choropleths](https://plotly.com/python/choropleth-maps/). Global choropleths however require geojson codes to connect the data from the countries to the location of the countries on the map which the WHR data did not include. This issue was easily resolved however by merging the WHR with [another dataset](https://github.com/plotly/datasets/blob/master/2014_world_gdp_with_codes.csv) the included the codes and then simply dropping the unneeded columns from the other dataset. 
Using global choropleths, we can better visualize the rest of the data showing the change over time and also the other unique factors the WHR included. To once again clarify what these factors are, the 9 columns included in the WHR are as follows:

1. Life Ladder - Answer to the question: "Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?”
1. Log GDP Per Capita - Log of a country's economic output per person calculated by dividing the gross domestic production (GDP) of a country by its population.
1. Social Support - Measures binary responses (either 1-0) to the question "If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?"
1. Healthy Life Expectancy at Birth - Age based on the World Health Organization's Global Health Observatory data.
1. Freedom to Make Life Choices - Measures binary response to the question "are you satisfied or dissatisfied with your freedom to choose what you do with your life?"
1. Generosity - Based on answer to the question "Have you donated money to a charity in the past month?" regressed with GDP per capita.
1. Perceptions of Corruption - Measures binary responses to two questions: "Is corruption widespread throughout the government or not?" and "Is corruption widespread within businesses or not?"
1. Positive Affect & Negative Affect - two separate columns based on similar questions. Positive Affect measured the responses to the question "did you experience the following feelings during A LOT OF THE DAY yesterday?" with the feelings in question being happiness, enjoyment, and smiles or laughter. Negative Affect measured responses to the same question with the feelings mentioned in the question being worry, sadness, and anger.

In order to visualize this data in a reasonable yet meaningful way, I figured that the best method would be to display a single year and a single factor to the viewer at a time, yet give them control over which year and factor they could view. I planned to implement the years on slider and the factors on a dropdown menu to allow the viewer full control of which global choropleth they would be viewing. This proved to be remarkably more difficult than I had expected.

### Challenges & Difficulties

The major problem with combining sliders and dropdown menus in plotly graphs is the issue of visibility. Each graph can contain multiple traces and ideally a combination of 9 factors with 10 years would result in 90 traces that could theoretically all fit on the same graph. While this part is certainly feasible, the graph should only display the single correct trace at a given time and should be dependent on both the slider and the dropdown selection, for example looking at the Life Ladder Score of all the countries in 2011. However, to determine which trace should be visible, both the slider and dropdown selection rely on separate boolean masks that tell a certain trace to be visible and make all other traces disappear. The problem is that these masks are separate from one another, meaning that moving the slider would have no effect on what the dropdown selector "thinks" it should be displaying. Essentially, this means that instead of a single graph to display everything, we will instead rely on 19, one for each year and one for each factor.

### The Results

Despite our inability to fully compress all of the years and factors into a single visualization, that does not mean the visualizations we are left with are low quality or useless. The visualizations we have created will allow the viewer to look at all factors for a specific year or all the years for a specific factor, and we can further increase the quality of these graphs by taking into account the color and adding annotations. To help distinguish the factors I had each choropleth for a given factor be a distinct color so that the viewer would recieve immediate visual feedback when switching between visualizations. The colorscales I chose for each choropleth was based on my own personal favorites that took into account distinct coloration from the other choropleths and also clearly distinguished the countries without data. Additionally, we can provide which country scored the highest and lowest for any particular factor as a helpful annotation for the viewer in the upper-right hand corner of the visualization. Below is where you can find all 19 visualizations sorted by what their independent variable.

| Sorted by Year | Sorted by Factor |
| ----------------- | -------------------  |
| [2011](data_by_year/index.md#2011) | [Life Ladder](data_by_factor/index.md#life-ladder) |
| [2012](data_by_year/index.md#2012) | [Log GDP per capita](data_by_factor/index.md#log-gdp-per-capita) |
| [2013](data_by_year/index.md#2013) | [Social Support](data_by_factor/index.md#social-support) |
| [2014](data_by_year/index.md#2014) | [Healthy Life Expectancy at Birth](data_by_factor/index.md#healthy-life-expectancy-at-birth) |
| [2015](data_by_year/index.md#2015) | [Freedom to Make Life Choices](data_by_factor/index.md#freedom-to-make-life-choices) |
| [2016](data_by_year/index.md#2016) | [Generosity](data_by_factor/index.md#generosity) |
| [2017](data_by_year/index.md#2017) | [Perceptions of Corruption](data_by_factor/index.md#perceptions-of-corruption) |
| [2018](data_by_year/index.md#2018) | [Positive Affect](data_by_factor/index.md#positive-affect) |
| [2019](data_by_year/index.md#2019) | [Negative Affect](data_by_factor/index.md#negative-affect) |
| [2020](data_by_year/index.md#2020) |           |
