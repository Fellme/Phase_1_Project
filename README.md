# Strategic Launching of Microsoft Entertainment Studios
[Morgan Fell](https://github.com/Fellme)

# Overview
I analyzed movie data from various sources to determine the best strategy for Microsoft's entrance into the entertainment industry. We selected data on popular movies released in the last 10 years and analyzed factors such as return on investment (RoI), studio profits, release timing, and the relationship between runtime and genre ranking. Our findings showed that the Walt-Disney-Fox conglomerate had the highest studio profits, suggesting that Microsoft could adopt a similar business model. We also found that genres such as Drama, Comedy, and Biographies have lower production budgets and higher RoIs. November releases tend to be the most profitable, though movie length can affect ratings.

# Business Understanding
The gateway to Microsoft successfully launching original content from their own entertainment studio relys on answering the following questions:
1. Which genres provide the largest return on investment?
2. How does the studio distributing the movie and the time of year it is released alter boxoffice performance?
3. Does the runtime of a film influence the popularity?

# Data
Large datasets from four major entermainment review websites were used to create a hollistic understanding. All of the tools required to filter, join, and visualize the sets are seen below.
#### IMDb
The Internet Movie Database(IMDb) is a website owned by Amazon that provides information about movies, TV shows, and other forms of entertainment.
#### The Movie Database (TMDb)
The TMDb (The Movie Database) is a non-profit, community-driven database of movies and TV shows that provides information about cast and crew, plot summaries, and ratings.
#### The Numbers(TN)
The Numbers is a website that provides financial data and analysis on the film and TV industries. 
#### BoxOffice Mojo
Box Office Mojo is a website that tracks box office data for movies and other forms of entertainment.

# Methods
To prepare the data for visualizations I will be using the following steps to clean each set to answer the questions listed at the beginning.

**Question 1:** Both SQL tables, *movie_basics* and *movie_ratings* will be filtered for release dates and ratings. This will then be joined the cleaned *tn_data_og* set using the primary title. Two new cou=lumns will be added for the month of release and the return on investment of genres. Only genres that met the average number of films will be used for visuals. 

1. Filter each database to focus on movies released from 2012-2022 that received at least the average rating of that set. Do not filter the BoxOffice Mojo dataset based on audience ranking.
2. Create a large dataframe by joining the IMDb movie_ratings and movie_basics with The Numbers's dataset.
-------------------------------------------------------------------------------------------------------------------------------
**Question 3** From the joint dataframes a new column will need to represent the best time of year for releases

3. Create a RoI column and filter the data to include only the month of movie release. 
-------------------------------------------------------------------------------------------------------------------------------
**Question 2** BoxOffice Mojo provides studio performance that can be used to point Microsoft towards a successful studio whose strategies and processes they could mirror 

4. Calculate the average number of films per genre (35.4). Only include genres that meet or exceed this average when generating visualizations.
5. Check if the music and musical genres should be combined.
6. Drop null values and filter out films with domestic gross below the average from the BoxOffice Mojo dataset.
7. Create a new column to represent total profit from domestic and foreign gross values. Calculate the average profit for each studio.
8. Combine duplicate studios, such as Lionsgate Films and Lionsgate Studio.
9. Assign parent studios to each film using the abbreviations to create a dictionary

# Results

**Which genre(s) produced the largest return on investment?**

The genres whose production budget is lower than their return on investment are the most cost-effective when starting a studio. This way Microsoft can spend little money up front with large returns.

- Thriller, Drama, and Comedy are the only genres to meet this goal.
- Adventure, Action, and Sci-Fi are popular but would require microsoft to invest a lot of money upfront running the risk of a negative return.
- I assume the costs are influenced by the excessive special effects budgets

![image](https://user-images.githubusercontent.com/20844445/210695657-831aaf15-131c-4af0-8000-1680946f114e.png)

**Does the studio influence movie success?**
- The studio producing most successful films is Walt Disney and Fox. Yes, studios do have an impact on movie success. 
- I noticed in researching that all of the studios listed have bought or acquired through purchase many studios who contribute to their profit
- This is a saturated market with established competition. Microsoft may want to look into purchases small to medium studios in an effort to mirror the success of Walt Disney and Fox
![image](https://user-images.githubusercontent.com/20844445/210697010-b1ef8f4a-2c92-49a6-9bba-53d89a9c4aaa.png)


**When is the best time to release films?**
- Microsoft should aim for a late fall/winter release, November-December
- The months of January, August, and April should be avoided
![image](https://user-images.githubusercontent.com/20844445/210696353-80d3ef9c-0a93-4aa3-87e9-8cebf5722151.png)


**Does the runtime of a genre influence audience popularity?**
- Comedies should be no longer than 105 minutes as this is when they receive the highest rating among audiences
- Sci-Fi, Drama, and Adventure should aim for a 169 minute runtime to achieve high ratings
- Action and Thriller were ranked highest at 149 minutes and 162 minutes

![image](https://user-images.githubusercontent.com/20844445/210696487-7ec1e093-3e3c-4801-a6ef-ec444da0a504.png)

## Conclusion
- Acquiring smaller studios with promising content, in order to potentially boost profits and tap into established competition.

- Produce cost-effective genres: Drama, Comedy, and Biographies

- Release in the fall, specifically November to maximize profits

- Comedies should be no longer than 1 hr. 45 minutes

- Adventure, Drama, and Thrillers should be at least 2hrs. 49 minutes

# Next Steps
- Beginning research into purchasable studios of medium to high value for Microsoft to bring on under their entertainment name. This mirrors that steps taken by current competitors.
- Connecting high performing producers, directors, and writers to the above data for potential partnership decisions.
- MPAA ratings should also be taken into account for popularity and profit.

# For More Information
Please contact Morgan Fell: [morgan13.fell@gmail.com](morgan13.fell@gmail.com)

# Repository Structure

```
├── ZippedData
├── Fell-Phase-1.ipynb
├── presentation.pdf
├── README.md

```
