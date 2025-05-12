# Kemenperin Scraper

A Python-based web scraper for extracting company information from the Indonesian Ministry of Industry (Kemenperin) directory website. The scraper retrieves company names, addresses, phone number, and KBLI (Indonesian Standard Industrial Classification) codes and stores them in a CSV file.

## Features

- Scrapes company data from all provinces in Indonesia
- Extracts detailed company information including:
  - Company name
  - Complete address (street, kelurahan, kecamatan, city, province)
  - Phone number
  - KBLI (Indonesian Business Classification)
- Implements robust error handling and retry mechanisms
- Supports resumable scraping with progress tracking
- Respects website's rate limits with built-in delays
- Saves data in CSV format for easy analysis
- Maintains scraping progress in JSON format

## Requirements

- Python 3.X
- Required Python packages:
  - requests
  - pandas
  - beautifulsoup4
  - time
  - os
  - json

## Usage

Run the scraper cell.

The scraper will:
- Create an `output` directory if it doesn't exist
- Start scraping from the first province if no previous progress exists
- Resume from the last saved position if interrupted
- Save data to `output/kemenperin.csv`
- Save progress to `output/scraping_progress.json`

## Output Format

The scraper generates a CSV file with the following columns:
- No: Company number
- Perusahaan: Company name
- Alamat: Street address
- Kelurahan: Sub-district
- Kecamatan: District
- Kota: City
- Provinsi: Province
- Telepon: Phone number
- KBLI: Business classification code

## Progress Tracking

The scraper maintains its progress in `output/scraping_progress.json` with:
- Current province index
- Current URL being processed
- Last update timestamp

## Error Handling

The scraper includes:
- Automatic retry mechanism for failed requests
- Graceful handling of network errors
- Progress saving on interruption
- Detailed error logging

## License

This project is licensed under the MIT License

## Disclaimer

This scraper is intended for educational and research purposes only. Users are responsible for:
- Ensuring compliance with the website's terms of service
- Respecting rate limits and server load
- Using the data in accordance with applicable laws and regulations
- Verifying the accuracy of scraped data

Last Update: 12 May 2025