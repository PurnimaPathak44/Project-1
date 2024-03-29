# Project-1: Succesful Movies Analysis
# Group-5: Kirby Judd, Purnima Pathak, David Jolia, Anthony Youssef

## Background

A new film company called "Rutgers" wants to produce a successful movie. In order to do that, they came across The Group-5 Data Analysis Company and provided them with a list of datasets that contains Movies information from 1962 to 2015. Based on these datasets, The Group-5 Agency’s task is to aggregate the data and find the trends that tend to show what factors are and are not responsible for a successful movie and present it to Rutgers to make strategic decisions regarding their production of movies.

## Defining a Successful Movie
The first question The Group-5 Agency wanted to answer was "What is a successful movie?" 

Financial success? Critical acclaim? Public opinion? 

Because success can be defined in several different ways depending on what a company desires, The Group-5 Agency decided to create a list of success metrics.

- Financial Success (Box Office Revenue $, Return on Investment (ROI), and Profitability)
- Award Wins/Nominations (Oscars)
- Movie Review Ratings (IMDb, Rotten Tomatoes, Metacritic)
- Popularity

The Group-5 Agency performed analysis on all four of these success metrics. 

Our main questions are: 
- "What variables influence Box Office Revenue success, ROI, and profitability?"
- "What variables influence Award Wins/Nominations (Oscars)?"
- "What variables influence Movie Review Ratings (IMDb, Rotten Tomatoes, Metacritic)?"
- "What variables influence Popularity?"

This provides Rutgers with multiple options for how they will produce their version of a successful movie.

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

After deleting unwanted columns and merging the API data with the main Kaggle data, we had a dataset containing 1178 rows and 26 columns.

## Analysis and Findings
### 1. "Budget vs Box Office Revenue with Review Ratings"
Utilizing the budget and box office revenue variables, we created a scatter plot with a heat map for Review Ratings. The heat map demonstrates that higher Review Rating films on average had a higher box office revenue. 

