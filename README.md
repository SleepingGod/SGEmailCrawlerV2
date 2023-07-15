Introduction:
Welcome to the user guide for SGEmailNameCrawlerV2, a powerful tool designed to extract email addresses and associated information from web pages. This guide will assist you in setting up and installing the program, provide an overview of its function and purpose, address ethical and legal considerations, and offer common troubleshooting tips.

This program was developed by Abhijith Subramanian AKA SleepingGod. It was originally designed for a friend who needed help with a web-scraping task. Most useful web-scrapers are locked behind expensive paywalls and there wasn’t much good & freely available code. It is an open-source project with a GPL License 3.0. You are welcome to modify and use this project for non-commercial use with appropriate credit. If you enjoy my work, you are welcome to buy me a coffee. Please note that the program is provided as-is, without any guarantee or warranty.

Table of Contents:

    Installation
        System Requirements
        Installation Steps
        Troubleshooting Installation Issues

    Program Overview
        Function Scope
        Purpose and Benefits

    Ethical and Legal Considerations
        Privacy and Data Protection
        Compliance with Applicable Laws

    Common Troubleshooting
        Unable to Extract Email Addresses
        Program Crashes or Freezes
        Network Connection Issues

 Full Overview of All Functions (For Developer Use)
Credits

    Installation:

System Requirements:
Before installing SGEmailNameCrawlerV2, ensure that your system meets the following requirements:

    Operating System: Windows, macOS, or Linux
    Memory: Minimum 4 GB RAM
    Storage: Minimum 100 MB of free disk space
    Internet Connection: Required for web scraping

Installation Steps:
Follow these steps to install SGEmailNameCrawlerV2:

Step 1: Download the Binaries:

    Download the binaries from a trusted source.
    Choose the appropriate version for your operating system.

Step 2: Extract the Files:

    Locate the downloaded ZIP or TAR file.
    Extract the contents to a desired location on your computer.

Step 3: Run the Program:

    Open the extracted folder.
    Run the program executable file for your operating system.
    The program should launch successfully.

Troubleshooting Installation Issues:
If you encounter any issues during installation, consider the following troubleshooting steps:

•	Ensure that your system meets the minimum requirements.
•	Verify that the downloaded binaries are not corrupted by re-downloading them.
•	Check if any antivirus or security software is blocking the program and temporarily disable it during installation.

Program Overview

Function Scope:
SGEmailNameCrawlerV2 is designed to extract email addresses and related information from web pages. It utilizes web scraping techniques to retrieve content from user-provided URLs. The program searches the content for email addresses and associated names, saving the scraped data for further analysis.

Purpose and Benefits:
The primary purpose of SGEmailNameCrawlerV2 is to automate the process of gathering email addresses and relevant information from web pages. It offers the following benefits:

•	Efficient extraction of email addresses from web pages
•	Identification of potential names associated with the email addresses
•	Handling and processing of large amounts of data quickly
•	Exporting scraped data for further analysis

Ethical and Legal Considerations:

Privacy and Data Protection:
When using SGEmailNameCrawlerV2, it is important to consider privacy and data protection. Extracting email addresses from web pages may involve collecting personal information without individuals' consent. To ensure ethical use:

•	Respect individuals' privacy and obtain proper consent before scraping their information.
•	Use the program strictly for legitimate purposes, such as collecting publicly available contact information for business or research purposes.
•	Avoid scraping sensitive or confidential data without explicit permission.

Compliance with Applicable Laws:
Users of SGEmailNameCrawlerV2 must comply with applicable laws and regulations, including but not limited to:

•	Data Protection Laws: Familiarize yourself with data protection laws in your jurisdiction, such as the General Data Protection Regulation (GDPR) in the European Union or the California Consumer Privacy Act (CCPA) in the United States.
•	Terms of Service and Website Policies: Respect the terms of service, privacy policies, and usage restrictions of websites you scrape. Some websites may explicitly prohibit scraping or require permission.
•	Intellectual Property Rights: Do not infringe on copyrights or intellectual property rights when scraping web pages. Respect the rights of website owners and content creators.

    Common Troubleshooting:

