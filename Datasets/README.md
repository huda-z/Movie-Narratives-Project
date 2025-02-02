

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

| Unnamed: 0 | film_id   | final_summary                                                                 | processed_final_summary                                                                                                                                                     |
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


