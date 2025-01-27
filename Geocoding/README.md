# Geocoding and Location Details Extraction from Movie Data

## Overview
This project extracts geographic details from location names in a movie dataset using geocoding services. The process includes cleaning location names, fetching geographic details (e.g., neighborhood, city, region, country), and batch processing large datasets while handling errors and ensuring efficient use of geocoding APIs.

## Features
1. **Geocoding Initialization:** The geopy library's Nominatim service is used for geocoding.
2. **Location Cleaning:** Location names are preprocessed to remove invalid characters and unnecessary information.
3. **Geographic Details Extraction:** Extracts specific details like neighborhood, city, region, and country for each location.
4. **Batch Processing:** Processes rows of the dataset in batches with rate limiting to avoid overwhelming the API.
5. **Results Storage:** Saves processed geographic details to a CSV file for further analysis.

## Dataset
The input dataset includes the following:
- `13k_finalsummary.csv`: Contains location names extracted using spaCy and other preprocessing steps.

The output dataset:
- `test_location_details.csv`: Enriched dataset with geographic details and success indicators for geocoding.

## Key Steps
### 1. Geolocator Initialization
- A `Nominatim` geolocator is initialized with `user_agent="geopy_app"` to identify the application.

### 2. Location Cleaning
- Location names are cleaned using the `clean_location_name` function:
  - Strips whitespace.
  - Removes non-alphabetical characters (except commas and spaces).
  - Handles special cases like "##" and extra spaces.

### 3. Geographic Details Retrieval
- The `get_location_details` function fetches geographic data for each location using the geolocator.
- It extracts details like:
  - Neighborhood
  - City
  - Region
  - Country
- Handles invalid locations and API errors gracefully.

### 4. Batch Processing
- The `process_batch` function processes rows in batches, performing the following:
  - Cleans location names.
  - Fetches geographic details for each location.
  - Tracks geocoding success for all locations in the batch.
- A 1-second delay between API calls ensures compliance with rate limits.

### 5. Results Storage
- Geographic details are added as new columns in the dataset:
  - `neighbourhood`
  - `city`
  - `region`
  - `country`
  - `geocoding_success`
- The enriched dataset is saved to `test_location_details.csv`.

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your_username/geocoding-location-analysis.git
   ```
2. Install required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure the input dataset (`13k_finalsummary.csv`) is available in the project directory.

## Usage
1. Open the `geocoding.ipynb` notebook in Jupyter or Google Colab.
2. Load the dataset and run the cells sequentially to process the data.
3. View the enriched dataset in `test_location_details.csv`.

## Results
- Extracted geographic details for each location are stored in the output CSV file.
- Tracks geocoding success rates and provides cleaned location names.


## Contributing
Contributions are welcome! Please submit pull requests or open issues to suggest improvements or report bugs.


