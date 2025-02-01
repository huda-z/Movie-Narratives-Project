# 🎬 Geospatial Analysis of IMDb Movie Summaries  

## 📌 Overview  
This project analyzes **geospatial references in IMDb movie summaries** using **Natural Language Processing (NLP)** techniques. It extracts **city and country mentions**, determines their **context**, and classifies the text thematically. The results offer insights into **how locations are represented** in movie storylines.  

---

## 🚀 Features  

### 📊 **Data Preprocessing & Cleaning**  
- Removing **stopwords, punctuation, and irrelevant words**  
- **Tokenization** of movie summaries  
- **Lowercasing** and **normalization** of text  
- Extraction of **n-grams (unigrams, bigrams, trigrams)**  

### 🌍 **Geolocation Extraction**  
- Identifying **city and country** mentions in IMDb movie summaries  
- **Handling multiple locations per script**  
- Extracting **contextual phrases** around city and country mentions  

### 🏗 **Geospatial Data Processing**  
- **Cleaning and merging datasets** for geolocation references  
- **Exploding multiple city-country pairs** into individual records  
- **Geocoding** locations for visualization  

### 🔎 **Context & Sentiment Analysis**  
- Extracting **context windows** (before & after a location mention)  
- **Sentiment analysis** of words surrounding city mentions  
- **Exact and fuzzy matching** for geolocation extraction  

### 📜 **Thematic Classification & Word Frequency**  
- **Grouping words into categories** (e.g., crime, tourism, war, love, religion)  
- **Using BERT embeddings** for thematic classification  
- **Extracting top thematic words per location**  

### 🗺 **Visualization & Insights**  
- **Interactive maps** of city mentions in movie summaries  
- **Top referenced cities per country**  
- **Word frequency analysis** for key locations  

---

## 📂 Dataset  

The dataset consists of IMDb movie summaries with the following key fields:  

| Column | Description |
|--------|------------|
| `film_id` | Unique IMDb movie identifier |
| `final_summary` | Processed IMDb movie summary |
| `city` | Extracted city names |
| `country` | Extracted country names |
| `geo_indices` | Start and end positions of location mentions |
| `geo_context_before` | Text appearing before the location |
| `geo_context_after` | Text appearing after the location |
| `sentiment_score` | Sentiment polarity of location references |

📌 **Example Data Sample**:  

| Film ID | City | Country | Final Summary |
|---------|------|---------|--------------|
| tt1140100 | New York | USA | "An aspiring musician moves to New York to chase his dreams..." |
| tt1142433 | London | UK | "A detective in London investigates a high-profile case..." |

---

## 🛠️ Technologies Used  

### 📦 **Libraries & Tools**  
- **Data Handling**: `pandas`, `numpy`, `re`, `collections`, `geopy`  
- **NLP Processing**: `nltk`, `textblob`, `transformers`, `fuzzywuzzy`  
- **Machine Learning**: `sklearn` (cosine similarity, KMeans clustering)  
- **Deep Learning**: `torch` (BERT embeddings)  
- **Visualization**: `matplotlib`, `seaborn`, `folium`, `plotly.express`  

---

## 🚀 Installation & Usage  

### 🔧 **1. Clone the Repository**  
```bash
git clone https://github.com/yourusername/geospatial-nlp-imdb.git
cd geospatial-nlp-imdb
```

### 📦 **2. Install Dependencies**  
```bash
pip install -r requirements.txt
```

### 🏃 **3. Run the Analysis**  
```bash
python analyze_summaries.py
```

---

## 📊 Results & Insights  

### 🏙 **1. Top Referenced Cities in IMDb Summaries**  
- **Most mentioned cities**: New York, London, Los Angeles, Paris, Mumbai  
- **Geographical trends** in movie settings  
- **Comparison of city mentions across different movie genres**  

### 🔍 **2. Contextual Analysis of Locations**  
- Example: _"Paris"_ appears in different contexts:
  - _“A young artist moves to **Paris** to find inspiration.”_
  - _“A major bank heist took place in **Paris**.”_
  - _“The protagonist’s romantic getaway is set in **Paris**.”_

### 😊 **3. Sentiment Analysis of City Mentions**  
- **Positive Sentiment**: Paris (romance, beauty), Los Angeles (dreams, opportunities)  
- **Negative Sentiment**: Gotham (crime, darkness), Detroit (crime, poverty)  

### 📜 **4. Thematic Classification using NLP & BERT**  
- **Crime**: New York, Chicago, Los Angeles  
- **Tourism**: Paris, Rome, London  
- **War**: Berlin, Baghdad, Hiroshima  
- **Romance**: Venice, Paris, Santorini  
- **History**: Cairo, Athens, Beijing  

### 🗺 **5. Interactive Maps of Movie Locations**  
- **Heatmaps**: Most referenced cities in movie summaries  
- **Cluster Maps**: Geographic distribution of movie settings  

---

## 📜 License  
This project is licensed under the **MIT License**.  

---

## 🤝 Contributing  

Contributions are welcome! To contribute:  

1. **Fork** the repository  
2. **Create a new branch**  
   ```bash
   git checkout -b feature-new-analysis
   ```
3. **Commit your changes**  
   ```bash
   git commit -m "Added new location analysis feature"
   ```
4. **Push to GitHub and create a Pull Request**  
