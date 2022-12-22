# Strategic Launching of Microsoft Entertainment Studios

## Overview
Analysis of movie data from IMDB, BoxOffice Mojo, TMDB, and The Numbers provided metrics on the strategic entrance of Microsoft into the entertainment industry. The data provided has been selected based on movies released in the last ten years with high popularity amongst audiences. The return on investment (RoI), studio profits, timing of release, and the correlation between runtime and genre ranking were used to make the best recommendations possible. The Walt-Disney-Fox conglomerate shows the highest studio profits, which opened the idea of Microsoft using the same business model they Disney has pursued. We've also noted Drama, Comedy, and Biographies to be genres that require a lower production budget resulting in a higher RoI. A fall release, specifically November, draws the highest profit; however, the length of the movie can influence the rating amongst fans.

## Business Understanding
The gateway to Microsoft successfully launching original content from their own entertainment studio relys on answering the following questions:

Which genres provide the largest return on investment?
How does the studio distributing the movie and the time of year it is released alter boxoffice performance?
Does the runtime of a film influence the popularity?

## Data
Large datasets from four major entermainment review websites were used to create a hollistic understanding. All of the tools required to filter, join, and visualize the sets are seen below.
#### IMDb
The Internet Movie Database(IMDb) is a website that provides information about movies, television shows, and other forms of entertainment. It includes a database of titles, cast and crew members, plot summaries, ratings, and reviews. IMDb also features news and information about the entertainment industry, as well as a section for trailers and other video content. The website is owned by Amazon and is one of the most popular resources for information about movies and television shows. It is used by both industry professionals and general audiences. I will be joining the movie_ratings and movie_basics using the shared column 'movie_id' with a filter for no ratings below 7.5 and at least 3500 votes contibuting to the rating.
#### The Movie Database (TMDb)
The TMDb (The Movie Database) is a community-driven movie and television show database. It is similar to IMDb in that it provides information about movies, television shows, and other forms of entertainment, including cast and crew lists, plot summaries, and ratings. However, TMDb is a non-profit organization and relies on contributions from its community of users to provide accurate and up-to-date information. In addition to its database, TMDb also offers a API (Application Programming Interface) that allows developers to access its data for use in other applications. TMDb is widely used by media professionals and enthusiasts as a resource for information about the entertainment industry. The genre_ids will be converted to text in separate rows so find the average audience rating of movies in the last ten years.
#### The Numbers(TN)
The Numbers is a website that provides financial data and analysis on the film and television industries. It includes information about box office revenues, budgets, production costs, and other financial metrics for movies and television shows. The website also offers analysis and reports on trends and performance in the entertainment industry. The Numbers is a useful resource for industry professionals, investors, and other interested parties looking for detailed financial information about the film and television industries. It is updated regularly with the latest data and analysis. The csv file will be filtered for movies in the last ten years. A calculation will produce a new column for the percent return on investment. Finally, it will be joined to the already combined SQL tables, movie_ratings and movie_basics
#### BoxOffice Mojo
Box Office Mojo is a website that provides detailed box office data for movies and other forms of entertainment. It tracks ticket sales for movies released in theaters, as well as home video and digital sales. The website also offers information on movie budgets and production costs, as well as analysis and reports on industry trends and performance. Box Office Mojo is a valuable resource for industry professionals, investors, and anyone interested in the financial performance of movies and other forms of entertainment. It is updated regularly with the latest box office data. This csv file will be used to report studio profits for movies in the last year that meet at least the average domestic gross and total profits. Upon further research into the entertainment industry, a new column for parent studios was added. 

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

## Conclusion
Overall, paying attention to the strategy of the high-performing studios purchasing smaller studio has resulted booming profits. Microsoft opening their own studio will be costly, and they will be up against strong, established competition. My recommendation is to follow the lead of Walt Disney by starting research into studios with promising content who would be willing to come under a larger name with the promise of monetary help for production budgets. Drama, Comedy, and Biographies are the most cost-effective genres with low production budgets needed resulting in higher returns. Movies should be released in the fall, specifically November to maximize RoI. Audience popularity for some genres can be influenced by the length(runtime) of the movie. For comedies, it is recommended you stay within 1.5-1.7 hour window. Dramas and Biographies tend to be more favorable when they are at least 2 hours.

## Next Steps
Beginning research into purchasable studios of medium to high value for Microsoft to bring on under their entertainment name. Thi mirrors that steps taken by current competitors. Connecting high performing producers, directors, and writers to the above data for potential partnership decisions. MPAA ratings should also be taken into account for popularity and profit.