Unable to Extract Email Addresses:

•	Ensure that the URLs provided are accessible and contain the desired content.
•	Check if the program's web scraping functionality requires specific configurations or additional dependencies.
•	Review the program's documentation for any limitations or known issues related to email extraction.

Program Crashes or Freezes:

•	Verify that your system meets the minimum requirements and has sufficient resources.
•	Check for any conflicting software or conflicting dependencies that may cause instability.
•	Update SGEmailNameCrawlerV2 to the latest version, as updates often include bug fixes and stability improvements.
   

Network Connection Issues:
•	Ensure that you have a stable internet connection and can access the web.
•	Check if any firewall or network settings are blocking the program's access to the internet.
•	If using a proxy server, configure the program to use the appropriate proxy settings.
•	Consult your network administrator or internet service provider if you encounter persistent network connection problems.

Overview of Functions:
This part of the documentation is to aid open-source developers in understanding the code in a bid to make development easier.
Function: setup_logger
This function is responsible for setting up the logger instance for logging messages during the scraping process. It creates a logger named "scraping" and configures it with a console handler and a file handler. The console handler prints log messages to the console, while the file handler saves log messages to a file named "scraping.log". The log levels for both handlers are set to DEBUG, and the log format includes the timestamp, log level, and message.
The function takes no arguments and returns the configured logger instance.
Function: upgrade_pip
This function is used to upgrade the pip package manager to the latest version. It calls the subprocess.check_call() function with the command ['python', '-m', 'pip', 'install', '--upgrade', 'pip'] to execute the pip upgrade command. If the command execution fails, an error message is logged, and the script exits with a status code of 1.
The function takes a logger as an argument and does not return any value.
Function: check_missing_libraries
This function checks for missing or uninstalled libraries required by the script. It iterates over a list of required libraries and uses the pkg_resources.get_distribution() function to check if each library is installed. If a library is not found, it is added to the missing_libraries list.
If there are any missing libraries, an error message is logged, listing the missing libraries. The user is then prompted to install the missing libraries by entering 'y' or 'n'. If the user chooses to install the missing libraries, the function iterates over the missing_libraries list and uses subprocess.check_call() to execute the pip install command for each library. If an error occurs during the installation, an error message is logged. If the user chooses not to install the missing libraries, an error message is logged, and the script exits with a status code of 1.
If all required libraries are installed, an info message is logged indicating that all required libraries are installed.
The function takes a logger as an argument and does not return any value.
Function: check_missing_language_modules
This function checks for missing or uninstalled language modules required by the script. It iterates over a list of required language modules and uses the pkg_resources.get_distribution() function to check if each module is installed. If a module is not found, it is added to the missing_modules list.

If there are any missing modules, an error message is logged, listing the missing modules. The user is then prompted to download and install the missing language modules by entering 'y' or 'n'. If the user chooses to download and install the missing modules, the function uses subprocess.check_call() to execute the spacy download command for the missing modules. If an error occurs during the download and installation, an error message is logged, and the script exits with a status code of 1.
If all required language modules are installed, an info message is logged indicating that all required language modules are installed.
The function takes a logger as an argument and does not return any value.
Function: load_language_module

This function is responsible for loading a specific language module for SpaCy. It uses the spacy.load() function to load the specified module. If the module fails to load due to an OSError, an error message is logged, and the script exits with a status code of 1.
The function takes the name of the language module as an argument and returns the loaded language module (nlp).
Function: get_user_ip

This function retrieves the IP address of the user by creating a socket connection to a remote server (8.8.8.8) and retrieving the socket's local IP address. It uses the socket module to create a socket, connects it to the server, and retrieves the local IP address using getsockname(). If any exception occurs during the IP retrieval process, a ValueError is raised with an error message.
The function takes no arguments and returns the user's IP address as a string.
Function: get_user_socket_number

