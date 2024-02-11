# Amazon Web Scraper

## Overview
This Python script is designed to scrape data from an Amazon product page and store it in a CSV file. It also includes functionality to periodically check the price of the product and send an email notification if the price drops below a certain threshold.

## Key Learning Points
1. **Web Scraping with BeautifulSoup**: 
    - Utilizes BeautifulSoup library to parse HTML content and extract specific elements (product title and price) from an Amazon product page.
    - Demonstrates how to navigate the HTML structure of a webpage and locate desired information using BeautifulSoup's methods.

2. **HTTP Requests with Requests Library**:
    - Uses the Requests library to send HTTP GET requests to the Amazon product page.
    - Includes custom headers in the request to mimic those of a real browser, which helps prevent detection and blocking by Amazon.

3. **Data Manipulation with Pandas**:
    - Imports the Pandas library to read and manipulate data.
    - Stores scraped data (product title, price, and date) in a CSV file using Pandas DataFrame.

4. **Periodic Task Scheduling with Time Module**:
    - Implements a while loop to repeatedly check the product price at regular intervals (every 24 hours) using the `time.sleep()` function.
    - Demonstrates how to schedule and execute tasks at specific intervals within a Python script.

5. **Email Notifications with smtplib**:
    - Defines a function (`send_mail()`) to send email notifications using the smtplib library.
    - Configures the SMTP server and sends an email when the product price drops below a certain threshold.

## Requirements
- Python 3.x
- BeautifulSoup (`bs4`)
- Requests
- Pandas

## Usage
1. Update the `URL` variable in the script to the Amazon product page URL you want to scrape.
2. Run the script using `python amazon_web_scraper.py`.
3. The script will fetch the product title, price, and current date, and store this information in a CSV file (`AmazonWebScraperDataset.csv`).
4. It will then check the price of the product daily. If the price drops below $15, it will send an email notification.

## Customization
- You can modify the `URL` variable to scrape data from a different Amazon product page.
- Adjust the price threshold in the `check_price()` function to receive email notifications for different price levels.

## Notes
- Ensure that your email credentials are correctly configured in the `send_mail()` function to receive email notifications.
- Please be aware of Amazon's terms of service regarding web scraping. Use this script responsibly and avoid excessive scraping to prevent IP blocking.
