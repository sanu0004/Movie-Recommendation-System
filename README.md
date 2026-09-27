# Movie-Recommendation-System
A content-based movie recommender system using cosine similarity on movie metadata, deployed with Streamlit and the TMDB API.
🎬 Recommends the top 5 similar movies based on genres, cast, crew, keywords, and plot overview using the TMDB 5000 Movies Dataset
🧹 Cleaned and merged raw movie & credits data with Pandas/NumPy, parsing nested JSON-like fields (genres, cast, crew) into usable tags
🔤 Converted movie tags into numerical vectors using Scikit-learn's CountVectorizer (bag-of-words, 5000 max features, stopwords removed)
📐 Built a similarity engine using cosine similarity to measure closeness between movies and rank recommendations
🌐 Deployed as an interactive Streamlit web app with live poster fetching via the TMDB API, and model persistence using pickle
