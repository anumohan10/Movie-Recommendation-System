# Movie Recommendation System

## 🌟 Aim of this Project

The **Movie Recommendation System** project is designed to provide **personalized movie suggestions** based on user preferences and viewing history. 

Utilizing **machine learning algorithms**, the system analyzes movie attributes and user reviews to predict and recommend films that align with individual tastes. This results in an enhanced user experience, simplifying content discovery while boosting engagement and satisfaction on streaming platforms.

The project leverages advanced data processing and **natural language processing** techniques to analyze user sentiment and preferences. This approach refines prediction accuracy, offering a highly tailored entertainment experience.

---

## 📊 About the Dataset

### 🔍 **Dataset Purpose**:
This dataset helps analyze **success factors** of movies, including production companies' strategies and predicting movie reception.

### ⚙️ **Data Transition**:
The dataset was transitioned from **IMDb** to **TMDb** after a DMCA takedown, which provided **more accurate data**, including complete cast/crew credits and revenue details.

---

### 📌 **Dataset Features**:
- Information on **movie revenues**, **cast/crew details**, and **audience ratings**.
- Includes **user-generated inconsistencies** in genres and ratings.
- Invites **community input** to refine data accuracy, especially regarding **budget assumptions**.

### 🔬 **Research Opportunities**:
- Facilitates film categorization by type and analysis of industry dynamics between **major** and **independent studios**.

[Explore the dataset here](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

---

## 🏗️ **Project Structure**

### 1. **Importing Required Packages**
```python
import numpy as np
import pandas as pd
```

### 2. **Loading the Dataset**
```python
movie_df = pd.read_csv('/path/to/tmdb_5000_movies.csv')
credits_df = pd.read_csv('/path/to/tmdb_5000_credits.csv')
```

### 3. **Data Cleaning**
- Removed unnecessary columns.
- Handled missing values (`NaN`) by dropping rows.
- Applied **stemming** and **removed spaces** for efficient text processing.

---

### 4. **Text Vectorization**

- Used `CountVectorizer` to convert **text data** into **numerical format**.
- Applied **Cosine Similarity** to measure the closeness between different movie vectors.

---

### 🎬 **Movie Recommendation Function**

The function below takes a **movie title** as input and provides **similar movie suggestions**.

```python
def recommendation(movie):
    index = new_data[new_data['title'] == movie].index[0]
    distances = sorted(list(enumerate(similarity[index])), reverse=True, key=lambda x: x[1])
    for i in distances[1:6]:
        print(new_data.iloc[i[0]].title)
```

#### Example Recommendation:
For the movie **"Batman"**, the system recommends:
- **Batman & Robin**
- **Batman Begins**
- **Batman Returns**
- **The R.M.**

---

## 🗂️ **Data Serialization**

The system uses **Pickle** to serialize the movie list and similarity matrix, allowing you to **reuse** the recommendation model without needing to recalculate it each time.

```python
import pickle

# Saving data with pickle
pickle.dump(new_data, open('movie_list.pkl', 'wb'))
pickle.dump(similarity, open('similarity.pkl', 'wb'))
```

---

## 🔑 **License**

This project is licensed under the **MIT License**.

```text
MIT License

Copyright (c) 2024 Anusree Mohanan

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

---

## 📚 **References**

- [TMDb Movie Metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
- [Pickle Documentation](https://docs.python.org/3/library/pickle.html)
- [Movie Recommender Systems on Kaggle](https://www.kaggle.com/code/rounakbanik/movie-recommender-systems)
- [Recommender System Basics](https://hackernoon.com/introduction-to-recommender-system-part-1-collaborative-filtering-singular-value-decomposition-44c9659c5e75)
- [Analytics Vidhya: Recommender Systems](https://www.analyticsvidhya.com/blog/2021/07/recommendation-system-understanding-the-basic-concepts/)

---

## 🎯 **Conclusion**

This project demonstrates how **data science** and **machine learning** techniques can be used to **enhance user experience** by offering personalized **movie recommendations** based on various factors like movie attributes, cast, and user preferences.
```
