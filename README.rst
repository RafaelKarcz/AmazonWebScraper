Amazon Web Scraper
==================

Overview
--------

This project is a Python-based tool for scraping product information from Amazon's product pages to create a dataset from scratch. Furthermore, it automatically checks the price of a specified product and sends an email alert if the price falls below a predefined threshold. This functionality is especially useful for monitoring price drops, such as during Black Friday sales, allowing users to make timely purchases at lower prices.

Features
--------

- **Data Extraction**: Scrapes product details such as title, price, rating, and number of reviews using BeautifulSoup.
- **Dataset Creation**: Builds a dataset from scratch by logging scraped data over time into a CSV file.
- **Price Monitoring**: Continuously monitors and logs the price of the product.
- **Email Alerts**: Sends an email notification when the product price drops below a set threshold.

How It Works
------------

1. **Setting Up the Scraper**:
   The scraper uses `requests` to fetch the product page and `BeautifulSoup` to parse the HTML content. The product details are extracted from specific HTML elements identified through inspecting the webpage. Users need to adjust the `headers` and possibly the BeautifulSoup selectors based on their system and the product page structure.

2. **CSV Logging**:
   Extracted data is logged into a CSV file for historical tracking. The path to the CSV file can be customized in the script.

3. **Email Notification**:
   When the product's price falls below a specified threshold, an email alert is sent to a predefined email address. This feature uses `smtplib` to handle the SMTP protocol.

Installation
------------

1. Clone this repository:
   ::
   
       git clone https://github.com/yourusername/amazon-web-scraper.git

2. Install required Python packages:
   ::
   
       pip install beautifulsoup4 requests pandas

Usage
-----

To use this scraper:

1. Modify the `URL` in the script to point to the Amazon product you want to monitor.
2. Adjust the HTML elements in the `scrape_data` function to match the structure of the new product page.
3. Set the `csv_file_path` to your preferred location.
4. Configure the email settings in the `send_mail` function with your email credentials.
5. Adjust the `time.sleep()` duration in the main loop depending on how frequently you want to check the price.

Consider setting a shorter interval for high-traffic sales periods like Black Friday.

Contributing
------------

Contributions to enhance the functionality, improve the efficiency, or broaden the scope of this project are welcome. Please fork the repository and submit a pull request with your changes.

License
-------

Distributed under the MIT License. See `LICENSE <LICENSE>`_ file for more information.

Acknowledgments
---------------

- Amazon for providing rich product pages suitable for scraping.
- httpbin.org for testing HTTP headers.
- `AlexTheAnalyst <https://github.com/AlexTheAnalyst>`_ for making this project a reality.
