# Strategic Launching of Microsoft Entertainment Studios

## Overview
Movie data from IMDB, BoxOffice Mojo, TMDB, and The Numbers was analyzed to provide metrics on the strategic entrance of Microsoft into the entertainment industry. The data provided has been selected based on movies released in the last ten years that were popularity amongst audiences. The return on investment (RoI), studio success, timing of release, and the correlation between runtime and genre ranking were used to make the best recommendations possible.

## Business Understanding
The gateway to Microsoft successfully launching original content from their own entertainment studio relys on answering the following questions:

Which genres provide the largest return on investment?
How does the studio distributing the movie and the time of year it is released alter boxoffice performance?
Does the runtime of a film influence the popularity?

## Data
Large datasets from four major entermainment review websites were used to create a hollistic understanding. All of the tools required to filter, join, and visualize the sets are seen below.
### IMDb
One of the most popular websites for information pertaining to movies consisted of multiple tables within SQL known as Movie Data ERD. I chose to open movie_ratings, movie_basics, persons, and writers. To access this data you will need to extract the zipped file. To easily use sql within pandas, the lambda function is used to import python's sql tools (pysqldf).
### The Movie Database (TMDb)
A community generated database started in 2008 holds extensive metadata for movies, TV Shows, and more. Their international presence boosts the contributions their are able to make to their data. We will use the CSV to gain insight into the average score each genre receives to be compared with IMDb's, which will provide a well-rounded view of audience preference.
### The Numbers(TN)
Trusted by numerous studios and independent film-makers, The Numbers focuses on revenue predictions as well as analytics seen within IMDb's and TMDb's data. I will use the information from thi site to build an understanding of return on investment by creating a percentage from the difference of worldwide gross an production budget, which will be divided by the production budget. This will be joined to the IMDb's dataframe by matching the title of films.
### BoxOffice Mojo
Boxoffice Mojo is an IMDb company. I will use the sum of domestic gross and foreign gross to find the average profit well-known studios have gained over the last ten years. Microsoft can use this information to understand the strategies used by the most successful studios.

## Methods
A consistent filtering system is used to bring each database to focus on movies released from 2012-2022 that received at least the average rating of that set. BoxOffice Mojo is the only dataset where an audience ranking was not filtered. A massive dataframe was created after joining the IMDb movie_ratings and movie_basics to The Numbers's dataset. A RoI column and date filtered to only include the month of movie release created the dataset with a limit of only the top 500 films used for visualization. The average number of films for each genre was 12.89. This created the need to only include genres who met at least that average when generating the visual. Genres such as music and musical were checked to see if they should be combined. After reviewing the films in each category, I determined there was not a need as films within the music genre geniually related to films about the music industry.

BoxOffice Mojo required numerous null values to be dropped, as well as filtering out films who were below the average domestic gross. A new column was created to represent the total profits from the domestic and foreign gross values. An average profit was calculated for each studio. Cross-referencing was required to ensure duplicate studios were combined, such as Lionsgate Films and Lionsgate Studio. I did choose the leave WB (NL) as as separate category because while New Line Cinema is owned by Warner Brothers, New Line is viewed as its own studio.

The Movie Database (TMDb) required switching out numeric genre keys with text. Characters surrounding the numerical values, such as [] needed to be removed for this to happen. Just as I did with the IMDb data, the genres were split out into separate rows to allow for easier mathmatical analysis. TmDb was used to get a pulse on audience popularity so that we were not only relying on monetary information.

## Results
![image](https://user-images.githubusercontent.com/20844445/209029597-50b7f6bc-42f7-4806-be54-da1301f7cfab.png)
The initial investment of any project should be lower than the profit. Action and Adventure movies require a higher production budget, or initial investment, that overshadows profit returns. Biographies, Comedies, and Dramas do not require as much financial backing to make, so the return is much higher.

![image](https://user-images.githubusercontent.com/20844445/209029194-f8942ad1-6545-4ca8-bcd3-d4d7c1bc92f2.png)
Based on the performance of studios who had movies with a domestic gross of at least $29,000,000 and a total profit of at least $139,000,000, we can see Walt Disney/Fox generated the highest average. When we dive further into the structure of this congolmerate, it becomes evident that their profits are brought in from numerous subsidiary companies. This strategy of acquiring smaller studios could provide a higher revenue for Microsoft than trying to start its own studio. Or, if Microsoft wanted to get bought out by one of the "Major Studios" above, they could still release movies under the name Microsoft Studios with split profit between themselves and the larger studio. Being an independent studio does come with its own autonomy;however, trying to compete against each of the studios listed above may prove challenging due to the hold they currently have over the industry. 

![image](https://user-images.githubusercontent.com/20844445/209029715-107c9902-549d-406f-9cfa-d90f1736979c.png)
Projects Microsoft hopes to see the biggest return from should be released in the fall. Our top three months are November, December, and October, which aligns with a higher family outtings due to the holidays. We would not advice releasing films within the months of August or September as those months do not have as many high ranking films.

![image](https://user-images.githubusercontent.com/20844445/209029818-9c1c1e66-38a7-4163-9c88-c7188cc34027.png)
From the TMDb perspective, Documentary films seem to receive the highest popularity ranking; however, there isn't a definitive difference in audience popularity for each genre.

![image](https://user-images.githubusercontent.com/20844445/209029774-ab157c96-2026-4e58-809c-d7cfe37a4137.png)
If we were to focus on the five genres from the RoI graph, we can see that Dramas and Biographies tend to receive a higher ranting when their runtime is over two hours (120 minute). Action and Adventure see spikes in their ratings throughout with varying runtimes. Noticably, we can see above an 8.2 around 90 minutes, 105 minutes, 120 minute, 149 minutes, and 180 minutes. I would suggest taking a closer look at the distrbutors, writers, and directors of the films receiving those ratings to better understand how those ratings were acheived. Comedy should stay under two hours (120 minutes). If you were to venture out into other genres, we can see that films over two hours generally have a better rating.
