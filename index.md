## Who Are the Russian Trolls?

It is currently under investigation whether during the 2016 U.S. elections a Russian 'troll factory', the IRA, released a number of tweets from fraudulent Twitter accounts. These tweets potentially influenced the population of voters by spreading statements, some of which were fake. The aim of this analysis is to better understand the strategy of the trolls by retrieving the main subjects of these tweets over time and categorizing them according to their targeted social, geographical, or political group. Quantifing the potential impact of those tweets and providing a link to specific events that were occuring in the United States at the time are the objectives.

![useful image](https://adarmonicteam.github.io//assets//images//blackcloud.png)

## Introduction

{:.test1}
hoverHERE


### Languages

An analysis of the types of languages that were tweeted reveals that Russian and English are the main languages. Interestingly, Spanish is not in this list even though it is the second most prominent language in the United States. The reason for this remains unclear. Since English is spoken by 72% of individuals in the U.S., our project focuses only on the tweets written in English. The following section will describe the models that were created for further analysis.

{% include languages.html %}

### Modelling Topics

In order to gain a better understanding of what the Trolls were posting about, a neural network was trained to recognize 11 topics that we deemed to be the most dominant based on the most common hashtags. This is hence a supervised learning approach. These topics include the following:
- **Trump**. Include any reference to Trump 
- **Trump Adversaries**. Include references to any political figure against Trump. Tweets in this category are commonly against Hillary Clinton or Obama.
- **Black**. Include any reference the African-American population
- **Patriot**. Includes tweets related to support of the NRA and the army
- **Crime**. Involve a type of criminal offense
- **Sports**. Includes any sports-related activity including events related to games, players and coaches 
- **Entertainment**. Include events related to celebrities, music and sometimes controversial topics
- **Health**. Includes tweets related health in general such as health insurance, going to the gym and food
- **Islam**. Involves anything against Islam, notably ISIS and bombings that occured internationally
- **Foreign Countries**. Includes tweets interested in international affairs and world news
- **Fukukshima**. A hashtag that appeared multiple times. It was quite distinct so we decided to give it its own topic

## Gaining Viewers

The Trolls were able to gain the attention of the masses via various strategies.

- One strategy was through exploiting popular and controversial events that occured either in America or internationally. As can be seen in the line plot below which ranges up to one year before the presidential election, there are distinct spikes that we can show to be correlated to events by reading specific tweets in the specific time periods. Examples include the following:

1. On **November 11th 2015**, there is a spike in the topic Foreign Countries. From inspection of the tweets, this is most likely attributable to the coordinated terrorist attacks that took place in Paris.
2. During the week of **February 29th 2016**, there is a peak in the topic related to African-Americans. The Oscars ceremony of 2016 was supposedly a very controversial ceremony, due to the fact that there were no black actors that were nominated. The Russian Trolls took advantage of this event to gain potential followers.
3. On **March 19th 2016**, there is a sharp increase in the topic Islam. This is the date of the bombing in Brussels, which is believed to have been related to ISIS. Tweets related to this event show strong anti-immigration sentiments.
4. On **September 26th**, the Trump Adversary topic sees its greatest spike. This was cooincidently the date of the first presidential debate between Donald Trump and Hillary Clinton.

{% include topics1.html %}

- A second strategy includes targetting specific populations of people. One of the most prominent that was found was that of the African-American population, which is a politically relevant community. Interestingly, when topic categorization was applied to analyze the types of tweets that were being released, the states which higher percentages of African-Americans correlated with the percent of Black-related tweets that were released by the Trolls.

{% include blackstates.html %} 

When a correlation coefficient is calculated that quantifies the relationship between the percentage of African-Americans versus the percent of Black-support topics in that state, a value of **0.52** is retrieved. This implies that there is a statistically relevant relationship between these two variables, and that the Trolls may very well have considered the African-American population of states when releasing tweets.

{% include BlackCorrelation.html %}

- Another strategy that was attempted was to reply to popular twitter authors such as **midnight** that are followed by a significant proportion of the American people. However, given the fact that only individuals who follow both the Troll who replied *and* the author to which the reply was made can see the reply, this tactic may have not been the best in terms of gaining an audience. For this reason the number of replies remains relatively low. (Does it drop off as time goes by?)

- One approach that had racked up a large quantity of followers was the creation of twitter counts that impersonated a real individual rather than accounts named in a news-related fashion. A notable example is the author jenn_abrams, a Troll account which was depicted to be a woman in her 30's that supported Trump. This account managed to attain a maximum follower count of 61759 during the period under inspection.

- These observations together show that a number of tactics were implemented by the Trolls, some of which were initiated without knowing what exactly would happen. In the next section, we will attempt to quantify the success of the Trolls, and later try to understand better how they targetted different states.

## Timeline Insights and Quantifying Success

From the following plot, it is clear that the general increase in followers cannot be attributed to an increase in tweets, nor increase in active authors. What could the increase in followers be attributed to? Are they real people? Or perhaps they are the Trolls themselves, including bots that may have been set up? To help answer this question, the statistics on the number of 'likes' were retrieved. 'Likes' have the potential to be considered as an indicator of Troll success - i.e. if they were able to get through to the general public. Here we see that the number of 'likes' skyrockets from 50,000 to 150,000 at the start of September, 2 months before the election. These numbers make sense, as there are approximately 200,000-400,000 followers in total during this period. 

{% include generalinfo.html %}

To better understand what topics were being 'liked', the model for topic prediction was applied. Here it is shown that the majority of 'likes' were attributed to topics related to the election such as Trump-support, Black-support and finally to smashing Trump adversaries (including Clinton and Obama), interestingly the news related tweets did not receive any significant increase in likes. Had these 'likes' been caused by bots, it would have been likely to see an increase in 'likes' that are not catered to a specific topic but rather distributed among all Troll tweets. Since practically no 'likes' were given to News-Feed topics, it may be less likely that the 'likes' are fake, and are rather related to real Americans who turn their interest towards politically-related topics.

{% include generalinfolikes.html %}

## Targetting Specific States

- From inspecting the names of the most active authors, it became clear that there are a number of author names which come across as neutral, news-related feeds. Examples of these include HOUSTONTOPNEWS and DAILYLOSANGELES. It is reasonable to assume that these accounts were created to target the population of cities in their respective names. In order to quantify this better, the following map was generated to visualize the number of tweets released in each state after filtering for cities and states contained in the author names. The map shows that the swing states of 2016 almost always had their own 'dedicated' Troll. On the other hand, several states that may not have been considered important to the Trolls did not have their own news account. 

{% include authorstate.html %}

- To better understand how do the trolls operate we wanted to see if they target specific states in the context of the tweet content itself. For each month in the dataset we filtered the number of tweets for each account category mentioning specific states or cities within those states. 

Below are the maps for the Right Trolls and the Left Trolls.

{% include left_troll_tweet_number.html %}

{% include right_troll_tweet_number.html %}

When we inspect the maps we see that in December 2015 there were 1460 tweets mentioning California for the right trolls yet for the same month the left trolls only had 1 tweet mentioning. In December 2015 a mass shooting and an attempted bombing occured in San Bernardino, California resulting in 14 killed and 22 seriously injured. The perpetrators were a married couple with the husband being U.S. born from Pakistani descent and the wife was born in Pakistan. It seems logical for the RightTrolls to tweet about this attack and use it to promote right wing agenda. The RightTroll tweets contained sympathetic tweets such as: "My heart goes out to the victims who were not so lucky  #Prayers4California", pro gun tweets such as: "Guns are our friends because in a country without guns, I'm what's known as "prey." All females are.  #Prayers4California" and "#SanBernardinoShooting displayes how inept and clueless anti-gun lawmakers are. #Prayers4California", criticism of the administration such as: "#ObamaLogic: we can’t defeat ISIS? We definitely must ban guns #Prayers4California" and "Under Obama administration mass shootings happen every month! He wants to cover his ass with gun control! #Prayers4California" and anti muslim tweets such as: "#GunControl but not Muslim control? Jihad a part of Islam when not raping 6 yr old girls  #Prayers4California". While the only LeftTroll tweets was unrelated to the event ("Deliberate act and home terror? Mosque Fire in Coachella, California, Investigated by FBI https://t.co/LSnUmD43Ia"). Except from this perticuliar event the RightTrolls did not target specific states. The LeftTrolls did not use this strategy as much with a maximum of about 200 tweets per state per month. In december 2015 the LeftTrolls targeted Chicago, Illinois with tweets related to social justice such as: "Chicago Police Admit To Killing Innocent 55-Year-Old Woman By Accident https://t.co/u9iZR2dwdW #BlackMatters https://t.co/D6qDwPOP96", "LIVE FEED FROM CHICAGO ANTI-MAYOR PRTOTEST #Chicago #Rahm #BlackLivesMatter #LaquanMcDonald #PoliceBrutality https://t.co/aaqw2noTHX", "No criminal charges will be filed against the Chicago cop who shot Ronald Johnson. Insanity. #BlackLivesMatter https://t.co/L5At3QoCdX" and tweets such as: "Chicago Mayors Speech Triggers Protests #ResignRahm #RahmEmanuelOut", "Chicago Mayor has to go directly to jail!!! #RahmEmanuelOut" that target the establishment targeting Rahm Emmanuele the mayor of Chicago. If we look at February 2016 we see that the LeftTrolls wrote 201 tweets mentioning Mississippi, upon further insepction most of the tweets were retweets or just copies of the same tweet: "NewsOne Now Audio Podcast: Bishop E.W. Jackson Calls #BlackLivesMatter Is Movement “Disgraceful”". Throughout that month this tweet was both written by different authors or by the same author in different dates 167 times without any retweets. This tweet was filtered as mentioning Mississippi due to the city of Jackson which in this specific case was unrelated. In March 2016 the marking of the 1965 Selma to Montgomery (both in Alabama) marches occured resulting in tweets that focused on black people such as: "I proud to be black!!! #SelmaToMontgomery1965", "I'm with Martin Luther king. Support everything he proposed #SelmaToMontgomery1965 https://t.co/9xhlaPA5yo" showing the LeftTrolls targeting specific events. Besides these few months the RightTrolls and LeftTrolls did not always target specific states but werer more focused on events.

## Do the trolls mention specific users?

We wanted to investigate who do the users mention in particular if they mention each other. We plotted the histogram of the trolls mentioned by other trolls and interestingly enough they only mention 13 trolls. All of these 13 troll’s accounts are categorized as HashtagGamer and except the first 3 they are mentioned only a number of times. For each of these 3 users we analyzed the 10 tweets with most replies, most likes and most retweets. Interestingly enough we did not feel that these tweets had a particular “trolling” message and some of them were the same for all the 3 users, with tweets such as: “#ThingsIWontBelieve this church sign https://t.co/BY7GlfV8X0” , “#IHatePokemonGoBecause There will be more distracted drivers”. Only in the 10 tweets with the most replies did we saw some tweets with a poitical side such as: “Obama is elected the 3rd time #MakeMeMadIn5Words”, “Why? And when will my people learn? Whites can’t be trusted #IStartCryingWhen https://t.co/GgDfyBZ5M7” and “#GrowingUpWithObama watching his ugly daughter in all networks https://t.co/Ip5EjlfDzI“. When we take the tweet about Obama being elected for the 3rd time two of the users tweeted it at the same exact time (to the hour). This fact made us do a further investigation into the subject that we will tackle later. We plotted the histogram of all the users mentioned by the trolls and as one can see the most mentioned user is: @midnight which is a late-night internet themed panel game show, while in red we marked the users we would expect to see mentioned (Donald Trump, Hillary Clinton) and the 3 trolls mentioned by other trolls. What we noticed is that in contrast to our expectation they did not mention that much Hillary Clinton nor Donald Trump (around 200 tweets out of more than a million). 

![image1](https://github.com/adarmonicteam/adarmonicteam.github.io/blob/master/_includes/trolls_mentioning_other_trolls.eps)
![image2](https://github.com/adarmonicteam/adarmonicteam.github.io/blob/master/_includes/mentioned_users.eps)

