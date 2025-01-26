# Script and Subtitle Scraper for Movies

A Python-based tool to scrape movie scripts and subtitles from multiple online sources, process large datasets in chunks, and filter results for analysis. This project is designed for researchers, movie enthusiasts, and anyone interested in analyzing movie scripts or subtitles.

---

## Features

### 1. **Scrape Movie Scripts**
Retrieve movie scripts from the following sources:
- [IMSDB](https://imsdb.com)
- [Springfield Springfield](https://www.springfieldspringfield.co.uk)
- [MovieScripts.com](https://www.moviescripts.com)

### 2. **Scrape Subtitles**
Download and process subtitles from:
- [OpenSubtitles](https://www.opensubtitles.org)
- [YTS Subtitles](https://yts-subs.com)

### 3. **Process Movie Titles in Chunks**
Efficiently handle large lists of movie titles (e.g., CSV files with thousands of entries) by processing them in manageable chunks.

### 4. **Save Results**
Store the retrieved scripts and subtitles in separate CSV files for easy access and analysis.

---

## How It Works

### 1. **Script Scraping**
- Scripts are fetched using web scraping techniques from the target sources.
- Results are saved with information on availability or any errors encountered.

### 2. **Subtitle Scraping**
- Subtitles are searched, downloaded, and processed from OpenSubtitles or YTS.
- Subtitles are extracted from `.zip` files (if applicable) and saved in `.srt` format.

### 3. **Chunk Processing**
- The input list of movie titles (e.g., `movies_names.csv`) is processed in chunks of 10,000 titles to avoid memory issues.
- Each chunk is saved into separate CSV files for better management.

### 4. **Filtering and Analysis**
- Results are categorized into "Available" or "Not Available" based on specific markers (e.g., "not available", "Failed to download").
- Filtered data is saved into new CSV files for further use.

---

## Requirements

- Python 3.7+
- Libraries:
  - `requests`
  - `beautifulsoup4`
  - `pandas`
  - `zipfile`
  - `io`

Install the required libraries using:

```bash
pip install requests beautifulsoup4 pandas

