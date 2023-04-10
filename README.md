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
### 1. "Budget vs Box Office Revenue with IMDb Rating"
Utilizing the budget and box office revenue variables, we created a scatter plot with a heat map for IMDb Ratings. The heat map demonstrates that higher IMDb Rating films on average had a higher box office revenue. 

The linear regressions r-squared value was around 0.49 so the strength of the model can explain around 49% of the variance in the outcome variable which is relatively high. 

The ROI was also calculated and added to the dataframe. We printed the top 10 highest-grossing movies with ROI and IMDb Rating and found that movies in the Horror genre had the highest ROI. This can be explained by their extremely low budgets compared to the revenue they generated. For example, "Paranormal Activity" had the highest ROI with a budget of $15,0000 and revenue of $193,355,800 giving it an incredbily high ROI percentage of 1,288,939%.

Main Findings: 
- High rated films (Review Ratings) generate more box office revenue on average
- The outcome variable of box office revenue can be explained with a strength of around 49% by the budget. This shows that the more money that is put into the production of a movie, the higher revenue is generated. 
- The horror movie genre is the best movie to make if looking to get the highest ROI percentage or if you have a low budget

### 2. "Top 10 Multigenres for Oscar movies vs. Non-Oscar movies"
For our next analysis, we decided to analyze which movie genres were most commonly found in the top 10 Oscar Award movies vs Non-Oscar movies. Our objective was to analyze the most frequent genre combinations of the movies. We decided to utilize the multigenre data already in the dataset instead of splitting them all into singular genre values since more broad genres such as "Drama" would be overly represented.

Oscar movies most frequent multigenre was "Animation, Adventure, Comedy" movies such as Toy Story, Up, and Monsters Inc.

Non-Oscar movies most frequent multigenre was  "Comedy, Romance" movies such as The 40-Year-Old Virgin, 27 Dresses, and The Holiday.

Two bar graphs were created for the Top 10 Oscar Movies Multigenres and Top 10 Non-Oscar Movies Multigenres. The single genres were color coded in order to get a better representation of which genre was appearing more frequently than others.

The Oscar movies appeared to have more Drama and Adventure movies while Non-Oscar movies had much more Comedy and Thriller movies. This could be explained by the Oscar movies on average being more serious and artistic style movies that are favored by movie critcs while Non-Oscar movies can have more comedy and thrilling fun movies that an average audience would enjoy.

The top 10 multigenres were grouped together into a dataframe by the mean of 'profit', 'revenue', 'budget', 'imdbRating', and 'popularity'.
The top 10 multigenres were grouped together into a dataframe by the sum of 'imdbVotes', 'oscar_wins', and 'oscar_nominations'.

Here are some example analysis tables that were generated:

The three most profitable multigenres on average: 
- ['Adventure', 'Family', 'Sci-Fi']	= $782,410,600
- ['Fantasy'] =	$737,701,800
- ['Adventure', 'Fantasy'] = $705,119,800

The three multigenres with the most oscar wins: 
- ['Drama', 'Romance'] = 24 oscar wins
- ['Action', 'Adventure', 'Drama'] = 23	oscar wins
- ['Action', 'Adventure', 'Sci-Fi']	= 16 oscar wins

Main Findings: 
- If the objective for a successful movie is to win the oscars than picking a genre that is more serious such as Drama or Adventure could be beneficial. Comedy movies are less common for Oscar nominated movies.
- Animation, Adventure, Comedy movies are the most frequent multigenre for Oscar awards and second most common multigenre for Non-Oscar movies. The budget for this multigenre is rather high (think of production companies such as "Pixar" "Walt Disney") but if the funds are there it may be worth it to try and win an Oscar. A good second option would be the Drama and Romance multigenre as it had the highest amount of oscar wins with 24 oscar wins.
- If the success goal is to make a highly rated movie, then the multigenre containing Drama and War may be a good option as they have the highest IMDb Ratings on average.

### 3. "Movie Film Ratings (G, PG, PG-13, R) Analysis"
The next analysis focuses on finding the differences between the four movie film rating (G, PG, PG-13, and R).

Below are the various mean tables for the four film ratings.

After splitting the data into dataframes containing the respective film ratings, we found that:
- G-Rated movies won out on every category. It had the highest review ratings, budget, popularity, revenue, profit, and award wins/nominations.
- Contrastingly, R-Rated movies had the second highest review ratings and award wins/nominations. However had the lowest revenue and budget.
- PG and PG-13 movies were fairly similar in all metrics with PG-13 having sightly higher popularity and award wins/nomination values.

Line graphs were created to demonstrate how Film Rating movies changed throught the year 1961-2015.

PG-13 movies were not introduced until July 1, 1984 which is why it shows up around that timeframe on the line graphs.


PG movies were the most profitable until around 1982 where G movies started to increase. The introduction of PG-13 movies in 1984 may have influence PG movie profits however it seems like PG profits were starting to decrease earlier in 1982. This could be due to the rise in popularity of G movies around that time. PG and PG-13 movies had some good year in the 1990's with high profits. R rated movies always had the least amount of average profit throughout the entire range. This could also be due to the fact that R rated movies have much lower budgets on average.

The average budget was similar for all ratings until around 1996 where G, PG, and PG-13 movie budgets increased. On average, the budget is highest for G-Rated movies and lowest for R-Rated movies.

Similar to the average profits, PG and R movies were the most popular until around 1982where G movies started to increase. With the introduction of PG-13 movies in 1984, we see the decrease in PG and R movies. This could be due to PG and R movies becoming less saturated since films can now be split into a new inbetween rating. G rated movies had a "golden popularity" era around the early 1990's but then all film ratings started even out and similar popularity after. More recently, PG-13 and R rated movies seemed to have had an increase in popularity starting somewhere around 2013.

### 4. "Top 10 Directors vs Revenue and Runtime Regression"

## Conclusion
After our analysis, we have discovered some significant patterns and variables that lead to a succesful movie. 

From our first analysis on Budget vs Box Office Revenue with IMDb Rating...


