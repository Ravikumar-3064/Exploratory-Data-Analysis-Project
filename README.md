
                                                   EXPLORATORY DATA ANALYSIS

                                                                                 
Exploratory Data Analysis (EDA) is the initial step in data analysis where we explore datasets to understand their structure, patterns, and key characteristics.
It helps uncover relationships, anomalies, and trends before applying machine learning or statistical models.

✨ Key Objectives of EDA:

🔍 Understand the dataset – shape, size, data types, missing values.

📈 Summarize data distributions – mean, median, variance, outliers.

🧩 Identify patterns & correlations between features.

🚨 Detect anomalies or unusual observations.

🎨 Visualize data for deeper insights using plots and graphs.

🛠️ Tools & Techniques:

Descriptive Statistics → mean, median, mode, standard deviation.

Data Visualization → histograms, scatter plots, boxplots, heatmaps.

Data Cleaning → handling null values, duplicates, and outliers.

Feature Understanding → identifying categorical vs numerical variables.


🧩 PART 1 – Web Scraping & Data Collection
📚 Libraries Used

🔗 requests → Fetches the website’s HTML content.

🥣 BeautifulSoup → Parses the HTML to extract structured data.

📂 csv → Saves the extracted data into a CSV file.

🏗️ Script Structure

🛡️ Uses a try...except block for error handling.

📋 Data stored in a list of dictionaries (author, quote, tags).

🔄 while loop iterates through pages to fetch quotes.

🔍 Scraping Process

Starts from page 1, continues until all pages are processed.

Constructs the page URL dynamically.

Uses requests.get() → retrieves HTML.

BeautifulSoup extracts:

✍️ Author

💬 Quote text

🏷️ Tags

Each entry is stored as a dictionary → appended to the list.

📑 Handling Multiple Pages

🔄 Script continues as long as there’s a "next" button.

📌 Current setup → scrapes up to 10 pages.

✅ Ensures all available quotes are collected.

💾 Saving to CSV

Exports results to quotes.csv.

Defines columns: author, quote, tag_name.

Uses csv.DictWriter to store rows.

📊 Structured dataset ready for analysis.

🧩 PART 2 – SQL Queries on Quotes Data
🔎 Query 1 – Count Quotes per Author
SELECT author, COUNT(*) AS quote_count
FROM quotes
GROUP BY author
ORDER BY quote_count DESC;


👉 Shows authors ranked by number of quotes.

🏷️ Query 2 – Top 5 Most Common Tags
SELECT tag_name, COUNT(tag_name) AS tag_count
FROM quotes
GROUP BY tag_name
ORDER BY tag_count DESC
LIMIT 5;


👉 Retrieves top 5 tags with the highest frequency.

✍️ Query 3 – Authors with More Than 5 Quotes
SELECT author, COUNT(author) AS quote_count
FROM quotes
GROUP BY author
HAVING COUNT(author) > 5;


👉 Filters only authors with >5 quotes.

📏 Query 4 – Find the Longest Quote
SELECT author, quote_text
FROM quotes
ORDER BY LENGTH(quote_text) DESC
LIMIT 1;


👉 Returns the longest quote and its author.

🧩 PART 3 – Exploratory Data Analysis (EDA)
📂 Steps

🐼 import pandas as pd → Import Pandas.

📥 pd.read_csv("quotes.csv") → Load dataset.

📝 df.info() → Summary (rows, cols, datatypes, null values).

👀 df.head() → Preview first 5 rows.

🔢 df['author'].nunique() → Count of unique authors.

📊 df.describe(include='all') → Descriptive statistics for all columns.

✅ Insights

🔍 Identifies missing values & datatypes.

✨ Shows sample data rows.

👩‍💻 Finds number of distinct authors.

📈 Provides statistical overview of dataset.
