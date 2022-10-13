**ASSUMPTIONS**
This analysis scraped data from english speaking Wikipedia to identify the number of articles per capita of various countries' politicians. It uses the following APIs and documentation.

Wikipedia API: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions
API documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews#Quick_start

ORES wikipedia Article Quality API: https://www.mediawiki.org/wiki/ORES

Politicians webscraped from the following Wikipedia link tree: https://en.wikipedia.org/wiki/Category:Politicians_by_nationality

Population per Country / Region Dataset: https://www.prb.org/international/indicator/population/table
 - Note This CSV was modified slightly. A single row was added in order to easily fit together with the politicians dataset. Certain politicians listed existed in pre-separated korea, thus are assigned a country that no longer exists. The hypothetical population of that non-existant country is added below.
 - Row added: Korean,77.7

Any articles that failed to be looked up were excluded from further analysis. A list of those countries may be be found in the notebook as they are excluded.

**Research Implications**
Over the course of this research I learned the value of not making assumptions about the ending distribution of a trend before seeing it for yourself, as well as the damage that a statistic by itself can do without context around it. For example if our findings section only reported the findings about quality by region per capita alot of findings could be drawn out that are not neccesarily represented in the more specific datasets. For example the position of western europe at the near bottom of the list is not supported by a country view of quality, which places many western european countries near the top. This really surprised me and I think is just a reflection of population figures, one of the dangers of reporting per capita statistics without the underlying numbers. Regions like South asia have so many people, and fewer countries (and thus politicians) than more dense regions like Europe, will obviously have less articles both high and low quality per capita. Whether or not this is a reflection on the region, the politics, or something else is hard to figure out with only that one statistic. I believe that the number of articles and their quality is largely dependent on how many politicians are actually serving in that country, the term limits of a country or region, and how involved with politics the average person in that country is. Of course it also goes without saying that there is a bias in the coverage smaller countries get on wikipedia as opposed to large power brokers, as is visible by top 10 countries by quality chart, but other complicated factors muddy the waters and make it difficult to firmly attribute differences to one source of bias or another.

_What biases did you expect to find in the data (before you started working with it), and why?_

Before working with the data I fully expected that large power broker countries will be overrepresented in the wikipedia articles count. I was partly correct on this fact and feel that if the USA or north america in general was included in this search they would blow the rest of the world out of the water in sheer coverage. Unfortuantely with America still largely dominating news even in other countries, it is no surprise that countries with imperial influence over others will be watched more closely, and thus have more articles written about them.

Furthermore we are looking at the English speaking wikipedia, meaning there is inherit US / European bias to which articles are being written or reviewed by wikipedia members high ranking enough to consider somethign quality.

_What might your results suggest about (English) Wikipedia as a data source?_

English speakers write articles about countries and regions that english regions are interested in, including themselves but also excluding certain other regions.

_Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?_

I believe training a model with the express purpose of pushing it into making extremely biased predictions about the quality of different region's politicians could be a useful way to draw attention to the problem of bias in underlying data. Wikipedia data is an interesting source of bias because it encapsulates our english speaking systematic bias. With a model such as this one we can not point at some bug or flaw in code. 

I will add that the use of per-capita measures to rank the countries and regions causes countries with very low populations to be boosted in the per-capita values rather than very high population countries that have a higher number of articles. Article count and population dont necessarily grow together linearly, also article count is an integer value, while population can be partial.
