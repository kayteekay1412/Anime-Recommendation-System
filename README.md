# Anime Recommender System

This project focuses on building an Anime Recommender System using collaborative filtering techniques. The system utilizes user ratings and anime metadata to provide personalized recommendations. The project also includes various data visualizations to explore and understand the dataset better.

## Project Overview

### Datasets

- **Anime Dataset**: Contains information about various anime, including their IDs, titles, genres, ratings, and member counts.
- **User Ratings Dataset**: Contains user ratings for different anime, where a rating of -1 indicates that the anime was watched but not rated by the user.

### Data Preprocessing

1. **Remove Unrated Entries**: User ratings with a value of -1 are excluded.
2. **Handle Missing Values**:
    - Rows with missing anime ratings are dropped.
    - Remaining missing values in the anime dataset are filled with "Unknown".
3. **Reset Index**: The index of the anime dataframe is reset.

### Data Visualization

1. **Rating Distribution**: Histogram showing the distribution of anime ratings.
2. **Anime Types**: Count plot displaying the number of each type of anime.
3. **Missing Values**:
    - Heatmap visualizing missing values in the anime dataset.
    - Heatmap visualizing missing values in the user ratings dataset.
4. **Most Popular Animes**: Bar plot showing the top 10 most popular animes based on member counts.
5. **Rating vs Type**: Violin plot illustrating the relationship between anime ratings and types.

### Recommender System

1. **Merge Data**: User ratings are merged with anime names for easier reference.
2. **Filter Animes**: Only animes with at least a specified number of ratings (`r = 2000`) are kept for the recommender system.
3. **User-Item Matrix**: A matrix is created with users as rows and anime titles as columns, where each cell represents the rating given by the user to the anime.

### Collaborative Filtering

The recommender system uses collaborative filtering to find similar animes based on user ratings. The function `find_corr` calculates the correlation between the ratings of different animes to suggest similar animes.

## Usage

### Dependencies

- numpy
- pandas
- matplotlib
- seaborn

### Running the Project

1. **Clone the Repository**:
    ```sh
    git clone https://github.com/kayteekay1412/anime-recommendation-system.git
    cd anime-recommendation-system
    ```

2. **Run the Code**:
    - Ensure the `anime.csv` and `rating.csv` files are in the appropriate directory.
    - Execute the script to preprocess data, generate visualizations, and build the recommender system.

3. **Test the Recommender**:
    ```python
    anime1 = 'Naruto'
    recommendations = find_corr(df_recom, anime1)
    print(recommendations.head(10))
    ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
