# 🎬 Geospatial Analysis of Movie Scripts using NLP  

## 📌 Overview  
This project explores **geospatial references in movie scripts** using **Natural Language Processing (NLP)** techniques. By analyzing **script data**, we extract city, region, and country mentions, identify contextual references, and visualize results through **interactive maps** and **statistical insights**.  

The dataset consists of cleaned movie scripts with associated locations, allowing for **deep linguistic and geographical insights** in storytelling.  

---

## 🏗️ Features  

### 🔹 **Text Preprocessing**
- **Tokenization**: Splitting text into words using `nltk.word_tokenize`.  
- **Stopword Removal**: Eliminating common words that do not carry meaning (`nltk.stopwords`).  
- **Lowercasing & Cleaning**: Standardizing text by removing special characters, symbols, and punctuation.  
- **N-Gram Extraction**: Identifying **unigrams, bigrams, and trigrams** to analyze phrase patterns.  

### 🌍 **Geolocation Extraction**
- **City, Region, and Country Extraction** from movie scripts.  
- **Handling Multiple Geographic References** per script entry.  
- **Context Window Analysis**: Extracting surrounding words for location mentions to understand **contextual sentiment**.  

### 📊 **Visualization & Insights**
- **Word Frequency Analysis**: Finding the most commonly used words in geographic contexts.  
- **Sentiment Analysis**: Using **VADER** and **TextBlob** to determine emotions surrounding places.  
- **Interactive Maps**: Displaying geographic mentions in scripts using **Folium**.  

---

## 📂 Dataset  
This project uses a structured dataset containing:  

| Column | Description |
|--------|------------|
| `Movie Name` | Title of the movie |
| `City` | Cities mentioned in the script |
| `Region` | Regions associated with the city |
| `Country` | Countries associated with the city |
| `Processed_Script` | Cleaned version of the script |
| `Geo Indices` | Start and end positions of location mentions |
| `Geo Context` | Extracted context before and after location mentions |
| `Sentiment Score` | Sentiment polarity of location-related contexts |

**Example Data Sample:**  
| Movie Name | City | Country | Processed Script |
|------------|------|---------|------------------|
| Arsenic and Old Lace | New York | USA | "Arsenic and Old Lace, written by..." |
| Aventure malgache | London | UK | "The entire world has heard about the dramatic..." |

---

## 🛠️ Technologies Used  

### 📦 **Libraries & Tools**
- **Data Processing**: `pandas`, `numpy`, `collections`, `re`  
- **NLP & Text Analysis**: `nltk`, `textblob`, `transformers` (BERT-based models)  
- **Machine Learning**: `sklearn` (cosine similarity, KMeans clustering)  
- **Visualization**: `matplotlib`, `seaborn`, `folium` (interactive maps)  
- **Deep Learning**: `torch` (PyTorch-based models)  

---

## 🚀 Installation & Usage  

### 🔧 **1. Clone the Repository**
```bash
git clone https://github.com/yourusername/geospatial-nlp-movies.git
cd geospatial-nlp-movies
```

### 📦 **2. Install Dependencies**
```bash
pip install -r requirements.txt
```

### 🏃 **3. Run the Analysis**
```bash
python analyze_scripts.py
```

---

## 📊 Results & Insights  

### 📌 **1. Geolocation-Based Word Frequency Analysis**  
- Extracted frequently used words surrounding geographic references in movie scripts.  
- Example: The word “crime” frequently appears near "New York" in movie dialogues.  

### 🌍 **2. Contextual Extraction for Locations**  
- Example: In a given script, “Paris” might be mentioned in different contexts:
  - _“She dreamt of moving to **Paris**.”_
  - _“The heist took place in downtown **Paris**.”_
  - _“He always admired the art scene in **Paris**.”_
- **Context window extraction** helps in understanding sentiment and themes related to cities.  

### 🔥 **3. Sentiment Analysis Around Cities**
- Using **VADER** and **TextBlob**, the project extracts **positive, neutral, or negative** sentiment surrounding locations.  
- Example Results:
  - "Los Angeles" → Positive Sentiment (Hollywood dreams, opportunities)  
  - "Gotham" (fictional, but in some scripts) → Negative Sentiment (crime, darkness)  

### 🗺️ **4. Interactive Maps**
- Visualizing city mentions using `Folium`, showcasing where most movies are set.  
- **Heatmaps & Clusters**: Mapping high-frequency city references in films.  

---



