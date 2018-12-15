### Who Are the Russian Trolls?

It is currently under investigation whether during the 2016 U.S. elections a Russian 'troll factory', the IRA, released a number of tweets from fraudulent Twitter accounts. These tweets potentially influenced the population of voters by spreading statements, some of which were fake. The aim of this project is to better understand the strategy of the trolls by retrieving the main subjects of these tweets over time and categorizing them according to their targeted social, geographical, or political group. Quantifing the potential impact of those tweets and providing a link to specific events that were occuring in the United States at the time are the objectives.

### Gaining Viewers

The Trolls were able to gain the attention of the masses via various strategies.

- One strategy was through exploiting popular and controversial events that occured either in America or internationally. As can be seen in the line plot below which ranges up to one year before the presidential election, there are distinct spikes that we have shown to be correlated to events.

{% include topics1.html %}

- A second strategy includes targetting specific populations of people. One of the most prominent that was found was that of the African-American population, which is a politically relevant community. Interestingly, when topic categorization was applied to analyze the types of tweets that were being released, the states which higher percentages of African-Americans correlated with the percent of Black-related tweets that were released by the Trolls.

{% include blackstates.html %} 

When a correlation coefficient is calculated that quantifies the relationship between the percentage of African-Americans versus the percent of Black-support topics in that state, a value of **0.52** is retrieved. This implies that there is a statistically relevant relationship between these two variables, and that the Trolls may very well have considered the African-American population of states when releasing tweets.

{% include BlackCorrelation.html %}

- Another strategy that was attempted was to reply to popular twitter authors such as **midnight** that are followed by a significant proportion of the American people. However, given the fact that only individuals who follow both the Troll who replied *and* the author to which the reply was made can see the reply, this tactic may have not been the best in terms of gaining an audience. For this reason the number of replies remains relatively low. (Does it drop off as time goes by?)

### Timeline Insights and Quantifying Success

From the following plot, it is clear that the general increase in followers cannot be attributed to an increase in tweets, nor increase in active authors. What could the increase in followers be attributed to? Are they real people? Or perhaps they are the Trolls themselves, including bots that may have been set up? To help answer this question, the statistics on the number of 'likes' were retrieved. 'Likes' have the potential to be considered as an indicator of Troll success - i.e. if they were able to get through to the general public. Here we see that the number of 'likes' skyrockets from 50,000 to 150,000 at the start of September, 2 months before the election. These numbers make sense, as there are approximately 200,000-400,000 followers during this period. 

{% include generalinfo.html %}

To better understand what topics were being 'liked', the model for topic prediction was applied. Here it is shown that the majority of 'likes' were attributed to topics related to the election such as Trump-support, Black-support and finally to smashing Trump adversaries (including Clinton and Obama). Since practically no 'likes' were given to News-Feed topics, it may be less likely that the 'likes' are fake, and are rather related to real Americans who turn their interest towards politically-related topics.

{% include generalinfolikes.html %}

### Who are the Authors?

From inspecting the names of the most active authors, it became clear that there are a number of author names which come across as neutral, news-related feeds. Examples of these include HOUSTONTOPNEWS and DAILYLOSANGELES. It is reasonable to assume that these accounts were created to target the population of cities in their respective names. In order to quantify this better, the following map was generated to visualize the number of tweets released in each state after filtering for cities and states contained in the author names. 

The map shows that the swing states of 2016 almost always had their own 'dedicated' Troll. Several states that 
