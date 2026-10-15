# Movie Recommender System

A content-based movie recommender system that suggests similar movies based on genres, cast, crew, keywords, and plot overview — built with Python and Scikit-learn, and deployed as an interactive web app using Streamlit.

## Overview

This project recommends the top 5 movies most similar to a movie selected by the user. It uses the **TMDB 5000 Movies Dataset**, processes movie metadata into a unified set of "tags," converts those tags into vectors, and computes similarity between movies using cosine similarity.

## Features

- 🎬 Recommends top 5 similar movies for any selected title
- 🧹 Cleans and merges movie + credits datasets using Pandas/NumPy, parsing nested JSON-like fields (genres, cast, crew, keywords)
- 🔤 Converts movie tags into numerical vectors using Scikit-learn's `CountVectorizer` (bag-of-words, top 5000 features, stopwords removed)
- 📐 Computes a similarity matrix using **cosine similarity** to rank and retrieve the most relevant recommendations
- 🌐 Deployed as an interactive **Streamlit** web app
- 🖼️ Fetches movie posters in real time via the **TMDB API**
- 💾 Model artifacts (movie list & similarity matrix) saved using `pickle` for fast loading

## Tech Stack

| Component          | Tool/Library |
|---------------------|--------------|
| Language             | Python |
| Data Processing       | Pandas, NumPy |
| ML / Vectorization    | Scikit-learn (CountVectorizer, cosine_similarity) |
| Web Framework          | Streamlit |
| External API           | TMDB API |
| Model Persistence      | Pickle |

## How It Works

1. **Data Loading & Merging** — Combines `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` on movie title
2. **Feature Engineering** — Extracts genres, keywords, top cast, director, and overview; combines them into a single "tags" string per movie
3. **Vectorization** — Converts tags into numerical vectors using `CountVectorizer`
4. **Similarity Computation** — Calculates cosine similarity between all movie vectors
5. **Recommendation** — For a selected movie, retrieves the 5 movies with the highest similarity scores
6. **Web App** — Streamlit UI lets the user pick a movie and view recommended titles with posters fetched from the TMDB API

## Setup & Usage

### 1. Clone the repo
```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

### 2. Install dependencies
```bash
pip install streamlit pandas numpy scikit-learn requests
```

### 3. Add the model files
Make sure `model/movie_list.pkl` and `model/similarity.pkl` are present (generated from the notebook, or download if provided separately).

### 4. Run the app
```bash
streamlit run App.py
```

### 5. Use it
Select a movie from the dropdown and click **"Show Recommendation"** to see 5 similar movies with posters.

## Note on Accuracy

This is a content-based, unsupervised recommender — there are no ground-truth labels, so traditional "accuracy" doesn't apply. Recommendation quality can instead be evaluated using metrics like Precision@K, Recall@K (with user interaction data), or by inspecting cosine similarity scores of the top-K results.

## License

This project is open source and available under the [MIT License](LICENSE).
