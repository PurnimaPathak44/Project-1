# Project-1: Succesful Movies Analysis

## Background

A new film company called "Rutgers" wants to produce a successful movie. In order to do that, they came across The Group-5 Data Analysis Company and provided them with a list of datasets that contains Movies information from 1962 to 2015. Based on these datasets, The Group-5 Agency’s task is to aggregate the data and find the trends that tend to show what factors are and are not responsible for a successful movie and present it to Rutgers to make strategic decisions regarding their production of movies.

## Defining a Successful Movie
The first question The Group-5 Agency wanted to answer was "What is a succesful movie?" 

Financial success? Critical acclaim? Public popularity? 

Because success can be defined in several different ways depending on what a company desires, The Group-5 Agency decided to create a list of success metrics.

- Box Office Revenue $
- Profit and Return on Investment (ROI)
- Movie Review Ratings (IMDb, Rotten Tomatoes, Metacritic)
- Award Wins/Nominations (Oscars)
- Popularity

The Group-5 Agency performed analysis on all five of these success metrics. 

This provided Rutgers with multiple options for how they will produce their version of a successful movie.

## Data Collection and Cleanup
Utilizing Kaggle datasets and The Open Movie Database API (OMDb API) the main dataset was created.

### Kaggle: 
The main dataset that we used via Kaggle was 1287 movie data from TMDB(The Movie Database) from the year 1961 - 2015.

Columns included: 
"Movie ID, Budget, Revenue, Profit, Title, Cast, Directors, Popularity, Keywords, Runtime, Genres, Production Company, and Release Date."

### OMDb API: 
Used Movie IDs in Kaggle Data to create requests from the OMDb API.

Supplemented Kaggle Data with:
"Writer, Awards, Ratings, Metascore, Imdb Rating, and Imdb Votes" for each movie

After deleting unwanted columns and merging the API data with the main Kaggle data, we had a dataset containg 1178 rows and 26 columns.

## Analysis and Findings
### "Budget vs Box Office Revenue with IMDb Rating"
Utilizing the budget and box office revenue variables, we created a scatter plot with a heat map for IMDb Ratings. The heat map demonstrates that higher IMDb Rating films on average had a higher box office revenue. 

The linear regressions r-squared value was around 0.49 so the strength of the model can explain around 49% of the variance in the outcome variable which is relatively high. 

The ROI was also calculated and added to the dataframe. We printed the top 10 highest-grossing movies with ROI and IMDb Rating and found that movies in the Horror genre had the highest ROI. This can be explained by their extremely low budgets compared to the revenue they generated. For example, "Paranormal Activity" had the highest ROI with a budget of $15,0000 and revenue of $193,355,800 giving it an incredbily high ROI percentage of 1,288,939%.

Main Findings: 
- High rated films (Review Ratings) generate more box office revenue on average
- The outcome variable of box office revenue can be explained with a strength of around 49% by the budget. This shows that the more money that is put into the production of a movie, the higher revenue is generated. 
- The horror movie genre is the best movie to make if looking to get the highest ROI percentage or if you have a low budget

### "Top 10 Multigenres for Oscar movies vs. Non-Oscar movies"
For our next analysis, we decided to analyze which movie genres were most commonly found in the top 10 Oscar nominated movies vs Non-Oscar movies. Our objective was to analyze the most frequent genre combinations of the movies. We decided to utilize the multigenre data already in the dataset instead of splitting them into singular genre values since more broad genres such as "Drama" would be overly represented.

### "Movie Film Ratings (G, PG, PG-13, R) Analysis"

### "Top 10 Directors vs Revenue and Runtime Regression"

## Conclusion
After our analysis, we have discovered some significant patterns and variables that lead to a succesful movie. 

From our first analysis on Budget vs Box Office Revenue with IMDb Rating...


