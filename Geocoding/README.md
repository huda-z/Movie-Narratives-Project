# Location Analysis: Geocoding and Extraction from Movie Data

## Overview
This project combines two approaches to analyzing location data from movie-related datasets. The first approach focuses on **geocoding predefined location names** to extract structured geographic details (e.g., city, region, country). The second approach uses **Named Entity Recognition (NER)** to extract location-related entities directly from movie scripts or subtitles. Together, these methods offer a comprehensive framework for location data analysis.

## Features
### Geocoding Predefined Locations
- **Geocoding API Integration:** Uses the `Nominatim` geocoding service from the `geopy` library.
- **Location Cleaning:** Preprocesses and standardizes location names for accuracy.
- **Batch Processing:** Handles large datasets by processing location names in batches.
- **Result Storage:** Extracted geographic details (e.g., neighborhood, city, region, country) are stored in a structured dataset.

### Location Extraction from Scripts
- **Named Entity Recognition (NER):** Utilizes the `dbmdz/bert-large-cased-finetuned-conll03-english` model for extracting location-related entities (e.g., cities, landmarks, countries) from text.
- **Batch Processing:** Efficiently processes movie scripts in customizable batch sizes.
- **Script Analysis:** Extracts location entities from raw text data, even if they’re not predefined.
- **Result Consolidation:** Combines results from multiple batches into a single dataset.

## Dataset
The analysis uses multiple input and output datasets:
- **Input Datasets:**
  - `processed_scripts.csv`: Contains processed movie scripts or subtitles.
  - `location_extraction_results.csv`: Interim results for extracted locations.
  - `13k_finalsummary.csv`: Dataset with predefined location names for geocoding.
- **Output Datasets:**
  - `test_location_details.csv`: Geocoded location details (e.g., city, region, country).
  - `location_extracted.csv`: Consolidated results of extracted locations from scripts.

## Key Steps
### 1. Geocoding Predefined Locations
#### Process:
1. **Initialize Geolocator:**
   - Uses `Nominatim` with a custom `user_agent` to identify requests.
2. **Clean Location Names:**
   - Strips invalid characters and unnecessary whitespace using the `clean_location_name` function.
3. **Fetch Geographic Details:**
   - Extracts attributes like neighborhood, city, region, and country.
4. **Batch Processing:**
   - Processes location names in batches with rate-limiting to comply with API restrictions.
5. **Save Results:**
   - Stores enriched geographic details in a CSV file (`test_location_details.csv`).

### 2. Location Extraction from Scripts
#### Process:
1. **Initialize NER Pipeline:**
   - Loads the pre-trained `dbmdz/bert-large-cased-finetuned-conll03-english` model.
2. **Extract Location Entities:**
   - Applies the `extract_locations` function to identify `LOC` (Location) and `GPE` (Geopolitical Entity) tags in scripts.
3. **Batch Processing:**
   - Processes scripts in user-defined batch sizes for efficient memory usage.
4. **Consolidate Results:**
   - Combines results from multiple runs into a single dataset (`location_extracted.csv`).

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your_username/location-analysis.git
   ```
2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure input datasets are available in the project directory.

## Usage
### Geocoding Predefined Locations
1. Load the dataset with predefined location names:
   ```python
   df = pd.read_csv('/path/to/13k_finalsummary.csv')
   ```
2. Process location names in batches:
   ```python
   process_batch(df, batch_size=500, output_file="test_location_details.csv")
   ```
3. View the enriched dataset in `test_location_details.csv`.

### Location Extraction from Scripts
1. Load the processed script dataset:
   ```python
   data = pd.read_csv('/path/to/processed_scripts.csv')
   ```
2. Extract locations using the NER pipeline in batches:
   ```python
   process_in_batches(data, batch_size=500, output_file="location_extraction_results.csv")
   ```
3. Consolidate results into a single dataset:
   ```python
   df_combined = pd.concat([df1, df2], axis=0, ignore_index=True)
   df_combined.to_csv('location_extracted.csv', index=False)
   ```

## Results
- **Geocoded Locations:**
  - Enriched dataset with geographic details for predefined location names.
  - Output: `test_location_details.csv`
- **Extracted Locations from Scripts:**
  - Dataset with location entities extracted from raw text.
  - Output: `location_extracted.csv`

## Limitations
- **Geocoding:**
  - Dependent on the accuracy and specificity of location names.
  - API rate limits can slow down large-scale processing.
- **NER Extraction:**
  - Results depend on the quality and clarity of script text.
  - Ambiguities or incomplete sentences may affect accuracy.

## Contributing
Contributions are welcome! Please feel free to submit pull requests or open issues for improvements or bug fixes.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments
- Hugging Face's `transformers` library for NER.
- The `geopy` library for geocoding.
- The Python community for tools like Pandas and Numpy.

