# DS300.M11 - Recommender system
## Vietnamese music recommender system for Spotify users

## Table of content
* [1. Introduction and motivation](#1-Introduction-and-motivation)
* [2. Repository structure](#2-repository-structure)
* [3. Data set](#3-data-set)
* [4. Methodologies](#4-methodologies)
* [5. Evaluation metrics](#5-evaluation-metrics)
* [6. Recommendation system](#6-recommendation-system)
* [7. Resutls](#7-resutls)

## 1. Introduction and motivation
Lately, it has shown the great explosion of entertainment market, especially in music.
There are over 60,000 tracks are now uploaded to Spotify every day.
It means Spotify is seeing a new track uploaded to its platform every 1.4 seconds [[1](https://www.musicbusinessworldwide.com/over-60000-tracks-are-now-uploaded-to-spotify-daily-thats-nearly-one-per-second/)].
Moreover, previous research [<a href="https://pubmed.ncbi.nlm.nih.gov/12793587/">2</a>]  has figured out the users preferred listening to music to doing any of other activities as watching television, reading books, and watching movies.
This leads to a need of developing a convenient, efficient and user-personalized recommendation system.

## 2. Repository structure


## 3. Data set
The data set can be found in folder `data`. There are 2 type of data for `content-based method` and `model-based method`.

We employ the [Web API](https://developer.spotify.com/documentation/web-api/) provided by Spotify for collecting the track information from this music platform.
With the API, we collect a set of `1781` Vietnamese tracks as the database for our proposed recommendation system.
For the experiments, we continue to collect tracks from `3 Spotify users`.

The attributes of a track are classified into 2 types: `basis information` and `acoustic features`.
```angular2html
Editorial features: date_added, artists, track_name, id, uri, track_href, analysis_url.
Acoustic features: popularity, danceability, energy, key, loudness, mode, speechiness, acousticness, instrumentalness, liveness, valence, tempo, duration_ms, time_signature.
```

Some statistics of the data:
```angular2html
Content-based method:
    User 1: 13 tracks.
    User 2: 32 tracks.
    User 3: 20 tracks.
```

```angular2html
Model-based method:
```
<p align="center"><img src="https://raw.githubusercontent.com/githubbinh/DS300.M11-Recommender-system/feature/branch/images/user_data.png" width="1000"></p>
<p align="center"><i>Fig. 1. Label distribution of each users' data.</i></p>

## 4. Methodologies
`Content-base method`: We experiment on the `track_name` feature collected from the users' frequently listened track names and `acoustic features` separately for computing the similarity. 

## 5. Evaluation metrics
`Human evaluation`: The list of top 10 recommended track names is given to the user in order to get the feedback. Then,
number of accepted track names are aggregated to have the final evaluation score. The metric pipeline are visualized in
Fig. 2.
<p align="center"><img src="https://raw.githubusercontent.com/githubbinh/DS300.M11-Recommender-system/feature/branch/images/human_avaluation.png" width="1000"></p>
<p align="center"><i>Fig. 2. Human evaluation pipeline.</i></p>

`k-fold Cross-validation`: As the data sets for training machine learning models are small in size. We take advantage of
k-fold Cross-validation in order to train machine learning model.

## 6. Recommendation system
<p align="center"><img src="https://raw.githubusercontent.com/githubbinh/DS300.M11-Recommender-system/feature/branch/images/recommendation_api.png" width="1000"></p>
<p align="center"><i>Fig. 3. Web API recommendation system.</i></p>

## 7. Resutls

