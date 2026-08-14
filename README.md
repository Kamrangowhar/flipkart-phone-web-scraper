# Flipkart Phone Web Scraper

Python web scraping and data cleaning project that extracts mobile phone product data (price, rating, reviews, specifications) from Flipkart search result pages and transforms it into a structured, analysis-ready CSV dataset.

## Overview

This project demonstrates an end-to-end web scraping and data extraction pipeline: sending HTTP requests with custom headers to bypass bot detection, parsing HTML with BeautifulSoup, looping through multiple paginated pages, and using regular expressions to extract structured attributes (Brand, Processor, RAM, ROM, Battery, Display Size, Camera) from unstructured product descriptions. The final output is a clean, tabular CSV dataset ready for analysis or machine learning.

## Key Features

- Automated web scraping of live e-commerce product listings using Python
- HTTP header spoofing (User-Agent) to bypass 403 Forbidden / anti-bot restrictions
- HTML parsing and DOM traversal using BeautifulSoup
- Multi-page pagination handling for large-scale data collection
- Regex-based text extraction and pattern matching for unstructured product specifications
- Data cleaning and type conversion (string to float, currency formatting removal)
- Feature engineering: extraction of Brand, Processor, RAM, ROM, Battery, Display Size, and Camera from raw text
- Structured data export to CSV using Pandas
- Missing data handling with NumPy (NaN management)

## Tech Stack / Skills Demonstrated

- **Languages:** Python
- **Libraries:** Requests, BeautifulSoup (bs4), Pandas, NumPy, Regex (re)
- **Techniques:** Web Scraping, HTML Parsing, Data Extraction, Data Cleaning, Data Wrangling, Regular Expressions, Pagination Handling, Exploratory Data Analysis (EDA) preparation
- **Core Concepts:** HTTP Requests, User-Agent Headers, DOM Traversal, CSS Class Selectors, String Manipulation, Data Type Conversion, CSV Export

## Project Structure

```
flipkart-phone-web-scraper/
│
├── Web_Scraping.ipynb        # Main Jupyter Notebook with full scraping and cleaning pipeline
├── Flipkart Phones.csv       # Final structured output dataset
└── README.md                 # Project documentation
```

## Dataset Output

The final cleaned dataset (`Flipkart Phones.csv`) includes the following columns:

| Column | Description |
|---|---|
| Brand | Extracted phone brand name |
| Product_name | Full product title |
| Processor | Extracted processor/chipset name |
| RAM | Extracted RAM size |
| ROM | Extracted internal storage size |
| Battery | Extracted battery capacity (mAh) |
| Display_Size | Extracted screen size (inches) |
| Camera | Extracted camera specification |
| No_of_ratings | Total number of product ratings |
| No_of_reviews | Total number of product reviews |
| Rating | Average product rating |
| Price | Product price (numeric, cleaned) |

## How It Works

1. **Request the page** — Send an HTTP GET request to the Flipkart search URL with a custom `User-Agent` header to avoid 403 errors.
2. **Parse HTML** — Use BeautifulSoup to parse the page content and locate product containers by CSS class.
3. **Extract raw fields** — Pull product name, price, rating, and review counts from each listing.
4. **Paginate** — Loop through multiple result pages to scale up data collection.
5. **Clean and convert** — Strip currency symbols/commas and convert price and rating fields to numeric types.
6. **Extract specifications with Regex** — Parse the raw specifications text to isolate Processor, RAM, ROM, Battery, Display Size, and Camera details.
7. **Structure and export** — Reorder columns and export the final cleaned dataset to CSV using Pandas.

## Installation

```bash
git clone https://github.com/<your-username>/flipkart-phone-web-scraper.git
cd flipkart-phone-web-scraper
pip install requests beautifulsoup4 pandas numpy
```

## Usage

Open and run `Web_Scraping.ipynb` in Jupyter Notebook or JupyterLab. The notebook will scrape the target Flipkart search pages and generate `Flipkart Phones.csv` in the project directory.

## Use Cases

- E-commerce price and product monitoring
- Market research and competitor analysis
- Dataset creation for machine learning / price prediction models
- Data analysis and visualization practice

## Disclaimer

This project is intended for educational and portfolio purposes only.

## Author

**Kamran Gowhar**