![Budget vs Box Office IMDB heatmap](https://user-images.githubusercontent.com/124934770/231001850-147f6650-e0ac-4637-83ad-7310559e0503.png)

The linear regressions r-squared value was around 0.49 so the strength of the model can explain around 49% of the variance in the outcome variable which is relatively high. 

![Budget vs Box Office regression](https://user-images.githubusercontent.com/124934770/230952967-ad323e27-2e09-448e-b17a-4ebfd57cfa86.png)

The ROI was also calculated and added to the dataframe. We printed the top 10 highest-grossing movies with ROI and Review Rating and found that movies in the Horror genre had the highest ROI. This can be explained by their extremely low budgets compared to the revenue they generated. For example, "Paranormal Activity" had the highest ROI with a budget of $15,0000 and revenue of $193,355,800 giving it an incredibly high ROI percentage of 1,288,939%.

Main Findings: 
- High rated films (Review Ratings) generate more box office revenue on average
- The outcome variable of box office revenue can be explained with a strength of around 49% by the budget. This shows that the more money that is put into the production of a movie, the higher revenue is generated. 
- The horror movie genre is the best movie to make if looking to get the highest ROI percentage or if you have a low budget

### 2. "Top 10 Multigenres for Oscar movies vs. Non-Oscar movies"
For our next analysis, we decided to analyze which movie genres were most commonly found in the top 10 Oscar Award movies vs Non-Oscar movies. Our objective was to analyze the most frequent genre combinations of the movies. We decided to utilize the multigenre data already in the dataset instead of splitting them all into singular genre values since more broad genres such as "Drama" would be overly represented.

Oscar movies most frequent multigenre was "Animation, Adventure, Comedy" movies such as Toy Story, Up, and Monsters Inc.

Non-Oscar movies' most frequent multigenre was "Comedy, Romance" movies such as The 40-Year-Old Virgin, 27 Dresses, and The Holiday.

Two bar graphs were created for the Top 10 Oscar Movies Multigenres and Top 10 Non-Oscar Movies Multigenres. The single genres were color coded in order to get a better representation of which genre was appearing more frequently than others.

![Oscar Movies Top 10 Multigenres](https://user-images.githubusercontent.com/124934770/230953592-72e32798-b56d-4f3e-97fd-b534ab2e388e.png)
![Non-Oscar Movies Top 10 Multigenres](https://user-images.githubusercontent.com/124934770/230953610-e9c31c4a-e248-4975-b86b-c6be3f7e498c.png)

The Oscar movies appeared to have more Drama and Adventure movies while Non-Oscar movies had much more Comedy and Thriller movies. This could be explained by the Oscar movies on average being more serious and artistic style movies that are favored by movie critics while Non-Oscar movies can have more comedy and thrilling fun movies that an average audience would enjoy.

The top 10 multigenres were grouped together into a dataframe by the mean of 'profit', 'revenue', 'budget', 'Ratings_Combined', and 'popularity'.
The top 10 multigenres were grouped together into a dataframe by the sum of 'imdbVotes', 'oscar_wins', and 'oscar_nominations'.

Here are some example analysis tables that were generated:

The three most profitable multigenres on average: 
- ['Adventure', 'Family', 'Sci-Fi']	= $782,410,600
- ['Fantasy'] =	$737,701,800
- ['Adventure', 'Fantasy'] = $705,119,800

The three multigenres with the most Oscar wins: 
- ['Drama', 'Romance'] = 24 Oscar wins
- ['Action', 'Adventure', 'Drama'] = 23	Oscar wins
- ['Action', 'Adventure', 'Sci-Fi']	= 16 Oscar wins

Main Findings: 
- If the objective for a successful movie is to win the Oscars then picking a genre that is more serious such as Drama or Adventure could be beneficial. Comedy movies are less likely to be nominated for Oscar awards.
- Animation, Adventure, Comedy movies are the most frequent multigenre for Oscar awards and second most common multigenre for Non-Oscar movies. The budget for this multigenre is rather high (think of production companies such as "Pixar" "Walt Disney") but if the funds are there it may be worth it to try and win an Oscar. A good second option would be the Drama and Romance multigenre as it had the highest amount of Oscar wins with 24 Oscar wins.
- If the success goal is to make a highly rated movie, then the multigenre containing Drama and War may be a good option as they have the highest Review Ratings on average.

### 3. "Award Wins vs Oscar Wins vs Box Office Revenue" and "Keywords percentage in Oscar Winners vs Non-Oscar Winners"
Next we wanted to analyze the Award wins vs Oscar wins vs Box Office Revenue. Award wins were movie awards other than the Oscars such as the Sundance film festival awards for example. We created a scatter plot with Award Wins as the x value, Oscar wins as the y value, and Box Office Revenue as the value indicator for the size of the marker. The larger the marker, the higher the box office revenue.

![Award win vs oscar wins vs Box office revenue regression](https://user-images.githubusercontent.com/124934770/230975935-edeb2765-8b10-459d-a354-30d0b5e8741c.png)

We noticed that there was a large concentrated cluster around 0-50 award wins and 0-4 Oscar wins. This makes sense as winning hundreds of awards or more than 1 Oscar is a difficult feat. The regression performed shows that there is an r-squared value of 0.55 which demonstrates a moderately high correlation and 55% variance explained by the model. Movie that win more awards will usually win more Oscars as well indicated by the quality of the movie. 

We also created a function to compare different movie keyword percentages between Oscar Winners and Non-Oscar Winners.

![Keywords percentages in Oscar winners vs Non-Oscar winners](https://user-images.githubusercontent.com/124934770/230976013-f3f9b6ed-6614-46cd-bc72-c1ad631eb726.png)

The top 3 movies with common keywords were:

- Based on Novel
- Gay
- Saving the World

Non-Oscar Winners had a higher percenage of movies base on novels than Oscar winners, while Oscar winners had a slightly higher percentage for saving the world.

### 4. "Movie Film Ratings (G, PG, PG-13, R) Analysis"
The next analysis focuses on finding the differences between the four movie film ratings (G, PG, PG-13, and R).

After splitting the data into dataframes containing the respective film ratings, we found that:
- G-Rated movies won out in every category. It had the highest review ratings, budget, popularity, revenue, profit, and award wins/nominations.
- Contrastingly, R-Rated movies had the second highest review ratings and award wins/nominations. However had the lowest revenue and budget.
- PG and PG-13 movies were fairly similar in all metrics with PG-13 having sightly higher popularity and award wins/nomination values but lower review ratings.

Line graphs were created to demonstrate how Film Rating movies changed throughout the year 1961-2015.

PG-13 movies were not introduced until July 1, 1984, which is why it shows up around that timeframe on the line graphs.

![Film Ratings Average Profit per Year](https://user-images.githubusercontent.com/124934770/230953835-fa4ad9d6-84bc-4edc-96ba-34afab0f5c54.png)

PG movies were the most profitable until around 1982 when G movies started to increase. The introduction of PG-13 movies in 1984 may have influenced PG movie profits however it seems like PG profits were starting to decrease earlier in 1982. This could be due to the rise in popularity of G movies around that time. PG and PG-13 movies had some good year in the 1990's with high profits. R rated movies always had the least amount of average profit throughout the entire range. This could also be due to the fact that R rated movies have much lower budgets on average.

![Film Ratings Average Budget per Year](https://user-images.githubusercontent.com/124934770/230953867-c7b0437e-30d5-4d94-887b-4b0be6756277.png)

The average budget was similar for all ratings until around 1996 where G, PG, and PG-13 movie budgets increased. On average, the budget is highest for G-Rated movies and lowest for R-Rated movies.

![Film Ratings Average Popularity per Year](https://user-images.githubusercontent.com/124934770/230957388-c03b2987-4733-4ed7-b223-bc629d23f887.png)

Similar to the average profits, PG and R movies were the most popular until around 1982 when G movies started to increase. With the introduction of PG-13 movies in 1984, we see the decrease in PG and R movies. This could be due to PG and R movies becoming less saturated since films can now be split into a new in-between rating. G rated movies had a "golden popularity" era around the early 1990's. After that, all four film ratings started to even out and generate similar popularity ratings. More recently, PG-13 and R rated movies seemed to have had an increase in popularity starting somewhere around 2013.

### 5. "Top 10 Directors vs Revenue and Runtime Regression"
We ended with an anlaysis of the top 10 directors and their average box office revenues.

![Top 10 Directors vs Box Office Revenue](https://user-images.githubusercontent.com/124934770/230995835-73ea6349-d056-4cba-9fb8-723cf22e4e6e.png)

It is seen that James Cameron has the topmost average revenue generated with his 3 movies in the dataset, followed by Colin Trevorrow who has only one movie and is the second top Director. This is also one of the limitations of this data that the analysis is not fair as we are not comparing the equal amount of movies per director so when we are generating the average revenue, we are taking 3 movies from James whereas we are only taking one movie from Colin. This graph omitted the directors with higher number of movie count so we decided to generate a graph of smaller sample of directors who did 5 or more movies and see how much mean revenue they generated.

![Top 10 Directors 5 or more](https://user-images.githubusercontent.com/124934770/230995864-8005a570-bbb6-4694-bbee-dbc5c1983228.png)

Looking at the graph of Directors who did 5 or more movies Vs Revenue, it is seen that Peter Jackson did 8 movies and his average revenue is the greatest. When we compare this graph with the Top 10 Directors vs Revenue graph, we see that the revenue is higher in the first graph. We must however consider that the more movies a director makes, his/her experience increases. We also need to consider that this is the mean revenue. It will be affected as the movie count per director increases.


We also wanted to see if runtime (movie length in minutes) had any correlation with box office revenue. However we found that the r-squared value was very low, which tells us that the length of a movie doesn't have much of an affect on the box office revenue a movie earns. 

![Runtime Regression](https://user-images.githubusercontent.com/124934770/230956743-b17b5113-62a6-4e6f-8dfc-813274c54a45.png)

# Discussion
The Group-5 Agency perfromed analysis on the success metrics in order to answer:

- "What variables influence Box Office Revenue success, ROI, and profitability?"
- "What variables influence Award Wins/Nominations (Oscars)?"
- "What variables influence Movie Review Ratings (IMDb, Rotten Tomatoes, Metacritic)?"
- "What variables influence Popularity?"

Our analysis has given us new insight on what variables may affect the success of a movie given the desired success metric.

Some limitations that should be identified in the analysis is that perhaps more than 1178 rows of data may be beneficial in getting an even more accurate calculation. For example, when calculating film rating (G, PG, PG-13, and R) there were signficiantly less G rated movies than R.  This could be due to the fact the R movies are cheaper and arguably easier to make, having more data to verify if this is the case would be beneficial.

# Conclusion
After our analysis, we have discovered some significant patterns and variables that lead to a successful movie. 

### Success Metric - Box office revenue, ROI, and profitability
Based Budget vs Box Office Revenue analysis scatter plots we can conclude that if you want a guaranteed higher Box Office Revenue, you may have to have use an increased budget. The r-squared-value of budget vs box office revenue was 0.49 which tells us that having an increased movie budget has a relationship with higher revenue. 

We also can conclude if you have a low budget then the best option for financial box office success would be to make a horror genre movie as they require a small budget and have a high ROI.

Hiring a director not only influences the quality of the movie, but also the potential revenue you could earn. Getting one of the top 10 directors for revenue would definitley help in increasing box office revenue. Although this may not be cheap, if the revenue outweighs the cost it could be very beneficial to hire one of: "James Cameron, David Yates, or J.J. Abrams" to name a few.

If you are focused on profitability, than making a movie with the a multigenre combination of ['Adventure, 'Family', Fantasy] would be the most profitable. Historically, G-Rated movies have done the best for profitability, however if we look at the most recent Year's profitiability on our "Film Rating Average Profit per Year" line graph we can see that all four film ratings are around the same profitability metric. However we still would conclude and reccomend G-Rated movies as the most profitable based on recent historic trends.

### Success Metric - Oscar award wins and nominations
If the objective for a successful movie is to win the Oscars then picking a genre that is more serious such as Drama or Adventure could be beneficial. Comedy movies are less likely to be nominated for Oscar awards.

Interestingly, [Animation, Adventure, Comedy] movies are the most frequent multigenre for Oscar awards and the second most common multigenre for Non-Oscar movies. The budget for this multigenre is rather high (think of production companies such as "Pixar" "Walt Disney") but if the funds are there it may be worth it to try and win an Oscar.

A good second option would be the [Drama, Romance] multigenre as it had the highest amount of Oscar wins with 24 Oscar wins.

### Success Metric - Movie Review Ratings (IMDb, Rotten Tomatoes, Metacritic)
The scatter plot heatmap from the Budget vs Box Office with Review Raiting verifies that a movie has to be well made to get higher review ratings. This can be strengthened by having an increased budget. 

If the success goal is to make a highly rated movie, then the multigenre containing Drama and War may be a good option as they have the highest Review Ratings on average.

### Success Metric - Popularity
G-Rated movies are the most popular on average however our line graph demonstrates that PG-13 movies have been the most popular as of late.  If a company is looking to create a succesful move base on popularity we would reccomend creating a PG-13 movie with a multigenre that may include [Adventure, Action, Sci-Fi, and Drama].
