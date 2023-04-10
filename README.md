# Project-1: Succesful Movies Analysis

## Background

A new film company called "Rutgers" wants to produce a successful movie. In order to do that, they came across The Group-5 Data Analysis Company and provided them with a list of datasets that contains Movies information from 1962 to 2015. Based on these datasets, The Group-5 Agency’s task is to aggregate the data and find the trends that tend to show what factors are and are not responsible for a successful movie and present it to Rutgers to make strategic decisions regarding their production of movies.

## Defining a Successful Movie
The first question The Group-5 Agency wanted to answer was "What is a succesful movie?" 

Financial success? Critical acclaim? Public popularity? 

Because success can be defined in several different ways depending on what a company desires, The Group-5 Agency decided to create a list of success metrics.

- Box Office Revenue $
- Return on Investment (ROI)
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
### "Top 10 Multigenres for Oscar movies vs. Non-Oscar movies"
### "Movie Film Ratings (G, PG, PG-13, R) Analysis"
### "Top 10 Directors vs Revenue and Runtime Regression"

## Conclusion
After our analysis, we have discovered some significant patterns and variables that lead to a succesful movie. 
