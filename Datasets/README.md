# Movie Summaries and Scripts - Dataset README
## Overview

This repository contains datasets related to movie summaries and web-scraped movie scripts. These datasets have been processed using **RoBERTa** tokenization for natural language processing tasks. The tokenized data can be used for various NLP tasks such as classification, clustering, or sequence analysis.

---

## Datasets

### 1. **IMDB Summary Dataset**

This dataset includes movie summaries that combine plot and synopsis details from IMDB. The raw summaries are processed using **RoBERTa** tokenization, breaking the text into subword tokens for better understanding of the text.

#### **Dataset Structure:**

- **film_id**: Unique IMDB identifier for each film.
- **final_summary**: The raw combined plot and synopsis for each movie.
- **processed_final_summary**: Tokenized version of the summary using **RoBERTa**, showing subword tokens (e.g., `'Ġthe'`, `'Ġcourse'`).

#### **Example Data (Before Processing):**

| film_id   | final_summary                                                                 |
|-----------|-------------------------------------------------------------------------------|
| tt0111161 | Over the course of several years, two convicts form a friendship, finding solace and eventual redemption through acts of common decency. |
| tt0468569 | When the menace known as the Joker wreaks havoc and chaos on the people of Gotham, Batman must accept one of the greatest psychological and physical tests of his ability to fight injustice. |
| tt1375666 | A thief who steals corporate secrets through the use of dream-sharing technology is given the inverse task of planting an idea into the mind of a CEO. |

#### **Example Data (After Processing with RoBERTa):**

| Index | film_id   | final_summary                                                                 | processed_final_summary                                                                                                                                                     |
|------------|-----------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0          | tt0111161 | Over the course of several years two convicts form a friendship...            | ['Over', 'Ġthe', 'Ġcourse', 'Ġof', 'Ġseveral', 'Ġyears', ',', 'Ġtwo', 'Ġconvicts', 'Ġform', 'Ġa', 'Ġfriendship', '...']                                                     |
| 1          | tt0468569 | When the menace known as the joker wreaks havoc...                            | ['When', 'Ġthe', 'Ġmenace', 'Ġknown', 'Ġas', 'Ġthe', 'Ġjoker', 'Ġwreaks', 'Ġhavoc', '...']                                                                                   |
| 2          | tt1375666 | A thief who steals corporate secrets through the use of dream-sharing...      | ['A', 'Ġthief', 'Ġwho', 'Ġsteals', 'Ġcorporate', 'Ġsecrets', 'Ġthrough', 'Ġthe', 'Ġuse', 'Ġof', 'Ġdream', '-', 'sharing', '...']                                             |

---

### 2. **Web-Scraped Movie Scripts Dataset**

This dataset contains scripts or subtitle text from movies that were gathered via web scraping. The raw text has been processed using **RoBERTa** tokenization to create subword tokens, making it easier for NLP tasks.

#### **Dataset Structure:**

- **Movie Name**: The title of the movie.
- **Script/Subtitle Text**: The raw script or subtitle text.
- **Processed Script**: Tokenized version of the script using **RoBERTa** tokenizer, showing subword tokens.

#### **Example Data (Before Processing):**

| Movie Name            | Script/Subtitle Text                                                                 |
|-----------------------|--------------------------------------------------------------------------------------|
| My Sassy Girl         | This is the story of the first and last time I fell in love.                         |
| Friday After Next     | 'Twas the night before Christmas, and all through the house, not a creature was stirring. |
| Zillion               | If you're stupid, then you can easily hide that. But if you're smart, it's harder.   |

#### **Example Data (After Processing with RoBERTa):**

| Movie Name            | Script/Subtitle Text                                                                 | Processed Script                                                                                                                                                           |
|-----------------------|--------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| My Sassy Girl         | This is the story of the first and last time I fell in love.                         | ['Ġthis', 'Ġis', 'Ġthe', 'Ġstory', 'Ġof', 'Ġthe', 'Ġfirst', 'Ġand', 'Ġlast', 'Ġtime', 'Ġi', 'Ġfell', 'Ġin', 'Ġlove', '.']                                               |
| Friday After Next     | 'Twas the night before Christmas, and all through the house, not a creature was stirring. | ['tw', 'as', 'Ġthe', 'Ġnight', 'Ġbefore', 'Ġchristmas', ',', 'Ġand', 'Ġall', 'Ġthrough', 'Ġthe', 'Ġhouse', ',', 'Ġnot', 'Ġa', 'Ġcreature', 'Ġwas', 'Ġstirring', '.']     |
| Zillion               | If you're stupid, then you can easily hide that. But if you're smart, it's harder.   | ['Ġif', 'Ġyou', "'", 're', 'Ġstupid', ',', 'Ġthen', 'Ġyou', 'Ġcan', 'Ġeasily', 'Ġhide', 'Ġthat', '.', 'Ġbut', 'Ġif', 'Ġyou', "'", 're', 'Ġsmart', ',', 'Ġit', "'", 's', 'Ġharder', '.'] |

