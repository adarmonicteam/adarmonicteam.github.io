## Who Are the Russian Trolls?

It is currently under investigation whether during the 2016 U.S. elections a Russian 'troll factory', the **Internet Research agency (IRA)** based in St. Petersburg, released a number of tweets from fraudulent Twitter accounts. These tweets potentially influenced the population of voters by spreading statements, some of which were fake. The aim of this analysis is to better understand the strategy of the trolls by retrieving the main subjects of these tweets over time and categorizing them according to their targeted social, geographical, or political group. Quantifing the potential impact of those tweets and providing a link to specific events that were occuring in the United States at the time are the objectives.

## Introduction

On October 7th 2016, the **Department of  Homeland Security** and the **Director of National Intelligence** (ODNI) stated that the American Intelligence Community was certain that the Russian Government had interfered with the U.S. election process through a number of strategies with the intent of damaging Hillary Clinton's presidential campaign. Examples of such strategies include, but are not limited to, directed hacking of Hillary Clinton's personal google email account and the broadcasting of fake news via social media accounts. In early 2017, the ODNI stated that the Russian president Vladimir Putin personally ordered this 'influence campaign' to harm Clinton's chances and thereby increase the chance of the election of a president more favorable to Russia. 

The Russian internet trolls targetted a number of social media services such as Facebook and Twitter. This analysis will consider data only from Twitter. The [dataset](https://www.kaggle.com/fivethirtyeight/russian-troll-tweets/home) is provided by FiveThirtyEight and comprises a number of features, including but not limited to, author name, content (the tweet itself), language, date, followers and account type. A [second dataset](https://about.twitter.com/en_us/values/elections-integrity.html#data) is used as supplementary material and includes other features that will be incorporated into the analysis such as the number of likes for a given tweet. We expect the types of accounts to differ in activity and subject matter depening on the timeframe. The analysis will attempt to dig deeper into the strategy of these Russian trolls.

### Languages

An analysis of the types of languages that were tweeted reveals that **Russian** and **English** are the main languages. Interestingly, Spanish appears to be negligible even though it is the second most prominent language in the United States. The reason for this remains unclear. Considering the fact that English is spoken by 72% of individuals in the U.S. and that Russian tweets would not be able to get through to the American population in general, our project focuses only on the tweets written in English. The following plot shows the most common languages, the legend is ordered by most frequent language to less frequent.

{% include languages.html %}

### Modelling Topics

This following section will describe the models that were created for further analysis.
In order to gain a better understanding of what the Trolls were posting about, a **neural network** was trained to recognize 11 topics that we deemed to be the most dominant based on the most common hashtags. This is hence a supervised learning approach. The neural net was implemented in PyTorch and trained using Google CoLab's Tesla K80 GPU. The net has three hidden layers - the first, second and third layers have 6000, 1000 and 100 neurons, respectively. The model was shown to have an accuracy of 85% through an evaluation on a test set. The list of topics is given below. **Try hovering over the topic description** for a graphical representation of the most tweeted words in a given topic.



{% include TrumpHover.html %} 

{% include AdvHover.html %}

{% include BlackHover.html %}

{% include PatHover.html %}

{% include CrimeHover.html %}

{% include SportHover.html %}

{% include EntHover.html %}

{% include HealthHover.html %}

{% include IslamHover.html %}

{% include ForHover.html %}

## Gaining Viewers

The Trolls were able to gain the attention of the masses via various strategies.

- One strategy was through **exploiting popular and controversial events** that occured either in America or internationally. As can be seen in the line plot below which ranges up to one year before the presidential election, there are distinct spikes that we can show to be correlated to events by reading specific tweets in the specific time periods. Examples include the following for the most followed accounts:

1. On **November 11th 2015**, there is a spike in the topic Foreign Countries. From inspection of the tweets, this is most likely attributable to the coordinated terrorist attacks that took place in Paris.
  > You may not be at war with Islam, but Islam is at war with you   #ISIS 
    -JENN_ABRAMS

2. During the week of **February 29th 2016**, there is a peak in the topic related to African-Americans. The Oscars ceremony of 2016 was supposedly a very controversial ceremony, due to the fact that there were no black actors that were nominated. The Russian Trolls took advantage of this event to gain potential followers.
  > #OscarsSoWhite REALLY?? #Oscars
    -JENN_ABRAMS
    
3. On **March 19th 2016**, there is a sharp increase in the topic Islam. This is the date of the bombing in Brussels, which is believed to have been related to ISIS. Tweets related to this event show strong anti-immigration sentiments.
  > No equality. No freedom. Just violence, civil war and terrorism... Do we need this to happen in America?
    -PIGEONTODAY
    
4. On **September 26th**, the Trump Adversary topic sees its greatest spike. This was cooincidently the date of the first presidential debate between Donald Trump and Hillary Clinton.
  > This is not a misspell on Hofstra University's debate tickets It's the name of Hillary's body double #debatenight
    -JENN_ABRAMS

{% include topics1.html %}

- A second strategy includes **targetting specific populations** of people. One of the most prominent that was found was that of the African-American population, which is a politically relevant community. Interestingly, when topic categorization was applied to analyze the types of tweets that were being released, the states which higher percentages of African-Americans correlated with the percent of Black-related tweets that were released by the Trolls.

{% include blackstates.html %} 

When a correlation coefficient is calculated that quantifies the relationship between the percentage of African-Americans versus the percent of Black-support topics in that state, a value of **0.52** is retrieved. This implies that there is a statistically relevant relationship between these two variables, and that the Trolls may very well have considered the African-American population of states when releasing tweets.

{% include BlackCorrelation2.html %}

- Another strategy that was attempted was to **reply to popular twitter authors** such as *midnight* that are followed by a significant proportion of the American people. However, given the fact that only individuals who follow both the Troll who replied *and* the author to which the reply was made can see the reply, this tactic may have not been the best in terms of gaining an audience. For this reason the number of replies remains relatively low. (Does it drop off as time goes by?)

- One approach that had racked up a large quantity of followers was the creation of twitter accounts that **impersonated a seemingly real individual** rather than accounts named in a news-related fashion. A notable example is the author JENN_ABRAMS, a Troll account which was depicted to be a woman in her 30's that supported Trump. This account managed to attain a maximum follower count of 61759 during the period under inspection.

- These observations together show that a number of tactics were implemented by the Trolls, some of which were initiated without knowing what exactly would happen. In the following sections, we will attempt to quantify the success of the Trolls, and later try to understand better how they targetted different states.

## Timeline Insights and Quantifying Success

From the following plot, it is clear that the general increase in followers cannot be attributed to an increase in tweets, nor increase in active authors. What could the increase in followers be attributed to? Are they real people? Or perhaps they are the Trolls themselves, including bots that may have been set up? To help answer this question, the statistics on the number of 'likes' were retrieved. 'Likes' have the potential to be considered as an indicator of Troll success - i.e. if they were able to get through to the general public. Here we see that the number of 'likes' skyrockets from 50,000 to 150,000 at the start of September, 2 months before the election. These numbers make sense, as there are approximately 200,000-400,000 followers in total during this period. 

{% include generalinfo2.html %}

To better understand what topics were being 'liked', the model for topic prediction was applied. Here it is shown that the majority of 'likes' were attributed to topics related to the election such as Trump-support, Black-support and finally to smashing Trump adversaries (including Clinton and Obama), interestingly the news related tweets did not receive any significant increase in likes. Had these 'likes' been caused by bots, it would have been likely to see an increase in 'likes' that are not catered to a specific topic but rather distributed among all Troll tweets. Since practically no 'likes' were given to News-Feed topics, it may be less likely that the 'likes' are fake, and are rather related to real Americans who turn their interest towards politically-related topics.

{% include generalinfolikes2.html %}

## Targetting Specific States

- There is a particular interest in the [swing states](https://constitutioncenter.org/blog/what-are-the-really-swing-states-in-the-2016-election/), as they include the population of voters that are not necessarily sure for which candidate to vote. The forecast of which states will be swing states in a given year is based on historical trends. For this reason they are considered by many the most relevant states to pursue during presidential campaigns. The definite and potential swing states of the 2016 U.S. election were forecasted to be:
  - Colorado
  - Florida
  - Iowa
  - Michigan
  - Minnesota
  - Nevada
  - New Hampshire
  - North Carolina
  - Ohio
  - Pennsylvania
  - Virginia
  - Arizona
  - Georgia
  - Oregon
  - Wisconsin
  
- In order to gain a better understanding of how the swing states may have been targetted, the tweets mentioning any of the swing states including the names of cities within them were filtered and counted over time. This was then compared to the trends of all non-swing states. The average value for the tweets per day for swing states is 90, while that of non-swing states is 57. A Wilcoxon test was performed due to the non-normal distribution of the data and results in a p-value of 6.15x10^-41. Note that the line plots are normalized by number of states that make up the data of a given line - e.g., the sum of tweets for the swing states in a given day are divided by 15 since there are 15 swing states. 

{% include swingstate1.html %}


- From inspecting the names of the most active authors, it became clear that there are a number of author names which come across as neutral, news-related feeds. Examples of these include HOUSTONTOPNEWS and DAILYLOSANGELES. It is reasonable to assume that these accounts were created to target the population of cities in their respective names. In order to quantify this better, the following map was generated to visualize the number of tweets released in each state after filtering for cities and states contained in the author names. The map shows that the swing states of 2016 almost always had their own 'dedicated' Troll. On the other hand, several states that may not have been considered important to the Trolls did not have their own news account. 

{% include authorstate.html %}

- To better understand how do the trolls operate we wanted to see if they target specific states in the context of the tweet content itself. For each month in the dataset we filtered the number of tweets for each account category mentioning specific states or cities within those states. 

Below are the maps for the Right Trolls and the Left Trolls.

{% include left_troll_tweet_number.html %}

{% include right_troll_tweet_number.html %}

When we inspect the maps we see that in December 2015 there were 1460 tweets mentioning California for the right trolls yet for the same month the left trolls only had 1 tweet mentioning. In December 2015 a mass shooting and an attempted bombing occured in San Bernardino, California resulting in 14 killed and 22 seriously injured. The perpetrators were a married couple with the husband being U.S. born from Pakistani descent and the wife was born in Pakistan. It seems logical for the RightTrolls to tweet about this attack and use it to promote right wing agenda. The RightTroll tweets contained sympathetic tweets such as: "My heart goes out to the victims who were not so lucky  #Prayers4California", pro gun tweets such as: "Guns are our friends because in a country without guns, I'm what's known as "prey." All females are.  #Prayers4California" and "#SanBernardinoShooting displayes how inept and clueless anti-gun lawmakers are. #Prayers4California", criticism of the administration such as: "#ObamaLogic: we can’t defeat ISIS? We definitely must ban guns #Prayers4California" and "Under Obama administration mass shootings happen every month! He wants to cover his ass with gun control! #Prayers4California" and anti muslim tweets such as: "#GunControl but not Muslim control? Jihad a part of Islam when not raping 6 yr old girls  #Prayers4California". While the only LeftTroll tweets was unrelated to the event ("Deliberate act and home terror? Mosque Fire in Coachella, California, Investigated by FBI https://t.co/LSnUmD43Ia"). Except from this perticuliar event the RightTrolls did not target specific states. The LeftTrolls did not use this strategy as much with a maximum of about 200 tweets per state per month. In december 2015 the LeftTrolls targeted Chicago, Illinois with tweets related to social justice such as: "Chicago Police Admit To Killing Innocent 55-Year-Old Woman By Accident https://t.co/u9iZR2dwdW #BlackMatters https://t.co/D6qDwPOP96", "LIVE FEED FROM CHICAGO ANTI-MAYOR PRTOTEST #Chicago #Rahm #BlackLivesMatter #LaquanMcDonald #PoliceBrutality https://t.co/aaqw2noTHX", "No criminal charges will be filed against the Chicago cop who shot Ronald Johnson. Insanity. #BlackLivesMatter https://t.co/L5At3QoCdX" and tweets such as: "Chicago Mayors Speech Triggers Protests #ResignRahm #RahmEmanuelOut", "Chicago Mayor has to go directly to jail!!! #RahmEmanuelOut" that target the establishment targeting Rahm Emmanuele the mayor of Chicago. If we look at February 2016 we see that the LeftTrolls wrote 201 tweets mentioning Mississippi, upon further insepction most of the tweets were retweets or just copies of the same tweet: "NewsOne Now Audio Podcast: Bishop E.W. Jackson Calls #BlackLivesMatter Is Movement “Disgraceful”". Throughout that month this tweet was both written by different authors or by the same author in different dates 167 times without any retweets. This tweet was filtered as mentioning Mississippi due to the city of Jackson which in this specific case was unrelated. In March 2016 the marking of the 1965 Selma to Montgomery (both in Alabama) marches occured resulting in tweets that focused on black people such as: "I proud to be black!!! #SelmaToMontgomery1965", "I'm with Martin Luther king. Support everything he proposed #SelmaToMontgomery1965 https://t.co/9xhlaPA5yo" showing the LeftTrolls targeting specific events. Besides these few months the RightTrolls and LeftTrolls did not always target specific states but werer more focused on events.

## Do the trolls mention specific users?

We wanted to investigate who do the users mention in particular if they mention each other. We plotted the histogram of the trolls mentioned by other trolls and interestingly enough they only mention 13 trolls. All of these 13 troll’s accounts are categorized as HashtagGamer and except the first 3 they are mentioned only a number of times. For each of these 3 users we analyzed the 10 tweets with most replies, most likes and most retweets. Interestingly enough we did not feel that these tweets had a particular “trolling” message and some of them were the same for all the 3 users, with tweets such as: “#ThingsIWontBelieve this church sign https://t.co/BY7GlfV8X0” , “#IHatePokemonGoBecause There will be more distracted drivers”. Only in the 10 tweets with the most replies did we saw some tweets with a poitical side such as: “Obama is elected the 3rd time #MakeMeMadIn5Words”, “Why? And when will my people learn? Whites can’t be trusted #IStartCryingWhen https://t.co/GgDfyBZ5M7” and “#GrowingUpWithObama watching his ugly daughter in all networks https://t.co/Ip5EjlfDzI“. When we take the tweet about Obama being elected for the 3rd time two of the users tweeted it at the same exact time (to the hour). This fact made us do a further investigation into the subject that we will tackle later. We plotted the histogram of all the users mentioned by the trolls and as one can see the most mentioned user is: @midnight which is a late-night internet themed panel game show, while in red we marked the users we would expect to see mentioned (Donald Trump, Hillary Clinton) and the 3 trolls mentioned by other trolls. What we noticed is that in contrast to our expectation they did not mention that much Hillary Clinton nor Donald Trump (around 200 tweets out of more than a million). 

![image1](https://github.com/adarmonicteam/adarmonicteam.github.io/blob/master/assets/images/trolls_mentioning_other_trolls.png)
![image2](https://github.com/adarmonicteam/adarmonicteam.github.io/blob/master/assets/images/mentioned_users.png)

## Do trolls re-write the same tweet?
We were interested to see if tweet contents are repeated several times. In order to do that we filtered the data to only contain tweets that were not labeled as a retweet and found that there are 16,707 tweets that appear more than once, 170 tweets that appear more than 10 times and 8 tweets that appear more than 30 times which are the tweets we focus on.  
As the tweets are too long to show on any figure we created the following mapping:

	- Tweet 1: “NewsOne Now Audio Podcast: Bishop E.W. Jackson Calls #BlackLivesMatter Is Movement “Disgraceful””
	- Tweet 2: “Honor scores  #sports”
	- Tweet 3: “SE Wis. road construction projects  #Wisconsin”
	- Tweet 4: “Celebrity style: Red carpet looks  #celebs #news”
	- Tweet 5: “Daily Celebrity Watch  #celebs #news”
	- Tweet 6: “RT @thehill: Trump repeatedly interrupted by protesters shouting #BlackLivesMatter”
	- Tweet 7: “On the Air  #sports”
	- Tweet 8: “Judge Rips Media”

As one can see these tweets target the BlackLivesMatter movement or news (sports and entertainment). We quantified how many times each one of these tweets appeared in the data with Tweet 1 appearing more than 200 times and Tweets 2 and 3 are above 100 and almost 100 times respectively. 

![image3](https://adarmonicteam.github.io//assets//images//number_duplicates.png)

We wanted to further investigate so we looked at how many unique authors wrote each tweet resulting with tweets 1,8 and 6 being written by several authors and all other tweets being only written by the same author. Tweets 1, 8, 6 interestingly enough have a political orientation while the tweets that were written by only 1 author seem to be more related to the category account of tweets (Sports, NewsFeed, etc.) hinting that there maybe was pre-written tweets distributed between trolls. 

![image4](https://adarmonicteam.github.io//assets//images//number_duplicates_authors.png)

We also wanted to see the times at which these tweets were published so we took only the date of the tweet (without separating the exact time) and looked at how many unique dates does each tweet have. This resulted in all of them having several unique dates with the lowest being tweets 8, 1, and 6 respectively. The fewer unique dates the more it seems as these tweets were written in coordination between authors whilst the other tweets maybe did not always have something to tweet about resulting in just re-tweeting something in order to keep their account active.

![image5](https://adarmonicteam.github.io//assets//images//number_duplicates_dates.png)


![useful image](https://adarmonicteam.github.io//assets//images//blackcloud.png)
