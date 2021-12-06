<b><span style="color:red">NSFW WARNING: NOTE THAT THERE ARE UNCENSORED SWEAR WORDS IN THIS ASSIGNMENT</span></b>.

# Analyzing Bad Mouths

To keep data processing times minimal, I selected around 100 posts from 78 subreddits to analyze. 

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
To find which non-swear words are commonly said with swear words, I trained a logistic regression model to predict whether a post swears or not based on the words in the post and then analyzed the coefficients of the features in the trained logistic regression. 
