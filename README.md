# Tales from the Crypto (Unit 12 Homework)

### Introduction

This analysis looks at Bitcoin and Ethereum news articles pulled from NewsAPI. I used 50 pages worth of relevant artciles for each cryptocurrency topic. This analysis is divided into 3 parts:

1. Sentiment Analysis (#Sentiment_Analysis)
2. Natural Language Processing (NLP) (#NLP)
3. Named Entity Recognition (NER) (#NER)

### Sentiment Analysis <a name="Sentiment_Analysis"></a>

For this section, I used polarity scores from the nltk libary to determine the compound, positive, negative and neutral scores for each cryptocurrency. Below are the table of results:

![Bitcoin Describe](Images/bitcoin_describe.png)

![Ethereum Describe](Images/eth_describe.png)

Using descripting statistics above, we have the following conclusions:
- Ethereum had the highest mean positive score at .0754
- Ethereum had most negative score with a minimum compound rate of -0.4939
- Ethereum also had the most positive score with the maximum compound rate of 0.8779


### Natural Language Processing <a name="NLP"></a>

In this section, I split the contents of each article into tokens, each with lowercase and without punctuation. In addition to the usual dictionary of english stopwords, I also included these stopwords

`sw_addons = {'reuters','photo','seen', 'illustration', 'taken', 'reutersdado', 'stafffile', 'dado', 'ruvic', 'basically', 'also'}'

These were frequently used words that came up because they referred to the source of the news (Reuters) and to descriptions of photos or photogrophers that usually accompany the news articles. They should not be considered because they are not really part of the article's content.

After cleaning up the articles and converting them to tokens, I looked for the most common bigrams for Bitcoin and Ethereum. The results are shown below and we can see that most of the bigrams are similar in both sets keywords. Presumbaly, there are in the same articles that were pulled and are also considered as alternatives to each other, so would be described similarly.

![Bitcoin Bigram](Images/bitcoin_bigrams.png)

![Ethereum Bigram](Images/eth_bigrams.png)

And then I looked at the 10 most frequently used words for each keyword which is shown below:

![Bitcoin top10](Images/bitcoin_top10.png)

![Ethereum top10](Images/eth_top10.png)

Lastly, we rended the tokens above into a word cloud that would summarize the news for each coin.

![Bitcoin wc](Images/bitcoin_wc.png)

![Ethereum wc](Images/eth_wc.png)


### Named Entity Recognition <a name="NER"></a>

In this section, I used a named entity recognition model for both coins and visualized the tags using Spacy

![Bitcoin ner](Images/bitcoin_ner.png)

![Ethereum ner](Images/eth_ner.png)