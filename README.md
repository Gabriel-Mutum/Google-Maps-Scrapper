# Scrapper - Google Maps Data

Using the Playwright library to perform web scraping and data extraction from Google Maps. Obtaining information about businesses, such as their Name, Address, Website, Phone Number, Number of Reviews, Rating, Shopping Option, Pickup Option, Delivery Option, Business Type, Hours and Introduction.

## Prerequisites

- Python 3.8 or 3.9
- Playwright Google Chrome or Chromium browser

## Run

1. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Install Playwright browsers:
   ```bash
   playwright install
   ```

## Usage

Run the script with your desired search term and number of results:

```bash
python main.py -s "Italian Restaurants in New York City" -t 20
```

- `-s` or `--search`: Search query for Google Maps (default: "turkish stores in toronto Canada")
- `-t` or `--total`: Number of results to scrape (default: 1)
- `-o` or `--output`: Output CSV file path (default: result.csv)
- `--append`: Append results to the output file instead of overwriting (default: off)

## Example

Append new results to an existing CSV file:

```bash
python main.py -s "Italian Restaurants in New York City" -t 20 -o italian_restaurants_nyc.csv --append
```

The script will launch a browser, perform the search, and start scraping information. Progress will be displayed in the terminal, and results will be saved to the specified CSV file. If `--append` is used, new results will be added to the end of the file without removing previous data.

## Notes

- The script opens a visible browser window (not headless) for scraping.
- Google Maps DOM may change, which can break the script. If you encounter issues, update the XPaths in `main.py`.
- Avoid running too many scrapes in a short period to prevent being blocked by Google.
