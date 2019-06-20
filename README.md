# Predicting Churn using PySpark

## Table of contents

- [Installation](#installation)
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Project Structure](#project-structure)
- [Reflections](#reflections)
- [References](#references)


## Installation

In order to execute the Jupyter Notebook you should have **Anaconda 4.5.11** and **python 3.6.6** installed. 
The notebook needs pyspark, matplotlib, numpy and pandas libraries. These are available as part of Anaconda installation and don't need any additional installation.

- Clone the repo: `git clone https://github.com/kvsrohit/sparkify.git`
- Run the Jupyter Notebook

## Project Overview

Sparkify is an online music streaming service that allows its users to listen and manage their favourite music. Sparkify offers its services in two tiers. The free tier where users can use Sparkify services for free but songs are interspersed with commercial breaks. The paid tier on the other hand is a premium service that plays ad free music at a monthly subscription fee.

Users can add songs to their play list, like or dislike songs, add other users as friends (possibly for sharing playlists) along with upgrading, downgrading or cancelling subscription. Each of the action taken by user is added to an event log which contains event type, timestamp of the event along with user name,  subscription tier and other event specific details.

Based on the usage pattern of users, Sparkify would like to predict if a user is at risk of leaving or downgrading their subscription. This will help them identify users who can be icentivised by means of discounts so that they stay.

## Problem Statement
Users cancelling the subscription or downgrading their account is a potential revenue loss. Sparkify would like to avoid and minimize users cancelling or downgrading the subscription.
The goal of this project is to apply data analysis and machine learning to predict if a user is at risk of cancelling the subscription. 

- The data is available in form of user events in json format
- Data needs pre-processing in form of
	- Clean up of missing or unusable data
	- Feature extraction to extract meaningful information
- The pre-processed data is then used to train several superwised machine learning model.
- The best suited model is then chosen to predict future data

## Project Structure

```text
Sparkify/
├── Sparkify.html
├── Sparkify.ipynb
├── mini_sparkify_event_data.json
└── README.md
```

- Sparkify.html                 ==> Generated report from notebook
- Sparkify.ipynb                ==> Notebook
- mini_sparkify_event_data.json ==> Sparkify user event log in json format

## Reflections

- Several features like average session duration, songs listenred per session have been averaged out for entire period. Splitting it 'week on week' could reveal interesting trends, as a shrinking session duration over the period may be a better indicator of users prone to churn. This may also improve accuracy of model.

- Additional information about user profile like user's age group, interests if made available, could have been very useful.

- We can derive the song genre based on title and external lookup. If users liking a particular genre are churning more, this could indicate issues with out recommendation engine.


## References
1. https://spark.apache.org/docs/latest/api/python/
1. https://medium.com/usf-msds/choosing-the-right-metric-for-evaluating-machine-learning-models-part-2-86d5649a5428
1. https://medium.com/thalus-ai/performance-metrics-for-classification-problems-in-machine-learning-part-i-b085d432082b
1. https://classroom.udacity.com/nanodegrees/nd025-ent/parts/577ca1f8-ed5e-4bbd-ab90-5934a870934e