---

## Location Extraction

Location extraction has been performed on both movie scripts and summaries to identify key locations mentioned within the text.

### **Location Extraction from Movie Scripts:**

| Index | Movie Name                     | Processed Script                                                                                 | Relevant Locations | City       | Region      | Country        | Processed Script Cleaned                                      |
|-------|--------------------------------|--------------------------------------------------------------------------------------------------|--------------------|------------|-------------|----------------|----------------------------------------------------------------|
| 0     | The Shawshank Redemption       | ['Ġbanker', 'Ġconvicted', 'Ġof', 'Ġu', 'x', 'icide', 'Ġforms', 'Ġfriendships', 'Ġin', 'Ġprison'] | ['new york']        | New York   | New York    | United States  | ['banker', 'convicted', 'icide', 'forms', 'friendships', 'prison'] |
| 1     | The Stanford Prison Experiment | ['Ġtwenty', 'four', 'Ġmale', 'Ġstudents', 'Ġselected', 'Ġfrom', 'Ġnew', 'Ġyork']                | ['new york']        | New York   | New York    | United States  | ['twenty', 'four', 'male', 'students', 'selected', 'new', 'york']  |
| 2     | 10 Rillington Place            | ['miss', 'Ġeady', 'Ġmr', 'Ġchristie', 'Ġin', 'Ġsheffield']                                       | ['sheffield']       | Sheffield  | England     | United Kingdom | ['miss', 'eady', 'mr', 'christie', 'sheffield']                  |

### **Location Extraction from Movie Summaries:**

| Index | Movie Name                     | Processed Summary                                                                                   | Relevant Locations | City       | Region      | Country        | Processed Summary Cleaned                                           |
|-------|--------------------------------|-----------------------------------------------------------------------------------------------------|--------------------|------------|-------------|----------------|--------------------------------------------------------------------|
| 0     | The Shawshank Redemption       | ['Ġbanker', 'convicted', 'of', 'a', 'crime', 'he', 'forms', 'a', 'friendship', 'in', 'a', 'prison']  | ['maine']          | Maine      | New England | United States  | ['banker', 'convicted', 'crime', 'forms', 'friendship', 'prison']    |
| 1     | The Dark Knight                | ['A', 'superhero', 'battles', 'villains', 'in', 'the', 'city', 'of', 'Gotham']                       | ['gotham']         | Gotham     | N/A         | N/A            | ['superhero', 'battles', 'villains', 'city', 'gotham']              |
| 2     | Inception                      | ['A', 'thief', 'who', 'steals', 'corporate', 'secrets', 'using', 'dream', 'technology']              | ['tokyo']          | Tokyo      | Kanto       | Japan          | ['thief', 'steals', 'corporate', 'secrets', 'dream', 'technology']    |

---

## Notes

- The **IMDB Summary Dataset** contains movie plot and synopsis information combined into a single "final_summary" field, which is processed for tokenization using **RoBERTa**.
- The **Web-Scraped Movie Scripts Dataset** provides subtitles or raw script data and processes them in the same manner.
- The **Location Extraction** tables show identified locations in both movie scripts and summaries for enhanced location analysis.

## **4. Word Frequency Analysis (Top 10 Words)**

Here are **3 selected movies** with their word frequencies from the **movie scripts** dataset:

### **Dataset 5A: Word Frequency Analysis (Top 10 Words)**

| Movie Name       | Word Frequencies                                                                 |
|------------------|-----------------------------------------------------------------------------------|
| South Africa     | {'new': 2, 'york': 2, 'jeff': 2, 'music': 3, 'truth': 2, 'francisco': 3}          |
| Greece           | {'addams': 33, 'wednesday': 70, 'family': 47, 'gomez': 26, 'morticia': 25}        |
| Brazil           | {'holiday': 1, 'love': 3, 'together': 4, 'family': 5, 'vacation': 2}              |

---

## **5. Sentiment Analysis (Scripts & Summaries)**

### **Dataset 6A: Sentiment Analysis for Scripts**

