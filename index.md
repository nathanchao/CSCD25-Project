<b><span style="color:red">NSFW WARNING: NOTE THAT THERE ARE UNCENSORED SWEAR WORDS IN THIS ASSIGNMENT</span></b>.

# Analyzing Bad Mouths

## Abstract
A large portion of society has deemed certain words to be "bad", however some
people still choose to use these words in their everyday speech. My project
aims to analyze the behaviour of these people. The project will hopefully give
hints to deeper questions such as why people swear and what kinds of societal
effects swearing has. I would also like to understand at a deep level the kinds
of people that swear.

Analyzing posts on Reddit is the ideal place to analyze these behaviours.
Users can post anonymously, so users are more free to speak their mind freely
without worrying about repercussions. The free-form speech posted on Reddit
allows us to analyze human speech in its most natural form without any major
influences.

To keep data processing times minimal, I selected around 100 posts from 78 subreddits to analyze. Also note that for this assignment, I am considering a swear word to be any word that contains "sh\*\*" or "fu\*\*".

## Analyzing Proportion of Posts that Swear in Different Sub-Reddits
The following figure shows the proportion of posts in the selected subreddits that swear. 

![Subreddits that swear](Pictures/subreddit%20swearing.png)
 
A key take away from the figure above is that subreddits that are based on some type of complaining tend to have the highest proportion of posts that swear. For example, the subreddits with the highest, second highest and fourth highest proportion of posts that swear are: "fuckepic", "misanthropy" and "rantgrumps". "fuckepic" is described as "The premiere source for all Epic Games criticism". "misanthropy" is defined as "the general hatred, distrust or disdain of the human species or human nature". "rantgrumps" is where Redditors "Rant and Vent about Game Grumps". 

Next, I looked at the median score in each subreddit of posts that swear vs. posts that don't swear. This is shown in the following plot.

![Post scores](Pictures/post%20scores.png)

I immediately noticed that in almost all subreddits, the median score for posts that swear is higher than that of posts that don't swear. Out of the sampled subreddits, the average ratio of scores of posts that swear to scores of posts that don't swear is: 5.408527796272671 and the median ratio is 1.9496527777777777.

From here, I tried to investigate a related question, which is my main research question: in which types of communities swearing is most/least favored in (based on the score of posts)? After trying two different approaches, I was unable to answer this question. 

The first method I tried was manually inspecting the subreddits with a large or small "score ratio", where the score ratio is the ratio of the median of scores of posts that swear to the median of scores of posts that don't swear. Some subreddits with a large "score ratio" are: "simpleliving", "Skookum" and "fiaustralia". I wasn't able to find anything in common between subreddits with a large "score ratio". 

Next, I wanted to see if there's a correlation between  "swear proportion" (the proportion of posts in a subreddit that swear) and "score ratio", I reran the whole notebook multiple times and used the pandas corr function to find the Pearson coefficient. There was always a moderate or weak correlation between "swear proportion" and "score ratio". From this I concluded that there is no significant correlation between "swear proportion" and "score ratio". 

## Finding which non-swear words are commonly said with swear words
To find which non-swear words are commonly said with swear words, I trained a logistic regression model to predict whether a post swears or not based on the words in the post and then analyzed the coefficients of the features in the trained logistic regression. Here are the words with the highest weights:

![Post scores](Pictures/log%20reg%20coeffs.png)

"Hate" was the word the highest weight. This makes sense because "hate" is oftentimes said along with f\*\*\*. Other vulgar words that are sometimes considered swear words (but weren't considered swear words for this project) such as "damn", "di\*\*" and "he\*\*" were among the words with the highest weights. These results make sense. Many of the words with the highest weights are commonly said along with swear words. 

## When do Redditors Swear?
First, I looked at swearing frequency in posts created from January 2019 - June 2021. Here is the plot:
 
![Post scores](Pictures/2%20year%20swearing.png)

The plot jumps around between consecutive months. It's not clear if there's an overall upward or downward trend. One noticeable spike that corresponds with a significant event in the world is the spike in March 2020. This is the time when Covid-19 first became serious. 

Next, I looked at the swearing frequency in posts based on the month they were created. Here is the plot:

![Post scores](Pictures/months%20swearing.png)

The swearing frequency from month-to-month is fairly consistent except for sharp decreases in swearing in January, September and November. I'm not sure what caused these sharp decreases. This could simply be caused by the randomness of the data sample.

Then, I looked at the swearing frequnecy in posts based on the day of the week that they were created on. Here's the plot:

![Post scores](Pictures/days%20swearing.png)

The swearing frequency is very consistent across all days of the week.
