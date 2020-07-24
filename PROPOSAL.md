# Data-driven Music Activity Analysis  
![LastFM_RYM](https://i.imgur.com/HhlkLb0.jpg)

## Summary 

The project explores personal music activity, using [Last.fm](https://www.last.fm/), a website that builds a detailed profile of each user's musical taste by recording details of the tracks heard by the user and [RateYourMusic](https://www.rateyourmusic.com/) a collaborative music database used to catalog and rate music (and films). The former however has a 'Report' section that does statistically create reports for past week and year but is quite limited. We use the liberty of having the overall archival data of both the websites to have the ability to visualize overall, yearly, monthly, weekly or even daily stats for artists, their albums, ratings per album or even play counts and various other combinations.  

## Goals

The intention of this project is to understand underlying possibilities of music listening behaviour having personally realised erratic taste in music, e.g. albums with the highest rating don't necessarly have high play count. Being able to create an overall summary of complete music activity from both sources together visually and statistically. Our goal however is still to be clearly specified as we continue to explore and understand our data. 

## Dataset

We're looking at two sources from a certain profile (one of the group members), taken from [LastFM](https://www.last.fm/user/reuben_francis) and [RateYourMusic](https://rateyourmusic.com/~reubenfrancis) profile. 

### LastFM

LastFM keeps tracks of the tracks that have been listened to and logs them. It has an open-source free API that helps extract necessary data from the website, the exports however are in [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer)-style XML. A little block of code can help extract XML data by looping through each page and finally converting it to '.csv' format. The output file consists of following columns:

    {utc_time, artist, album, scrobbles}
    
The resultant data has approximately 50,000 rows, total number of tracks logged since the start.

### RYM

RateYourMusic helps rate albums you've heard and also create a 'wishlist' of albums to be heard. The profile, once authenticated have a direct link to export data in the main website. This however is just a '.txt' file that needs to be preprocessed and converted to '.csv'. This file however needs a lot more cleaning, the columns that are reduced to the following:

    {artist, album, release_date, rating, ownership} # ownership categorises rated and wishlisted

There's a total of around 5,000 rows, total albums rated and wishlisted in count.


## Techniques

- Regression (Simple Linear): Predicting rating for an album by combining the two datasets

- Time Series Analysis (ARIMA): Using timeseries data from LastFM to predict possible progression of play count for a certain       timerange 

- Clustering (K-Means ): Discovering the possible groups with different parameters and cluster count. 

- Supervised Learning (K Nearest Nieighbour):Our task here is to seperate the data into several classes to predict the new sample   joint using feature similarity.

- A possibility of classification as we continue to explore the data.


## Milestones

### *Milestone 1*

Exclusively cleaning artist name duplications and similar problems and combining LastFM and RYM data as a single dataset compromising a few columns. Creating visualizations exclusively for each dataset and realising possible behaviours.

### *Milestone 2*

Being able to possibly create certain models as mentioned in *Techniques* and possibly come up with conclusion on behaviour of the persons music activity. 

### *Milestone 3 (optional)*

A possible solution to  have the visualisation of the project done better while also web scraping more information from RateYourMusic if possible (demands some tedious work for each row of RYM data).