| Location | Top Positive Words                                        | Top Negative Words                     |
|----------|------------------------------------------------------------|----------------------------------------|
| Russia   | {'happy': 0.57, 'glory': 0.54, 'friend': 0.49}             | {'serious': -0.08, 'falling': -0.15}   |
| Brazil   | {'joy': 0.55, 'peace': 0.53, 'love': 0.50}                 | {'danger': -0.10, 'sad': -0.20}       |
| Canada   | {'success': 0.60, 'grace': 0.55, 'victory': 0.58}          | {'defeat': -0.12, 'loss': -0.10}      |

---

### **Dataset 6B: Sentiment Analysis for Summaries**

| Location | Top Positive Words                                        | Top Negative Words                     |
|----------|------------------------------------------------------------|----------------------------------------|
| Russia   | {'happy': 0.57, 'glory': 0.54, 'friend': 0.49}             | {'serious': -0.08, 'falling': -0.15}   |
| Brazil   | {'joy': 0.55, 'peace': 0.53, 'love': 0.50}                 | {'danger': -0.10, 'sad': -0.20}       |
| Canada   | {'success': 0.60, 'grace': 0.55, 'victory': 0.58}          | {'defeat': -0.12, 'loss': -0.10}      |

---

## **6. Theme Classification (Scripts & Summaries)**

### **Dataset 7A: Theme Classification for Scripts**

| Location         | Theme     | Word          | Count |
|------------------|-----------|---------------|-------|
| Brazil           | Love      | together      | 1     |
| Brazil           | War       | fight         | 1     |
| Brazil           | Fantasy   | spell         | 1     |

---

### **Dataset 7B: Theme Classification for Summaries**

| Location         | Theme     | Word          | Count |
|------------------|-----------|---------------|-------|
| Brazil           | Love      | together      | 1     |
| Brazil           | War       | fight         | 1     |
| Brazil           | Fantasy   | spell         | 1     |

---

## **7. Intensity (Frequency of Mentions)**

### **Dataset 7A: Intensity for Scripts**

| Location            | Frequency of Mentions | Top Associated Words                          |
|---------------------|-----------------------|-----------------------------------------------|
| United States       | 0                     |                                               |
| Brazil              | 1177                  | jake, kate, carson                           |
| Canada              | 857                   | sparky, victor, victors                       |

---

### **Dataset 7B: Intensity for Summaries**

| Location            | Frequency of Mentions | Top Associated Words                          |
|---------------------|-----------------------|-----------------------------------------------|
| United States       | 0                     |                                               |
| Brazil              | 1177                  | jake, kate, carson                           |
| Canada              | 857                   | sparky, victor, victors                       |

---

## **8. Bias Detection (Enhanced Sentiment Analysis)**

### **Dataset 8A: Bias Detection (Scripts)**

| Location            | Average Sentiment Score | Top Positive Words         | Top Negative Words         |
|---------------------|-------------------------|----------------------------|----------------------------|
| United States       | 0.00000                 | hope, peace, joy            | conflict, struggle          |
| Brazil              | 0.00000                 | love, freedom, excitement    | oppression, defeat          |
| Rzhev               | -0.38180                | courage, strength            | battles, war                |

---

### **Dataset 8B: Bias Detection (Summaries)**

| Location            | Average Sentiment Score | Top Positive Words         | Top Negative Words         |
|---------------------|-------------------------|----------------------------|----------------------------|
| United States       | 0.00000                 | hope, peace, joy            | conflict, struggle          |
| Brazil              | 0.00000                 | love, freedom, excitement    | oppression, defeat          |
| Rzhev               | -0.38180                | courage, strength            | battles, war                |

---

## **9. Film Metadata with Date Extraction**

### **Dataset 9: Film Metadata with Date Extraction**

| Index | film_id   | city       | release_year | Theme                | decade | theme  | date       |
|-------------|-----------|------------|--------------|----------------------|--------|--------|------------|
| 0           | tt1218038 | boston     | 2009         | Politics             | 2000   | Politics | 2009-01-01 |
| 1           | tt1226229 | new york   | 2010         | Family, Love         | 2010   | Family | 2010-01-01 |
| 2           | tt1231290 | new york   | 2008         | Family, Love         | 2000   | Family | 2008-01-01 |

---

### **Note**: Due to the large size of the datasets, a Google Drive link is provided for easy access: https://drive.google.com/drive/folders/1aJ55Figa9r5u7DQn6I89tyJUU5xcpW4d?usp=sharing
