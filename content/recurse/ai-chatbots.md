+++
description = ""
title = "RC 11: Stanleybot 🤖 1.Oh.n0"
date = "2017-02-15T01:07:01-05:00"
tags = [ "Recurse"]
+++

During my last week at Recurse, I wanted to apply the knowledge I've gained about Machine Learning into a project. During my batch, I spent a portion of my time immersing myself with the terminology, concepts, and tooling but not as much as I hoped building and applying what I'd learned.

On the final week, I wanted to attempt one of the projects on my back burner for a while. I had been thinking about the data that we generate every day on the multiple of services we utilize. Myself, I spend most of my time on data collection sources(noted [here](https://blog.stanzheng.com/recurse/week-1/) and [here](https://blog.stanzheng.com/recurse/halfway-checkin/), chats, taking notes, and email. I was curious if given enough data about myself, would it be plausible to reproduce something that I could have written.



# Collecting the data
The service I use the most if Facebook Messages and Messenger; I have been on the service for multiple year so surely I must have had thousands of conversations. I also a frequent participant in Slack.

- 70K Facebook Messenger Archive messages [using Chris Roth's Chronist Scraper Methodology](https://github.com/cjroth/chronist/blob/master/lib/facebook.py)
- 10K Slack messages focused around conversations about tech and work.
<br/>
<br/>


# LSTM

Recurrent Neural networks using Long short term memory is better explained by these blogs and experts. In short using LSTM is a type of Recurrent Neural Network that is good at keeping context for generative models.

Given my conversations with friends and colleagues, it would give enough context to how I talk and speak hopefully. However, a key issue was that many of the taggings didn't have as because I would have to pull groups of messages and try and map it 1:1. It became a can of worms trying to rework the parsing to pull correct conversation pairs.

- http://colah.github.io/posts/2015-08-Understanding-LSTMs/
- http://suriyadeepan.github.io/2016-06-28-easy-seq2seq/
- http://www.wildml.com/2016/04/deep-learning-for-chatbots-part-1-introduction/
- https://www.youtube.com/watch?v=SJDEOWLHYVo



# Despair and RNNs on Zulip
I was not excited the output I was getting from training the data and the incompleteness of the dataset. I remembered on Zulip someone was talking about a generative text bot mixed with Donald Trump's tweets and the first chapter 1984. To get halfway there with the data I had so far, I could feed it into a RNN to generate text.

- http://karpathy.github.io/2015/05/21/rnn-effectiveness/
- http://nbviewer.jupyter.org/gist/yoavg/d76121dfde2618422139

Utilizing Yoav Goldberg's notebook I was able to feed it all 80K of lines of conversation I had generated in attempt to put out some plausible content. Reading it was like reading my diary, full of conversations that escaped my recent memory but still cringe worthy. (Maybe running it on private conversations isn't very wise...)

```
Theres always next dominion
would look
All the poll, this your pitched sometime and stuff. She use to sit
my new year..
to see a doctor
Here is a time and login pages              canvas and repost
nothing has worked out of my idea)",
```


Conclusion
---
I had fun time bootstrapping my knowledge about machine learning to create a plausible bot of myself. Going forward I'd like to grab conversational pairs and mix my data with a helpbot to have a plausible closed domain bot that could pass. It was the first time I had a good intuition about a machine learning domain problem and how to get better results. I got to use Tensorflow, Jupyter Notebooks, Docker, and a whole load of python scripts to scrape my own data and dig through it. Eventually, it'll become a reality but I don't think anytime soon yet.