This function retrieves the socket number of the user by creating a socket connection, binding it to a random available port (0), and retrieving the bound socket's port number. It uses the socket module to create a socket, binds it to port 0, and retrieves the bound socket's port number using getsockname(). If any exception occurs during the socket number retrieval process, a ValueError is raised with an error message.
The function takes no arguments and returns the user's socket number as an integer.
Function: fetch_url
This asynchronous function is used to make an HTTP GET request to a specified URL using an aiohttp.ClientSession. It sends the request and awaits the response using the session.get() method. It then returns the response text.
The function takes two arguments: the session object representing the client session and the url to fetch. It returns the response text as a string.
Function: validate_proxy

This asynchronous function is used to validate a proxy by making an HTTP request to a specified URL using an aiohttp.ClientSession. It measures the response time for the request and checks if it is below a threshold (0.3 seconds). If the response time is below the threshold, the proxy is considered valid, and its URL is returned. If the response time exceeds the threshold or an exception occurs during the request, None is returned.
The function takes three arguments: the proxy URL to validate, a list of urls_to_check to make requests to, and the logger object for logging messages. It returns the valid proxy URL or None.
Function: is_valid_ip
This function checks if a given string is a valid IP address. It uses the socket.inet_aton() function to attempt to convert the string to a valid IP address. If the conversion succeeds, the IP address is considered valid and True is returned. Otherwise, False is returned.
The function takes a string ip as an argument and returns a boolean value indicating whether the IP address is valid.
Function: is_valid_socket_number

This function checks if a given string is a valid socket number. It attempts to convert the string to an integer and checks if the resulting number is between 0 and 65535 (inclusive). If the conversion and range check are successful, True is returned. Otherwise, False is returned.
The function takes a string port as an argument and returns a boolean value indicating whether the socket number is valid.
Function: read_csv_user_proxies

This function reads a CSV file named "userproxy.csv" located in the program's base folder. It reads the contents of the file and parses each row as a proxy tuple containing the IP address and port number. The proxies are stored in a list and returned.
If the CSV file is not found or any error occurs during the reading process, appropriate error messages are printed, and an empty list is returned.
The function takes no arguments and returns a list of proxy tuples.
Function: search_and_validate_proxies

This asynchronous function is used to search for and validate free working proxies with random user agents. It retrieves HTML content from multiple pages of a proxy website and extracts IP addresses and port numbers from the HTML using regular expressions. It then validates each proxy by making HTTP requests to specified URLs and measuring the response time. Proxies with response times below a threshold (0.3 seconds) are considered valid and added to a list. The list of valid proxies is returned.
The function takes two arguments: a list of urls_to_scrape to validate proxies against and the logger object for logging messages. It returns a list of valid proxy tuples.
Function: user_select_proxy_options
This asynchronous function is used to prompt the user to select proxy options for scraping. It presents a menu with four options and prompts the user to enter their choice. The options include using the user's own IP address with a random user agent, retrieving a list of free working proxies with random user agents, using a custom IP address and socket number with random user agents, and using a custom IP address and user agents from a CSV file.

Depending on the user's choice, the function performs the necessary actions, such as retrieving the user's IP address and socket number, searching for and validating proxies, or reading custom proxies from a CSV file. The selected proxy-user agent pairs are stored in a list and returned.

The function takes a logger object and a list of base_urls to scrape as arguments. It returns a list of proxy-user agent pairs.

Function: user_input_max_depth

This function prompts the user to enter the maximum depth of scraping, which determines how many levels deep the program will explore when scraping URLs. The user is prompted to enter a positive integer value between 1 and 10. If the user enters an invalid value, appropriate error messages are logged, and the user is prompted again. Once a valid value is entered, it is returned.
Function: user_input_max_threads

This function prompts the user to enter the maximum number of concurrent threads, which determines how many parallel requests can be made simultaneously. The user is prompted to enter a positive integer value. The function also provides information about the number of CPU cores and suggests a maximum number of threads based on that. If the user enters an invalid value, appropriate error messages are logged, and the user is prompted again. Once a valid value is entered, it is returned.
Function: user_input_name_threshold

