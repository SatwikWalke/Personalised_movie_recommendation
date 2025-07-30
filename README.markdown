# Movie Recommendation System

## Project Overview
This project implements a movie recommendation system using both **content-based** and **collaborative filtering** techniques, along with a **hybrid approach** that combines the two. The system is built using Python and leverages the MovieLens 100k dataset to recommend movies based on user preferences and movie genres.

## Features
- **Content-Based Filtering**: Recommends movies based on genre similarity using TF-IDF and cosine similarity.
- **Collaborative Filtering**: Uses Singular Value Decomposition (SVD) to recommend movies based on user ratings.
- **Hybrid Recommendations**: Combines content-based and collaborative filtering to provide personalized recommendations.
- **Dataset**: Utilizes the MovieLens 100k dataset (`u.data` for ratings and `u.item` for movie metadata).

## Requirements
To run this project, you need the following Python libraries:
- `pandas`
- `numpy`
- `scikit-learn`
- `surprise`

You can install the required libraries using pip:
```bash
pip install pandas numpy scikit-learn scikit-surprise
```

## Dataset
The project uses the MovieLens 100k dataset, which includes:
- `u.data`: User ratings with columns `userId`, `movieId`, `rating`, and `timestamp`.
- `u.item`: Movie metadata with columns including `movieId`, `title`, and genre flags.

Ensure these files are placed in the `ml-100k` directory within the project folder. You can download the dataset from [GroupLens](https://grouplens.org/datasets/movielens/100k/).

## Usage
1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Set Up the Environment**:
   Create a virtual environment and install the required libraries:
   ```bash
   python -m venv movieenv
   source movieenv/bin/activate  # On Windows: movieenv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Run the Notebook**:
   Open the `analysis.ipynb` notebook in Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook analysis.ipynb
   ```

4. **Example Outputs**:
   - **Content-Based Recommendations**: Run the notebook to see recommendations for a movie (e.g., "Kick") based on genre similarity.
   - **Collaborative Recommendations**: Get recommendations for a specific user (e.g., user ID 1) based on their ratings.
   - **Hybrid Recommendations**: Combine both approaches to get personalized recommendations for a user based on a specific movie.

   Example output:
   ```
   Content-Based Recommendations for 'Kick':
   ['Eat Drink Man Woman (1994)', 'Ed Wood (1994)', ...]

   Collaborative Recommendations for User ID 1:
   ['Secrets & Lies (1996)', 'L.A. Confidential (1997)', ...]

   Hybrid Recommendations for User ID 1 based on 'Kick':
   ['Eat Drink Man Woman (1994)', 'Ed Wood (1994)', ...]
   ```

## File Structure
```
movie-recommendation-system/
├── ml-100k/
│   ├── u.data
│   ├── u.item
├── analysis.ipynb
├── README.md
├── requirements.txt
```

## How It Works
- **Data Loading**: The `load_data` function reads the MovieLens dataset and merges ratings with movie metadata.
- **Content-Based Model**: Uses TF-IDF vectorization on movie genres to compute a cosine similarity matrix for recommending similar movies.
- **Collaborative Filtering Model**: Employs the SVD algorithm from the `surprise` library to predict user ratings and recommend movies.
- **Hybrid Model**: Combines content-based recommendations with collaborative filtering predictions to provide more accurate, personalized recommendations.

## Future Improvements
- Add support for additional movie features (e.g., plot summaries, directors) in the content-based model.
- Implement cross-validation for the collaborative filtering model to improve accuracy.
- Add a user interface (e.g., a web app) for easier interaction with the recommendation system.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.