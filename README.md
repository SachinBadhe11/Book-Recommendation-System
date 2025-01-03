# Book Recommendation System - A Collaborative Filtering Approach in Google Colab

This project implements a book recommendation system leveraging collaborative filtering techniques within the Google Colab environment. By analyzing book titles, authors, and user ratings, the system provides personalized book recommendations based on similarity to previously enjoyed books.

## Features

* **Collaborative Filtering:** Utilizes a collaborative filtering approach to identify similar books based on user preferences.
* **TF-IDF Vectorization:** Employs TF-IDF to transform text data (book titles and authors) into numerical representations, enabling similarity calculations.
* **Cosine Similarity:** Measures the similarity between books using cosine similarity on their TF-IDF vectors.
* **Top-N Recommendations:** Generates a list of the top N most similar books as recommendations.
* **Interactive Google Colab Notebook:** The entire system is implemented within a Google Colab notebook, providing an interactive and accessible environment for exploration and experimentation.

## Getting Started

1. **Access the Notebook:** Open the notebook directly in Google Colab by clicking the badge below:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](YOUR_COLAB_NOTEBOOK_LINK)
   **Note:** Replace `YOUR_COLAB_NOTEBOOK_LINK` with the actual link to your Colab notebook.

2. **Data Preparation:** Ensure the `books_data.csv` file, containing book information, is uploaded to your Colab environment. 

3. **Execution:** Execute the code cells sequentially within the notebook. The notebook is structured to guide you through the data loading, preprocessing, model training, and recommendation generation steps.

4. **Exploration:** Experiment with the recommendation system by modifying the input book title in the designated cell. Observe the generated recommendations and analyze the system's behavior.

## Methodology

The recommendation system follows these key steps:

1. **Data Ingestion and Preprocessing:**
   - Loads the `books_data.csv` file into a pandas DataFrame.
   - Converts the 'average_rating' column to a numeric data type for analysis.
   - Creates a 'book_content' column by combining book titles and authors, providing a textual representation for each book.

2. **Feature Engineering with TF-IDF:**
   - Applies TF-IDF vectorization using scikit-learn's `TfidfVectorizer` to transform the 'book_content' text into numerical vectors.
   - This process creates a matrix where each row represents a book, and each column represents a term (word) from the vocabulary.
   - The values within the matrix reflect the importance of each term in each book, enabling similarity calculations.

3. **Similarity Calculation using Cosine Similarity:**
   - Computes the cosine similarity between all pairs of books using scikit-learn's `linear_kernel` function, operating on the TF-IDF vectors.
   - Cosine similarity measures the angle between two vectors, indicating their similarity. Higher cosine similarity values suggest greater resemblance between books.

4. **Recommendation Generation:**
   - The `recommend_books` function takes a target book title as input.
   - Identifies the index of the target book within the DataFrame.
   - Retrieves the cosine similarity scores for all books compared to the target book.
   - Sorts the books in descending order based on their similarity scores.
   - Returns the top N most similar books, excluding the target book itself, as recommendations.

## Dependencies

* Python 3.x
* pandas
* numpy
* scikit-learn
* plotly

These libraries can be installed within the Colab environment using `!pip install library_name`.

## Contributing

Contributions are welcome and encouraged! Feel free to fork this project, make improvements, and submit a pull request. Your contributions will help enhance the functionality and usability of the book recommendation system.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
