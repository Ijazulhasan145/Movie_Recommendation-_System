# Movie_Recommendation-_System
## Assignment no 1:

Movie Recommendation System Report
Introduction
Recommender Systems play a vital role in modern-day technology, assisting users in discovering items based on their preferences. This report focuses on building a baseline movie recommendation system using the TMDB 5000 Movie Dataset. The system employs Demographic Filtering to recommend movies based on popularity and votes.
Datasets Overview
The following datasets were used in this analysis:

tmdb_5000_credits.csv:
- movie_id: Unique movie identifier.
- cast: List of actors (lead and supporting).
- crew: List of key crew members (director, writer, etc.).

tmdb_5000_movies.csv:
- id: Movie identifier (same as movie_id in the first dataset).
- genre: Movie genres (e.g., Action, Comedy).
- budget, popularity, revenue, runtime, vote_average: Various metrics.
- title: Movie title.
These datasets were merged on the id column to create a unified dataset for analysis.
Data Preparation
Description of Datasets:
The tmdb_5000_credits.csv dataset contains movie-specific details like movie_id, cast, and crew.
The tmdb_5000_movies.csv dataset contains movie details like id, budget, genre, popularity, revenue, runtime, and vote_average.
Steps Taken to Clean/Merge Data:
Renaming Columns for Consistency: The movie_id column in the tmdb_5000_credits.csv file was renamed to id for consistency with the tmdb_5000_movies.csv file.
Merging Datasets: The two datasets were merged using the id column, which is common in both, to create a consolidated dataset containing both movie details and credits.
Data Cleaning: Missing values were handled, irrelevant columns were dropped, and data types were adjusted (e.g., converting numeric columns like vote counts to proper data types).
-iltering Movies: Movies were filtered based on the number of votes, and only those with sufficient votes (greater than or equal to the 90th percentile) were retained.
Methodology:
The methodology followed to build the recommendation system includes:
Loading and Merging Data: The datasets were loaded into Pandas, and the movie_id column was renamed to id for proper merging.
Calculating Metrics: The mean of vote_average (C) was calculated, and the 90th percentile of vote_count (m) was determined to filter movies with sufficient votes.
Filtering Movies: Movies with vote_count greater than or equal to m were selected.
Weighted Rating Formula: A weighted rating for each movie was calculated using the formula:
  Weighted Rating = (v / (v + m) * R) + (m / (v + m) * C)
  Where:
  v = Number of votes
  R = Average rating
  C = Global average rating
  m = Minimum votes required
Sorting and Visualizing: Movies were sorted based on their calculated scores, and the top 10 movies were selected for recommendation. A bar chart of the most popular movies was also generated.
Results and Visualizations
Top 10 Movies Based on Scores:
The top 10 movies based on the weighted rating formula are selected, ranking movies that have both high ratings and a sufficient number of votes. The movies are displayed along with their respective scores.
Bar Chart of Popular Movies:
A bar chart is generated to show the top 6 most popular movies based on the popularity metric, highlighting the most trending movies.
Conclusion
Summary of Findings:
The recommendation system ranks movies based on their weighted ratings, which take both average ratings and vote counts into account. This ensures more reliable recommendations.
The top 10 movies are displayed, and their popularity is visualized using a bar chart.
Limitations and Future Improvements:
Limitations:
1. The current system uses Demographic Filtering, meaning the same recommendations are given to all users, regardless of individual preferences.
2.The system doesn't account for specific user interests or preferences, only focusing on popularity and average ratings.
Future Improvements:
1. Content-Based Filtering: This could be implemented to recommend movies based on user-specific preferences, such as genres or actors.
2.Collaborative Filtering: This approach would recommend movies based on the preferences of similar users.
3. Personalization: Future versions could incorporate user viewing history and preferences for personalized suggestions.
 Incorporating More Data: Additional features like keywords or movie descriptions could be included to refine recommendations.