This function prompts the user to enter the name threshold for potential name extraction. The name threshold is used to filter and extract potential names from the content using spaCy's NLP model. The user is prompted to enter a non-negative integer value. Information about the name threshold and suggested value range is provided. If the user enters an invalid value, appropriate error messages are logged, and the user is prompted again. Once a valid value is entered, it is returned.
Function: user_input_levenstein_threshold

This function prompts the user to enter the Levenshtein threshold for name matching. The Levenshtein threshold is used in the name extraction process to determine how closely potential names are matched to the email addresses found. The user is prompted to enter a non-negative integer value. Information about the Levenshtein threshold and suggested value range is provided. If the user enters an invalid value, appropriate error messages are logged, and the user is prompted again. Once a valid value is entered, it is returned.
Function: prompt_positive_integer

This function is a utility function used to prompt the user to enter a positive integer value. It takes a message as input and displays the message to the user. If the user enters an invalid value, appropriate error messages are printed, and the user is prompted again. Once a valid value is entered, it is returned.
Function: prompt_float_between_0_and_1

This function is a utility function used to prompt the user to enter a floating-point value between 0 and 1. It takes a message as input and displays the message to the user. If the user enters an invalid value, appropriate error messages are printed, and the user is prompted again. Once a valid value is entered, it is returned.
Function: prompt_levenshtein_threshold
This function is a utility function used to prompt the user to enter the Levenshtein threshold for name matching. It takes a logger object as input and provides information about the Levenshtein threshold. The user is prompted to enter a non-negative integer value. If the user enters an invalid value, appropriate error messages are logged, and the user is prompted again. Once a valid value is entered, it is returned.
Function: prompt_distance_threshold

This function is a utility function used to prompt the user to enter the distance threshold for similarity matching between names and email addresses. It takes a logger object as input and provides information about the distance threshold. The user is prompted to enter a value between 0 and 1. If the user enters an invalid value, appropriate error messages are logged, and the user is prompted again. Once a valid value is entered, it is returned.
Function: calculate_distance

This function calculates the Levenshtein distance between a name and an email address. It takes the name, email, and a threshold as input. If the distance is less than or equal to the threshold, the distance is returned. Otherwise, infinity is returned.
Function: is_valid_email

This function checks if an email address is valid. It takes an email address as input and uses a regular expression pattern to validate the email format. If the email address is valid, it returns True. Otherwise, it returns False.
Function: extract_emails_from_content

This asynchronous function extracts email addresses from content using regular expressions. It takes the content, an email pattern, and a list of obfuscated email patterns as input. It searches for email addresses using the patterns and returns a list of valid email addresses.
Function: extract_names

This asynchronous function extracts potential names from content using spaCy's NLP model. It takes the content, a list of emails, the name threshold, the Levenshtein threshold, a logger object, and the spaCy NLP model as input. It processes the content using the NLP model, extracts entities and noun chunks, and matches them with email addresses to find potential names. The results are returned as a dictionary mapping email addresses to potential names.
Function: truncate_content

This asynchronous function truncates content into smaller chunks of a maximum length. It takes the content and the maximum content length as input. It removes HTML tags, square brackets, parentheses, curly braces, URLs, special characters, punctuation marks, numeric characters, and common stopwords from the content. It then splits the content into smaller chunks based on the maximum length and returns a list of chunks.

Function: extract_emails_from_content

This asynchronous function extracts email addresses from content using regular expressions. It takes the content, an email pattern, and a list of obfuscated email patterns as input. It searches for email addresses using the patterns and returns a list of valid email addresses.

Function: extract_names

This asynchronous function extracts potential names from content using spaCy's NLP model. It takes the content, a list of emails, the name threshold, the Levenshtein threshold, a logger object, and the spaCy NLP model as input. It processes the content using the NLP model, extracts entities and noun chunks, and matches them with email addresses to find potential names. The results are returned as a dictionary mapping email addresses to potential names.

Function: extract_email_from_image

This asynchronous function extracts email addresses from an image. It takes an image data object as input, reads the image data, decodes it using OpenCV, applies thresholding and OCR using Tesseract, and matches the extracted text against an email pattern. If an email is found, it is returned; otherwise, an empty string is returned. Any exceptions that occur during the process are logged and raised.

