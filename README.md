

# 🧴 Perfume Recommendation System

A **content-based recommendation engine** that suggests perfumes similar to a given fragrance based on their ingredients, accords, target gender, and seasonal suitability. This project harnesses **Natural Language Processing (NLP)** and **machine learning** techniques to deliver personalized perfume recommendations with high accuracy.

---

## 📂 Project Overview

Developed as a notebook project in **Google Colab** and exported as a Python script, this system leverages powerful Python libraries to process, analyze, and model perfume data, enabling rich similarity matching.

**Key technologies used:**

* **Pandas** — Efficient data manipulation and analysis
* **NLTK** — Robust text preprocessing including tokenization and lemmatization
* **Scikit-learn** — Feature extraction (TF-IDF) and K-Nearest Neighbors modeling
* **Chardet** — Automatic encoding detection for reliable data loading

---

## 🔍 Core Features

* Comprehensive text cleaning and preprocessing of perfume notes and attributes
* TF-IDF vectorization using n-grams to capture phrase-level features
* Weighted combination of scent notes, gender, and seasonal attributes for enhanced recommendation accuracy
* K-Nearest Neighbors model employing cosine similarity to identify closest perfume matches
* Returns a ranked list of top N perfumes similar to the input query, with similarity scores

---

## 📊 Dataset Details

The dataset (`perfume_data_combined.csv`) includes the following essential columns:

| Column Name    | Description                                 |
| -------------- | ------------------------------------------- |
| `name`         | Perfume name                                |
| `main accords` | Core fragrance accords                      |
| `top notes`    | Initial scent notes                         |
| `middle notes` | Heart of the perfume                        |
| `base notes`   | Lingering scent notes                       |
| `for_gender`   | Target gender (e.g., male, female, unisex)  |
| `seasons`      | Seasonal suitability (e.g., summer, winter) |

---

## 🧠 How It Works

1. **Data Preprocessing**
   Performs tokenization, stopword removal, lemmatization, and punctuation cleanup on all text fields.

2. **Feature Engineering**
   Combines fragrance notes with gender and season metadata, applying custom weights to reflect their importance in similarity calculations.

3. **TF-IDF Vectorization**
   Converts combined textual data into numeric vectors using bigrams, filtering out overly rare or common terms to focus on meaningful patterns.

4. **Model Training**
   Builds a K-Nearest Neighbors model (with k=10) that uses cosine similarity to measure the closeness between perfume profiles.

5. **Recommendation Generation**
   Retrieves and ranks the most similar perfumes to the query, providing names, gender, seasons, and similarity percentages.

---

## 📦 Installation & Setup

Ensure you have **Python 3.7+** installed, then install required packages:

```bash
pip install pandas scikit-learn nltk chardet
```

Download necessary NLTK resources:

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('wordnet')
```

---

## 🚀 Usage Example

```python
query_perfume = "Boss Soul"
recommended_perfumes = recommend_similar_perfumes(query_perfume)

for name, gender, seasons, similarity in recommended_perfumes:
    print(f"Perfume Name: {name}")
    print(f"For Gender: {gender}")
    print(f"Seasons: {seasons}")
    print(f"Similarity Percentage: {similarity:.2f}%\n")
```

---

## 📎 Source Notebook

Explore the full interactive notebook and code in **Google Colab**:
[Perfume Recommendation System Notebook](https://colab.research.google.com/drive/1BBBK4O96ry74ZkB9lB-Sty09oC5bEjko)
## Autor
-- Ahmed Khaled
---


