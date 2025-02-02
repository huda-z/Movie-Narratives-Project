# Movie-Narratives-Project

## Welcome!

Thank you for exploring my project! I hope you find the materials insightful as you dive into the work. Below is an overview of the key aspects of the project to help you understand its structure and guide you through the different sections.

---

## **Project Phases**
The project is divided into the following key phases:

1. **Phase 1: Web Scraping for Data Collection**  
   Data is scraped from various sources for movie information.

2. **Phase 2: Data Preprocessing**  
   Clean and prepare the scraped data for analysis.

3. **Phase 3: Geocoding and Spatial Reference Extraction**  
   Extract geographic locations mentioned in the data and map them.

4. **Phase 4: Natural Language Processing (NLP)**  
   Process movie scripts and summaries for sentiment analysis and theme detection.

5. **Phase 5: Temporal Analysis**  
   Analyzing time-related patterns across movies.

---

## **Code Organization**
The code is structured into folders corresponding to each phase. Each folder contains scripts and resources specific to that phase. This organization ensures the workflow remains clear and well-organized.

---

## **Instructions for the NLP Phase**
In this phase, several datasets are essential for analysis:

- **Summary Country Analysis**:  
  Use the dataset `final_summary_cleaned_geocoded.csv` located in the `summary` folder.

- **Scripts Country/City Analysis**:  
  Use the dataset `12853_scripts_cleaned.csv` located in the `scripts` folder.

- **Summary City Analysis**:  
  Use the dataset `city_summary.csv` located in the `summary` folder.

---

## **Visualizations**
The project provides interactive visualizations for better understanding of the results:

### **Country-Level Visualizations**  
Two HTML files are available for geographic visualizations at the country level, focusing on the datasets.

### **City-Level Visualizations**  
Three HTML files for city-level visualizations are available:  
- One for the summary dataset.  
- Two for the scripts dataset, focusing on the top three cities mentioned.

> **Note**: The visualizations are tailored to the dataset type (summaries or scripts), so make sure to check accordingly.

---

## **Datasets**
Due to the size of the datasets, they are available via a Google Drive link for easy access:

- [Google Drive Link to Datasets](https://drive.google.com/drive/folders/1aJ55Figa9r5u7DQn6I89tyJUU5xcpW4d?usp=sharing)

### **1. IMDB Summary Dataset**  
Contains movie summaries with detailed plot and synopsis data. The summaries are tokenized using **RoBERTa** for NLP tasks.  

#### Example Data:

| film_id   | final_summary                                                                 |
|-----------|-------------------------------------------------------------------------------|
| tt0111161 | Over the course of several years, two convicts form a friendship, finding solace and eventual redemption through acts of common decency. |
| tt0468569 | When the menace known as the Joker wreaks havoc and chaos on the people of Gotham, Batman must accept one of the greatest psychological and physical tests of his ability to fight injustice. |

### **2. Web-Scraped Movie Scripts Dataset**  
Contains scripts or subtitle text from movies scraped from the web. These scripts are also tokenized using **RoBERTa** for easy NLP processing.

#### Example Data:

| Movie Name            | Script/Subtitle Text                                                                 |
|-----------------------|--------------------------------------------------------------------------------------|
| My Sassy Girl         | This is the story of the first and last time I fell in love.                         |
| Friday After Next     | 'Twas the night before Christmas, and all through the house, not a creature was stirring. |

---

## **Location Extraction**
Location extraction was performed on both movie scripts and summaries to identify key locations within the text. Here's a sample of the location extraction results:

### Example (Scripts Dataset):
| Movie Name                     | Relevant Locations | City       | Region      | Country        |
|---------------------------------|--------------------|------------|-------------|----------------|
| The Shawshank Redemption       | ['new york']        | New York   | New York    | United States  |
| The Stanford Prison Experiment | ['new york']        | New York   | New York    | United States  |

---

## **Additional Analysis**  
The project also includes additional analyses, such as:

- **Word Frequency Analysis**  
- **Sentiment Analysis (Scripts & Summaries)**  
- **Theme Classification**  
- **Intensity (Frequency of Mentions)**  
- **Bias Detection**  
- **Film Metadata with Date Extraction**

These analyses provide insights into different aspects of the movie data.

---

## **How to Contribute**  
Feel free to fork the project and contribute! You can improve the code, add new analyses, or suggest enhancements. Pull requests are always welcome!