Function: basic_auth_header

This asynchronous function generates a Basic authentication header string. It takes a username and password as input, combines them into credentials, encodes them using Base64, and returns the header string.

Function: calculate_distance

This function calculates the Levenshtein distance between a name and an email address. It takes the name, email, and a threshold as input. If the distance is less than or equal to the threshold, the distance is returned. Otherwise, infinity is returned.

Function: is_valid_email

This function checks if an email address is valid. It takes an email address as input and uses a regular expression pattern to validate the email format. If the email address is valid, it returns True. Otherwise, it returns False.

Function: scrape_url

This asynchronous function performs the scraping of a given URL. It takes a session object, URL, thresholds for Levenshtein distance and name similarity, an NLP object, a logger object, a Selenium WebDriver, and proxy options as input. It makes a request to the URL, extracts content, emails, and new URLs, and returns the scraped data and new URLs.

Function: scrape_coordinator

This asynchronous function coordinates the scraping process. It takes base URLs, thresholds, maximum threads, a logger object, an NLP object, maximum depth, proxy options, and progress bars as input. It manages the scraping process by processing URLs, updating progress, saving data, and handling exceptions.

Function: format_time

This function formats time in seconds into hours, minutes, and seconds. It takes the seconds as input and returns the formatted time string.

Function: master_save

This function saves the scraped data from the master dictionary to a CSV file. It takes the master dictionary, last saved index, save interval, and filename as input. It retrieves entries to be saved, appends them to the CSV file, and removes them from the dictionary.

Function: optional_data_cleanup

This function performs optional data cleanup on the scraped data. It takes the master dictionary as input, creates a workbook, creates sheets for duplicates, non-valid emails, and each base URL, and populates the sheets with cleaned data.

Function: main

This asynchronous function is the main entry point of the program. It sets up the logger, checks dependencies, prompts user input, creates an NLP object, sets up progress bars, handles keyboard interrupts, and initiates the scraping process.

CREDITS

SGEmailNameCrawlerV2 acknowledges and credits the following libraries, whose contributions are instrumental in the program's functionality:

    asyncio: A library for writing asynchronous code and managing concurrent operations.
    aiohttp: An asynchronous HTTP client library for making HTTP requests.
    base64: A library for encoding and decoding binary data in base64 format.
    csv: A library for reading and writing CSV files.
    logging: A library for flexible logging capabilities.
    multiprocessing: A library for utilizing multiple processes for parallel execution.
    random: A library for generating random numbers and making random selections.
    re: A library for working with regular expressions.
    signal: A library for handling signals and interrupting program execution.
    socket: A library for low-level networking operations.
    subprocess: A library for spawning new processes, connecting to their input/output/error pipes, and obtaining their return codes.
    sys: A library that provides access to system-specific parameters and functions.
    time: A library for time-related functions and operations.
    traceback: A library for printing or retrieving a stack traceback.
    urllib.parse: A library for parsing URLs and manipulating URL components.
    collections.defaultdict: A library that provides a defaultdict class, which is a subclass of the built-in dict class with a default value for missing keys.
    Levenshtein: A library for calculating Levenshtein distance and string similarity.
    cv2 (OpenCV): An open-source computer vision and image processing library.
    nltk: A library for natural language processing tasks such as tokenization, stemming, and tagging.
    numpy: A library for efficient numerical operations and array manipulations.
    openpyxl: A library for reading and writing Excel files.
    pkg_resources: A library for managing Python package resources.
    pytesseract: A Python wrapper for Google's Tesseract OCR engine.
    spacy: An open-source library for natural language processing.
We would also like to credit:
The Stanford NER Project
Open AI ChatGPT 3.5 for code analysis

We extend our gratitude to the developers and contributors of these libraries for their invaluable efforts in creating and maintaining these powerful tools. Their dedication and expertise have significantly enhanced the capabilities of SGEmailNameCrawlerV2, enabling efficient email scraping and data processing.
