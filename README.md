# Movie_Recommendation-_System
## Assignment no 1:

### Movie Recommendation System Report
#### Introduction
Recommender Systems help users discover items based on preferences. This report focuses on building a movie recommendation system using the TMDB 5000 Movie Dataset. It uses Demographic Filtering to recommend movies based on popularity and votes.

Datasets Overview
tmdb_5000_credits.csv:

movie_id: Unique identifier.
cast: List of actors.
crew: Key crew members (director, writer, etc.).
tmdb_5000_movies.csv:

id: Movie identifier (same as movie_id).
genre: Movie genres (e.g., Action, Comedy).
budget, popularity, revenue, runtime, vote_average: Various movie metrics.
title: Movie title.
These datasets were merged on the id column for analysis.

Data Preparation
Description of Datasets:

The tmdb_5000_credits.csv contains movie-specific details like movie_id, cast, and crew.
The tmdb_5000_movies.csv contains id, genre, budget, popularity, and other metrics.
Data Cleaning and Merging:

Renaming Columns: movie_id was renamed to id for consistency.

Merging: Both datasets were merged using the id column.

Data Cleaning: Missing values were handled, irrelevant columns removed, and data types adjusted.

Filtering: Movies with vote counts greater than the 90th percentile were kept.

Methodology

Loading and Merging Data: The datasets were merged on the id column.

Calculating Metrics: The mean of vote_average (C) and the 90th percentile of vote_count (m) were calculated.

Filtering Movies: Movies with vote_count ≥ m were selected.

Weighted Rating Formula: The formula used is:

Weighted Rating
=
(
𝑣
𝑣
+
𝑚
×
𝑅
)
+
(
𝑚
𝑣
+
𝑚
×
𝐶
)
Weighted Rating=( 
v+m
v
​
 ×R)+( 
v+m
m
​
 ×C)
Where:
v = Number of votes
R = Average rating
C = Global average rating
m = Minimum votes required

Sorting and Visualizing: Movies were sorted by score, and the top 10 were displayed. A bar chart of popular movies was also created.
Results and Visualizations

Top 10 Movies: Movies with the highest weighted ratings are displayed, based on both ratings and vote count.
Bar Chart: A chart visualizing the top 6 most popular movies based on the popularity metric.

Conclusion

Summary of Findings:

The system ranks movies using a weighted rating formula, ensuring more reliable recommendations.
The top 10 movies are presented, and their popularity is visualized.
Limitations and Future Improvements:

Limitations:
The system uses Demographic Filtering, providing the same recommendations for all users.
It doesn’t consider specific user preferences, focusing only on popularity and ratings.

Future Improvements:

Content-Based Filtering: Recommendations based on user preferences (e.g., genre, actors).

Collaborative Filtering: Suggestions based on similar users’ preferences.

Personalization: Incorporating user viewing history for tailored recommendations.

Additional Data: Including features like keywords or descriptions to refine recommendations.
