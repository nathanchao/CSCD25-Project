# Analyzing Bad Mouths

## Data Story
url: https://nathanchao.github.io/CSCD25-Project/
## Abstract
A large portion of society has deemed certain words to be "bad", however some\
people still choose to use these words in their everyday speech. My project\
aims to analyze the behaviour of these people. The project will hopefully give\
hints to deeper questions such as why people swear and what kinds of societal\
effects swearing has. I would also like to understand at a deep level the kinds\
of people that swear.\
\
Analyzing posts on Reddit is the ideal place to analyze these behaviours. \
Users can post anonymously, so users are more free to speak their mind freely\
without worrying about repercussions. The free-form speech posted on Reddit \
allows us to analyze human speech in its most natural form without any major \
influences.

## Research Questions
**Primary research question:** In which communities is swearing most/least favoured\
(based on the score of posts that have a swear word)?

**Additional Research Questions:**
* Do people swear more or less in certain communities? If so, which communities?
* Does swearing affect the score of a post? If so, how?
* What behaviours on Reddit are associated with swearing?
* When is swearing the most/least common? 

## Proposed additional datasets:
None

## Methods:
**Overview:**

I plan to mainly use `text_submissions.csv.gz` for my analyses. If additional \
analyses are needed, I can easily apply similar techniques to the data in\
`text_comments.csv.gz`. To manage the size of the datasets that I have chosen, \
I will make use of the pandas "sample" function. This function will allow me \
to work with a smaller set of the data without losing any of the important \
properties of the data.

**Initial/Exploratory Analysis:**

I will give a brief overview of the methods I used to transform the raw data\
into a form appropriate for my project and then perform initial/exploratory \
analysis. This process is done in `Project_Milestone.ipynb`. First, I removed\
submissions without selftext. I manually inspected the data to do so. Upon\
inspection, I noticed that some submissions had selftext of "[removed]", NaN, or \
"[deleted]" and removed all these submissions. Then I split the postings into\
words using nltk.word_tokenize. I then removed extra sequences of \
characters that aren't part of a word (e.g., "\n", url's, and punctuation). \
From there, I manipulated the data into a dataframe that shows the frequency \
of all swearwords in each comment. For initial/exploratory analysis, I found \
the percentage of submissions containing a swear word and plotted the \
percentage of words that are swear words in each post with a swear word in it.

**Methods that will be used to answer research questions:**

To answer the research questions, I need methods for the following three tasks:\
grouping posts by community/time, comparing the scores of posts, and finding \
activities on Reddit that are correlated with swearing. I will explain the\
methods for each of these tasks in the following sections.

**Grouping posts by community/time**:

For three of the research questions, I will be looking at swearing within \
individual communities/time periods. To do this, I will need to transform the data that I \
have so that it's grouped by community/time. After doing that, I will easily be able\
to find the median/mean score/swearing frequency of posts within a given \
community/time period. A visualization technique that I will use a is bar chart to \
visually compare swearing frequency of posts in different communities/time periods.

**Comparing the scores of posts:**

For two of the research questions, I will be comparing the scores of different \
posts. To rank posts by score, I will use percentiles. This means that box \
plots will be an appropriate visualization technique that I will make good use\
of.


**Finding activities on Reddit that are correlated with swearing:**


I want to see if there are certain non-swear words or topics that people who\
swear like to use and talk about. To do this, I will use logistic regression \
with the words of each submission being the features. This will show me which \
non-swear words are commonly used with swear words.


## Organization within the team:
I will be working by myself, so I will do all the work.
