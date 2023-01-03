# Strategic Launching of Microsoft Entertainment Studios

## Overview
Analysis of movie data from IMDB, BoxOffice Mojo, TMDB, and The Numbers provided metrics on the strategic entrance of Microsoft into the entertainment industry. The data provided has been selected based on movies released in the last ten years with high popularity amongst audiences. The return on investment (RoI), studio profits, timing of release, and the correlation between runtime and genre ranking were used to make the best recommendations possible. The Walt-Disney-Fox conglomerate shows the highest studio profits, which opened the idea of Microsoft using the same business model they Disney has pursued. We've also noted Drama, Comedy, and Biographies to be genres that require a lower production budget resulting in a higher RoI. A fall release, specifically November, draws the highest profit; however, the length of the movie can influence the rating amongst fans.

## Business Understanding
The gateway to Microsoft successfully launching original content from their own entertainment studio relies on answering the following questions:

- Which genres provide the largest return on investment?
- How does the studio distributing the movie and the time of year it is released alter boxoffice performance?
- Does the runtime of a film influence the popularity?

## Data
Large datasets from four major entermainment review websites were used to create a hollistic understanding. All of the tools required to filter, join, and visualize the sets are seen below.
#### IMDb
The Internet Movie Database(IMDb) is a website owned by Amazon that provides information about movies, TV shows, and other forms of entertainment.
#### The Movie Database (TMDb)
The TMDb (The Movie Database) is a non-profit, community-driven database of movies and TV shows that provides information about cast and crew, plot summaries, and ratings.
#### The Numbers(TN)
The Numbers is a website that provides financial data and analysis on the film and TV industries. 
#### BoxOffice Mojo
Box Office Mojo is a website that tracks box office data for movies and other forms of entertainment.

## Methods
In preparation for visualization, the following strategies were used to clean, sort, and join datasets:

- Filter each database to focus on movies released from 2012-2022 that received at least the average rating of that set, except for BoxOffice Mojo which does not have audience ratings.
- Create a massive dataframe by joining the IMDb movie_ratings and movie_basics to The Numbers's dataset.
- Create a RoI column and date filter to only include the month of movie release in the dataset, with a limit of only the top 500 films for visualization.
- Determine the average number of films for each genre, and only include genres that meet or exceed this average when generating visualizations.
- Check if certain genres, such as music and musical, should be combined.
- Drop null values and filter out films below the average domestic gross in the BoxOffice Mojo dataset.
- Create a new column to represent total profits from the domestic and foreign gross values.
- Calculate the average profit for each studio, and cross-reference to combine duplicate studios.
- Use TMDb to replace numeric genre keys with text and remove characters surrounding the values.
- Split the genres into separate rows for easier mathematical analysis.

## Results
![image](https://user-images.githubusercontent.com/20844445/209029597-50b7f6bc-42f7-4806-be54-da1301f7cfab.png)
The initial investment of any project should be lower than the profit. Action and Adventure movies require a higher production budget, or initial investment, that overshadows profit returns. Biographies, Comedies, and Dramas do not require as much financial backing to make, so the return is much higher.

![image](https://user-images.githubusercontent.com/20844445/209188318-8a43adda-4487-44ae-b13d-55bc8518ef2c.png)

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

## Repository Structure

```
├── ZippedData
├── Fell-Phase-1.ipynb
├── README.md
├── presentation.pdf

```
