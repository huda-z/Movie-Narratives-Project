# Script and Subtitle Scraper for Movies

A Python-based tool to scrape movie scripts and subtitles from multiple online sources, process large datasets in chunks, and filter results for analysis. 

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

## Expected Outcome

The tool processes movie titles, scrapes scripts and subtitles, and saves the results in a structured format. Below is an example of the expected output:

| **Column Name**          | **Description**                                                                                     | **Example**                 |
|---------------------------|-----------------------------------------------------------------------------------------------------|-----------------------------|
| `Movie Name`              | The title of the movie provided in the input CSV file.                                             | `The Godfather`             |
| `Script_IMSDB`            | The script retrieved from IMSDB. Returns "Unavailable" if not found.                               | `"I'm gonna make him an offer he can't refuse..."` |
| `Script_Springfield`      | The script retrieved from Springfield Springfield. Returns "Unavailable" if not found.             | `"Look how they massacred my boy."` |
| `Subtitle`                | The subtitle text downloaded from OpenSubtitles. Returns "Unavailable" if not found or processed.  | `"English subtitles file"` |
| `Availability`            | Categorized as "Available" or "Not Available" based on script and subtitle presence.               | `Available` or `Not Available` |

### Sample Output (Chunk File: `chunk_1.csv`)
```csv
Movie Name,Script_IMSDB,Script_Springfield,Subtitle,Availability
The Godfather,"<Script text>","Unavailable","<Subtitle text>",Available
Inception,"<Script text>","<Script text>","Unavailable",Available
Pulp Fiction,"Unavailable","<Script text>","<Subtitle text>",Available
