# IMDb Movies Dataset Analysis

## Overview
This project conducts an extensive Exploratory Data Analysis (EDA) on the IMDb movies dataset. The analysis covers trends in movie production, country and continent contributions, genre distributions, and biases in the dataset (e.g., country, genre, and decade biases). The primary tools used are Python, Pandas, Matplotlib, and Seaborn.

## Features
The analysis provides insights into:
1. **Movies per Year:** Trends in movie production over time.
2. **Movies per Country:** Movie production volume by country and continent.
3. **Movies per Genre:** Popular genres and keyword-based genre categorization.
4. **Null Values Analysis:** Handling and visualization of missing data.
5. **Bias Detection:** Examination of biases in scripts, subtitles, and summaries based on countries, decades, and genres.

## Dataset
The analysis utilizes several IMDb-related datasets:
1. `film_keywords.tsv`: Contains keywords associated with movies.
2. `films_base_details.tsv`: Includes base details such as release date, country of origin, and other metadata.
3. `processed_scripts.csv`: Processed movie scripts and subtitles.
4. `final_merged_result.csv`: Merged dataset of movie summaries and scripts.

## Key Findings
### 1. Movie Trends Over Time
- A significant increase in movie production was observed after the 1980s.
- The 2000s and 2010s saw the highest movie production volumes, driven by advances in digital production and streaming platforms.

### 2. Country and Continent Contributions
- **North America** dominates movie production, led by the United States.
- **Europe** and **Asia** are significant contributors, with strong outputs from the UK, France, India, Japan, and South Korea.
- **Africa**, **Oceania**, and **Latin America** contribute smaller but growing shares to global movie production.

### 3. Genre Analysis
- The most common genres include Romance, Drama, Comedy, and Action.
- A keyword simplification approach was used to group similar genres for better visualization and insights.

### 4. Bias Detection
- Country bias: Movies from the United States, France, and Brazil have a prominent presence in the dataset.
- Decade bias: Earlier decades (e.g., 1920s–1950s) have fewer scripts and subtitles available compared to recent decades.
- Genre bias: Romance and Drama are highly represented, reflecting global audience preferences.

### 5. Missing Data
- Scripts and subtitles are missing for 83% of movies.
- The dataset includes null values in fields like synopsis, which were handled during the analysis.

## Methodology
The analysis involved the following steps:
1. **Data Cleaning:** Handling null values, removing unnecessary columns, and converting dates.
2. **Grouping and Aggregation:** Grouping data by year, country, genre, and continent to identify trends.
3. **Visualization:** Creating bar plots, heatmaps, and stacked charts using Matplotlib and Seaborn.
4. **Bias Analysis:** Detecting country, genre, and decade biases using summary statistics and visualizations.
5. **Keyword Simplification:** Merging similar keywords into broader categories for genre analysis.

## Installation
To replicate the analysis, follow these steps:
1. Clone this repository:
   ```bash
   git clone https://github.com/your_username/imdb-movies-analysis.git
   ```
2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure the datasets (`.tsv` and `.csv` files) are present in the project directory.

## Usage
1. Open the `EDA.ipynb` notebook in Jupyter or Google Colab.
2. Run the notebook cells sequentially to reproduce the analysis and visualizations.

## Results
Key visualizations and findings are saved in the `results/` directory. These include:
- Bar charts for movies per year, country, and genre.
- Heatmaps for null value analysis.
- Stacked bar charts for decade and genre biases.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to enhance the analysis.

