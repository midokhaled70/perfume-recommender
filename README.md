

# 🧴 Perfume Recommendation System

This project is a content-based recommendation system that suggests similar perfumes based on their ingredients, accords, target gender, and seasonal usage. It leverages natural language processing and machine learning techniques to find and recommend perfumes with similar profiles.

## 📂 Overview

This notebook-based project was developed in **Google Colab** and automatically saved as a Python script. It uses:

- **Pandas** for data handling  
- **NLTK** for text preprocessing  
- **Scikit-learn** for vectorization and nearest neighbors search  
- **Chardet** for encoding detection  

## 🔍 Features

- Cleans and preprocesses perfume data (notes, gender, seasons)
- Uses TF-IDF vectorization with n-grams for feature extraction
- Trains a Nearest Neighbors model using cosine similarity
- Recommends top N similar perfumes for a given perfume

## 📊 Dataset

- `perfume_data_combined.csv`  
The dataset should include the following columns:
- `name`
- `main accords `
- `top notes`
- `middle notes`
- `base notes`
- `for_gender`
- `seasons`

## 🧠 How It Works

1. **Preprocessing**:  
   - Tokenization, stopword removal, lemmatization, and punctuation cleanup are applied to both perfume notes and attributes.

2. **Feature Engineering**:  
   - Notes and attributes are combined with a custom weight factor to enhance the impact of gender and seasonal preferences.

3. **TF-IDF Vectorization**:  
   - Vectorizes combined perfume descriptions using bigrams and filters rare/common terms.

4. **Model Training**:  
   - Trains a K-Nearest Neighbors model (k=10) with cosine similarity to find similar perfumes.

5. **Recommendation**:  
   - For a given perfume, returns the top N similar perfumes along with their similarity percentage.

## 📦 Installation & Setup

Make sure you have the following Python packages installed:

```bash
pip install pandas scikit-learn nltk chardet
```

Also, ensure that you download required NLTK resources:

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('wordnet')
```

## 🚀 Usage

```python
query_perfume = "Boss Soul"
recommended_perfumes = recommend_similar_perfumes(query_perfume)

for perfume in recommended_perfumes:
    print("Perfume Name:", perfume[0])
    print("For Gender:", perfume[1])
    print("Seasons:", perfume[2])
    print("Similarity Percentage:", f"{perfume[3]:.2f}%")
```


## 📎 Source Notebook

This code was originally developed in [Google Colab](https://colab.research.google.com/drive/1BBBK4O96ry74ZkB9lB-Sty09oC5bEjko).


