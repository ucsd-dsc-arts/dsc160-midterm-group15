# Project Title

DSC160 Data Science and the Arts - Midterm Project Repository - Spring 2020

Project Team Members: 
- Nathan Tsai, nhtsai@ucsd.edu
- Hanbyul Ryu, h9ryu@ucsd.edu
- Joseph Del Val, jdelval@ucsd.edu
- Jacob Benson, jtbenson@ucsd.edu

## Abstract

(10 points) 

This analysis seeks to expand upon the previous genre classification covered in class in broadening the scope to a greater number of genres and tracks, utilizing the diverse and vast resources available from the Spotify API. Using songs sampled from different genre playlists generated by Spotify’s API, we seek to answer the question: which genres will be classified with the highest degree of accuracy? We hypothesize that genres considered intuitively unique by humans, such as Hip Hop and Classical, will be classified correctly most often. Spotify’s API will provide us with the features we will use in this analysis, such as energy, loudness, acousticness, and tempo. In addition to this, we will personally extract features from the sample audio including Time Series, Mel Frequencies, and MFCCs. In order to carry out our analysis to completion we will make use of librosa, pandas, and scikit-learn. 

While much of our analysis will lie in the exploratory data analysis and classification, we will also make use of visualization: both in visualizing the feature differences between genres during the exploratory stage, as well as visualizing the differences in classification accuracy in order to communicate our results. The significance of this analysis lies in its ability to highlight the particularly unique genres amid the music we listen to and in its use of Spotify— a popular music streaming service that is used by millions of listeners worldwide.


## Data

(10 points) 

Our cultural data source was a collection of playlists from the online music streaming service Spotify. The playlists in question were hand-crafted by Spotify in order to provide music to listeners who are seeking a specific genre.
From Spotify's API, we acquired information about the tracks contained on 18 different playlists.

90s Rock Anthems: https://open.spotify.com/playlist/37i9dQZF1DX1rVvRgjX59F?si=GqFfPLIFTayeACySPYQ3Rg  
80s Rock Anthems: https://open.spotify.com/playlist/37i9dQZF1DX1spT6G94GFC?si=8cA6oEgdS1ik6QY9o897ew  
00s Rock Anthems: https://open.spotify.com/playlist/37i9dQZF1DX3oM43CtKnRV?si=umHsbMXiR-WdwATVR8LcVA  
Rock Classics: https://open.spotify.com/playlist/37i9dQZF1DWXRqgorJj26U?si=uGZNvnwPQlWgrr6GhUXbHQ  
Classical Essentials: https://open.spotify.com/playlist/37i9dQZF1DWWEJlAGA9gs0?si=OqZq_LxFRIKruh9OoZa6SA  
Classical Reading: https://open.spotify.com/playlist/37i9dQZF1DWYkztttC1w38?si=39fZeozBTiKwD3ZzBHXw7w  
Classical Focus: https://open.spotify.com/playlist/37i9dQZF1DXd5zUwdn6lPb?si=GcoKHKNRROWY3jNk0Zz4rQ  
I Love My West Coast Classics: https://open.spotify.com/playlist/37i9dQZF1DX9sQDbOMReFI?si=ICj1Y695Qjm1PrMKZNJ7PQ  
I Love My '90s Hip Hop: https://open.spotify.com/playlist/37i9dQZF1DX186v583rmzp?si=d-69VQS2S5We01fPAJy2VA  
Get Turnt: https://open.spotify.com/playlist/37i9dQZF1DWY4xHQp97fN6?si=6eHGocEHSxisFo_WoeTDEQ  
Classic Punk: https://open.spotify.com/playlist/37i9dQZF1DX3LDIBRoaCDQ?si=G3vdAY5lRIuUTUHB7Osl1g  
Punk Essentials: https://open.spotify.com/playlist/37i9dQZF1DXd6tJtr4qeot?si=-swGdu91S56d9rccIrOABA  
New Punk Tracks: https://open.spotify.com/playlist/37i9dQZF1DX0KpeLFwA3tO?si=TwGXWilrSLKTrp-VoECasA  
Jazz Classics: https://open.spotify.com/playlist/37i9dQZF1DXbITWG1ZJKYt?si=NVWfjjWQQ3uWmiGwjz5m_g  
Jazz Classics Blue Note Edition: https://open.spotify.com/playlist/37i9dQZF1DWTR4ZOXTfd9K?si=NpJY-SqhRXax4m7QiNb1Ag  
Late Night Jazz: https://open.spotify.com/playlist/37i9dQZF1DX4wta20PHgwo?si=-IQHHoQbSSuXRvJFR3HYgw  
Smooth Jazz: https://open.spotify.com/playlist/37i9dQZF1DXdwTUxmGKrdN?si=FPV6wJ-BTneKUIO6tRT9Vw  
Jazz X-Press: https://open.spotify.com/playlist/37i9dQZF1DX85XJl1mZAlp?si=OQYyVza3Qie0NCxJ7UNkKQ  

The music contained within these playlists spans centuries, ranging from Cello Suits by Johann Sebastian Bach, to Hip Hop music composed a few days ago. And, of course, the artists who created these songs are equally as varied. The playlists themselves are quite frequently updated by Spotify, and thus very recent cultural artifacts.  
As for the matter of whether or not it is a digital native, this too depends on which song is in question. Many of the classical and jazz pieces may be recordings of a recent performance of the song, whereas many of the modern tracks could possibly be digital releases from the beginning. 
It is from the heterogeny of this dataset that we seek to find underlying patterns and different characteristics of each of these genres. In finding these patters, we will eventually be able to classify one from the other, and from this find how near-- or far-- some of these genres are from one another.

In terms of the data values we are analyzing, each feature comes from one of two origins. 
One of these origins is Spotify's API itself. Spotify's API provides us with many of its own analyses of the song in question. These range from tempo or time signature, to how instrumental and how "danceable" the music is.
As for the other origin, we ourselves analyzed the 30 second samples provided to us by Spotify's API. From this 30 second sample, we extracted the time series, Mel frequencies, and MFCCs of each sample audio.

## Code

(20 points)

The code written in order to acquire our data is available here: [link](code/Data%20Scraping.ipynb)  
Here, we made use of Spotify's API in order to retrieve information about the tracks contained inside 18 different playlists. These were then put into pandas dataframes and saved as CSV files.

The code written in order to process this data and extract features is available here: [link](code/Data%20Processing.ipynb)  
Here, we made use of librosa in order to extract features from Spotify's 30 second sample audio, adding these features to the pandas dataframes from the last section, and saving them as separate CSV files.

The code written in order to conduct exploratory data analysis is available here: [link](EDA.ipynb)  
Here, we used Pandas and Matplotlib to explore the data we had collected.

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- data acquisition/scraping
- cleaning
- analysis
- generating results. 

Link each of your notebooks or .py files within this section, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:
- Why is this culturally relevant?
- How does your computational approach differ from the traditional art historical, musicological, manuel/subjective approach to analyzing your cultural subject? 
- How do you think the original artists/musicians would respond to this type of analysis? Would it change/inform their practice in some way?
- How do your results relate to broader social, cultural, economic political, etc., issues? 
- In what future directions could you expand this work?

## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project
- Does this code require other pip packages, software, etc?
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
