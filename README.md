# Netflix-1990s-Movie-Analysis
This project dives into the nostalgic world of 1990s movies available on Netflix, using exploratory data analysis to uncover insights about movie durations and genres from that iconic decade. This analysis focuses on filtering Netflix movie data, visualizing movie duration distributions, and identifying trends in action movies from the 1990s.
Dataset

The dataset used is ```netflix_data.csv```, which contains detailed information about Netflix shows, including:





**show_id**: Unique ID for each show



**type**: Type of show (e.g., Movie, TV Show)



**title**: Title of the show



**director**: Director of the show



**cast**: Cast of the show



**country**: Country of origin



**date_added**: Date the show was added to Netflix



**release_year**:Year the show was released



**duration**: Duration of the show in minutes



**description**: Description of the show



**genre**: Genre of the show

The analysis focuses on movies released between 1990 and 1999.

# Analysis Performed

This project includes the following key steps:





**Data Loading and Filtering**:





Loaded the Netflix dataset using pandas.



Filtered the dataset to include only movies released in the 1990s (1990–1999).



**Visualization**:





Created a histogram to visualize the distribution of movie durations in the 1990s, identifying that the most common duration is approximately 100 minutes.



**Action Movie Analysis**:





Filtered the 1990s movies to focus on the "Action" genre.



Counted the number of action movies with a duration of less than 90 minutes using a for loop and the .sum() method for comparison.

# Key Findings





The most frequent movie duration in the 1990s is around 100 minutes, as seen in the histogram peak.



A small number of action movies from the 1990s have durations under 90 minutes, indicating that action films from this era tend to be longer.

# Code

The analysis is performed using Python with the pandas and matplotlib libraries. Below is the core code used:

```import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
netflix_df = pd.read_csv("netflix_data.csv")

# Filter for movies
netflix_subset = netflix_df[netflix_df["type"] == "Movie"]

# Filter for 1990s movies
movies_1990s = netflix_subset[(netflix_subset["release_year"] >= 1990) & (netflix_subset["release_year"] < 2000)]

# Visualize movie durations
plt.hist(movies_1990s["duration"])
plt.title('Distribution of Movie Durations in the 1990s')
plt.xlabel('Duration (minutes)')
plt.ylabel('Number of Movies')
plt.show()

# Filter for action movies
action_movies_1990s = movies_1990s[movies_1990s["genre"] == "Action"]

# Count short action movies (<90 minutes)
short_movie_count = 0
for label, row in action_movies_1990s.iterrows():
    if row["duration"] < 90:
        short_movie_count += 1

print(f"Number of short action movies (<90 minutes): {short_movie_count}")
```


# How to Run





**Prerequisites**:





Python 3.x


```
Install required libraries: pip install pandas matplotlib
```


**Setup**:





Download the ```netflix_data.csv``` dataset (not included in this repository due to size; ensure you have access to it).



Place the dataset in the same directory as the script.



**Execution**:





Run the Python script to generate the histogram and output the count of short action movies.

# Future Enhancements





Analyze other genres (e.g., Comedy, Drama) for comparison.



Explore correlations between movie duration, release year, and country of origin.



Investigate director or cast trends in 1990s Netflix movies.

# Contributing

Feel free to fork this repository and submit pull requests for additional analyses or improvements. Please ensure any new code follows the existing structure and includes clear comments.

License

This project is licensed under the MIT License.
