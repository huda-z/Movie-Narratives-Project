# Temporal and Geographical Analysis of Movies

## Overview
This project analyzes the temporal and geographical distribution of movies, examining how countries, cities, and associated themes evolve over time. The analysis identifies patterns in film production, explores nuanced versus stereotypical portrayals, and provides insights into the diversity of themes across locations.

## Features
1. **Temporal Analysis:**
   - Distribution of movies across years and decades.
   - Statistical tests for significant patterns in movie releases and themes.

2. **Geographical Analysis:**
   - Frequency of countries and cities in movies.
   - Classification of countries and cities by associated film industries (e.g., Hollywood, Bollywood).

3. **Theme Analysis:**
   - Classification of themes as "Stereotypical" or "Nuanced" based on predefined categories.
   - Evolution of themes over time and their distribution across regions.
   - Diversity of themes analyzed using Shannon entropy.

4. **Visualization:**
   - Stacked bar charts for top themes by decade and cities.
   - Heatmaps for theme frequency across top countries and decades.
   - Line charts for nuanced themes over time.

## Datasets
- **Input Files:**
  - `Cities-years-themes.csv`: Contains movie-related data by cities, years, and themes.
  - `countries-year-themes.csv`: Includes country-level data with themes and years.
- **Output Files:**
  - Processed datasets for frequency distributions, statistical significance, and theme analysis.

### Key Columns:
- `country`: Name of the country.
- `city`: Name of the city.
- `release_year`: Year of movie release.
- `theme`: Themes associated with the movie.
- `decade`: Grouped decade of the release year.

## Key Steps
### 1. Temporal Distribution of Movies
- **Country and City Trends:**
  - Plot the number of movie records per year and decade.
  - Highlight the most frequently represented countries and cities.
- **Statistical Analysis:**
  - Perform chi-square tests to determine the significance of temporal patterns.

### 2. Theme Frequency Over Time
- **Theme Trends:**
  - Analyze how certain themes (e.g., "History," "Family") appear more frequently in specific time periods (e.g., post-war depictions).
- **Theme Classification:**
  - Categorize themes as "Stereotypical" or "Nuanced."
  - Compare their frequencies over time using line plots.

### 3. Geographical Distribution of Themes
- **City and Country Analysis:**
  - Identify top countries and cities based on theme frequency.
  - Classify countries into film industries (e.g., Hollywood, Bollywood).
- **Shannon Entropy:**
  - Measure the diversity of themes across cities to assess nuanced portrayals.

### 4. Top 10 Themes and Locations
- **Heatmap:**
  - Visualize top themes across top 10 countries over decades.
- **Stacked Bar Chart:**
  - Show theme frequency across cities over decades.

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your_username/temporal-geographical-analysis.git
   ```
2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure the input datasets are placed in the project directory.

## Usage
1. **Run Temporal Analysis:**
   ```python
   # Import libraries
   import pandas as pd
   import matplotlib.pyplot as plt
   import seaborn as sns

   # Load datasets
   cities = pd.read_csv('/path/to/Cities-years-themes.csv')
   countries = pd.read_csv('/path/to/countries-year-themes.csv')

   # Analyze trends
   analyze_temporal_distribution(cities, countries)
   ```
2. **Run Geographical Analysis:**
   ```python
   # Analyze top countries and cities
   analyze_geographical_distribution(cities, countries)
   ```
3. **Run Theme Analysis:**
   ```python
   # Analyze nuanced vs. stereotypical themes
   analyze_themes(cities, countries)
   ```

## Results
- **Temporal Trends:**
  - Country and city-level distributions over time.
  - Evolution of themes across decades.
- **Geographical Insights:**
  - Prominence of certain countries (e.g., Hollywood vs. Bollywood).
  - Diversity and nuanced portrayals of themes.
- **Theme Analysis:**
  - Frequency of top themes (e.g., "Family," "Love").
  - Visualizations for nuanced vs. stereotypical portrayals.

## Limitations
- **Data Completeness:**
  - The analysis depends on the completeness and accuracy of input datasets.
- **Model Dependency:**
  - Results may vary based on the classification of themes and associated rules.

## Contributing
Contributions are welcome! Please feel free to submit pull requests or open issues for enhancements or bug fixes.

