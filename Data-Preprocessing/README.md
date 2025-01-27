# Text Tokenization and Dataset Merging with RoBERTa

This project provides a pipeline for cleaning, tokenizing, and merging datasets using Python and the RoBERTa tokenizer. It is designed to preprocess movie-related scripts and summaries for natural language processing tasks.

## Features
- **Text Cleaning**: Removes special characters, digits, and extra spaces for consistent text formatting.
- **Tokenization**: Uses the RoBERTa tokenizer to process text into input IDs, attention masks, and subword tokens.
- **Dataset Merging**: Combines two datasets (`scripts` and `final_summary`) into a unified DataFrame for further analysis.
- **Output Files**:
  - `processed_final_summary.csv`: Contains tokenized text, attention masks, and cleaned summaries.
  - `merged_dataset.csv`: The merged dataset of scripts and summaries.

---

## Requirements
The following libraries are required to run the code:
- `pandas` (for data manipulation)
- `transformers` (for RoBERTa tokenizer)
- `re` (for text cleaning and regular expressions)

Install the required Python packages using pip:

```bash
pip install pandas transformers
```

---

## Dataset Descriptions

### 1. **Processed Scripts (`processed_scripts.csv`)**
This dataset contains information about movie scripts, including:
- `Movie Name`: The name of the movie.
- `Script Content`: The text of the movie script.

### 2. **Final Summary (`final_summary.csv`)**
This dataset includes:
- `film_id`: Unique identifier for each movie.
- `final_summary`: Summaries of the movies.

---

## How It Works

1. **Load and Clean Datasets**:
   - Drops unnecessary columns (`Unnamed: 0`) if present.
   - Cleans the `final_summary` column to remove unwanted characters and spaces.

2. **Tokenization**:
   - Initializes the RoBERTa tokenizer.
   - Converts cleaned summaries into token IDs and attention masks with padding and truncation (512 tokens).
   - Creates a column with tokenized text split into subwords.

3. **Merge Datasets**:
   - Merges the `scripts` and `final_summary` datasets using an outer join on specified keys (`Movie Name` and `film_id`).

4. **Outputs**:
   - Saves processed summaries and the merged dataset to CSV files.

---

## File Structure

```
.
├── processed_scripts.csv         # Input dataset of movie scripts
├── final_summary.csv             # Input dataset of movie summaries
├── processed_final_summary.csv   # Tokenized and cleaned summaries (Output)
├── merged_dataset.csv            # Merged dataset (Output)
├── script.py                     # Main script containing the pipeline
├── README.md                     # Documentation
```

---

## Expected Outcome

### 1. **Processed Final Summary (`processed_final_summary.csv`)**

| **Column Name**        | **Description**                                                                                   |
|-------------------------|---------------------------------------------------------------------------------------------------|
| `film_id`              | Unique identifier for the movie.                                                                 |
| `cleaned_summary`      | The summary text after cleaning (removal of special characters, digits, and extra spaces).        |
| `input_ids`            | The tokenized representation of the cleaned summary as input IDs for the RoBERTa model.          |
| `attention_mask`       | The attention mask generated during tokenization, indicating the tokens to focus on.             |
| `processed_final_summary` | The summary split into subword tokens using the RoBERTa tokenizer.                             |

### Example:

| **film_id** | **cleaned_summary**             | **input_ids**          | **attention_mask** | **processed_final_summary**    |
|-------------|---------------------------------|-------------------------|--------------------|---------------------------------|
| 1           | A cleaned version of the text. | [0, 1943, 23, ...]     | [1, 1, 1, ...]     | ['A', 'cleaned', 'version', ...] |
| 2           | Another cleaned text here.     | [0, 389, 11, ...]      | [1, 1, 1, ...]     | ['Another', 'cleaned', ...]    |

---

### 2. **Merged Dataset (`merged_dataset.csv`)**

| **Column Name**           | **Description**                                                                             |
|----------------------------|---------------------------------------------------------------------------------------------|
| `Movie Name`              | Name of the movie as provided in the scripts dataset.                                       |
| `Script Content`          | The full content of the movie script.                                                       |
| `film_id`                 | Unique identifier for the movie (from the summaries dataset).                               |
| `cleaned_summary`         | Cleaned version of the movie summary.                                                       |
| `input_ids`               | Tokenized representation of the cleaned summary for RoBERTa.                                |
| `attention_mask`          | Attention mask to focus on relevant tokens during tokenization.                             |
| `processed_final_summary` | Subword tokenized version of the movie summary.                                             |

### Example:

| **Movie Name**    | **Script Content**      | **film_id** | **cleaned_summary**      | **input_ids**          | **attention_mask** | **processed_final_summary** |
|--------------------|-------------------------|-------------|--------------------------|-------------------------|--------------------|-----------------------------|
| The Godfather      | Script content here.   | 1           | A cleaned summary here.  | [0, 1943, 23, ...]     | [1, 1, 1, ...]     | ['A', 'cleaned', ...]       |
| Inception          | Another script here.   | 2           | Another summary here.    | [0, 389, 11, ...]      | [1, 1, 1, ...]     | ['Another', 'summary', ...] |

---

## Usage Instructions

1. **Prepare the Datasets**:
   - Ensure `processed_scripts.csv` and `final_summary.csv` are in the project directory.

2. **Run the Script**:
   Execute the script in your terminal:
   ```bash
   python script.py
   ```

3. **Outputs**:
   - `processed_final_summary.csv`: Contains cleaned and tokenized summaries.
   - `merged_dataset.csv`: Combined dataset with movie scripts and summaries.

4. **Check Missing Values**:
   After merging, the script prints any missing values in the merged dataset for further investigation.

---

## Customization

### 1. **Change the Maximum Token Length**
Modify the `max_length` parameter in the tokenization step:
```python
max_length=512  # Change to desired length
```

### 2. **Adjust Merge Keys**
Ensure the column names for merging are correct:
```python
merged_df = pd.merge(
    scripts,
    final_summary,
    left_on="Movie Name",  # Adjust key as needed
    right_on="film_id",    # Adjust key as needed
    how="outer"
)
```

---

## Troubleshooting

- **FileNotFoundError**:
  Ensure the input files (`processed_scripts.csv` and `final_summary.csv`) are in the same directory as the script.

- **Tokenization Issues**:
  If text exceeds the maximum token length, ensure truncation is enabled:
  ```python
  truncation=True
  ```

- **Missing Values**:
  Review the `missing_values` output to identify columns with null entries.

---

