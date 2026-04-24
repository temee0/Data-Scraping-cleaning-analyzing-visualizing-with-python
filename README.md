# Wikipedia Best-Selling Books Data Project
![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/books-world.jpg)

## Overview
This project focuses on scraping, cleaning, analyzing, and visualizing data from Wikipedia’s **List of best-selling books** page. The goal was to build a simple end-to-end data project that demonstrates how raw web data can be collected, transformed into a usable dataset, and explored through analysis and visualizations.

The project covers the full workflow from web scraping to data cleaning, exploratory data analysis, and visualization.

## Project Objectives
- Scrape book-related data from Wikipedia
- Combine multiple tables into a single dataset
- Clean and standardize inconsistent columns
- Handle missing values and messy text fields
- Analyze patterns in book sales, languages, authors, and publication years
- Visualize key insights from the dataset

## Data Source
The data was scraped from Wikipedia’s **List of best-selling books** page using `pandas.read_html()`.

Because the page contains multiple tables with slightly different structures, the tables were loaded, reviewed, and combined into one working dataset.

## Tools and Libraries Used
- **Python**
- **Pandas** for scraping, cleaning, and analysis
- **Matplotlib** for visualization
- **Requests** for fetching HTML where needed
- **Jupyter Notebook** for the workflow

## Project Workflow

### 1. Data Scraping
I scraped all relevant tables from the Wikipedia page using `pandas.read_html()`.  
A total of 14 tables were loaded from the page.

Since the tables had similar structures but also included some unique columns, I reviewed the columns and prepared them for merging into a single dataset.

### 2. Data Cleaning
The dataset required several cleaning steps before analysis:

- Merged similar columns with different names, such as:
  - `Approximate sales` and `Approx. sales`
  - `First published` and `Years of Publication`
  - `Book` and `Book series`
- Removed trailing and leading spaces from column names and text values
- Manually filled the two missing values in the author column
- Cleaned the **Approximate Sales** column by:
  - removing citation brackets
  - removing notes in parentheses
  - converting values such as `"15.11 million"` into numeric format
- Cleaned the **First Published** column by:
  - extracting the starting year from each entry
  - removing notes in parentheses
  - converting it to a numeric data type for easier analysis.

### 3. Exploratory Data Analysis
I explored the dataset to answer questions such as:

**Which books have the highest approximate sales?**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/top10bookstable.png)
**Which original languages appear most often?**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/bookbylanguagetable.png)
**Which authors appear most frequently?**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/top10authorstable.png)
**How are books distributed over time?**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/bookbyyeartable.png)

### 4. Data Visualization
I created visualizations to better understand the dataset, including:

**Top 10 best-selling books:**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/top10booksoutput.png)
**Number of books by original language:**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/bookcountlanguageoutput.png)
**Total sales by language:**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/salesbylanguageoutput.png)
**Publication trend by decade:**
  ![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/booksbydecadeoutput.png)

Since the publication years spanned a very wide range, grouping books by **decade** produced a clearer and more meaningful trend than plotting every year individually.

##Code Snippet
![](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/Code.png)
**_click [here](https://github.com/temee0/Data-Scraping-cleaning-analyzing-visualizing-with-python/blob/main/Wikipedia%20Best%20Seller%20Notebook.ipynb) to view the Jupiter notebook for this project_**

## Key Insights
Some notable insights from the analysis include:

- English was the most common original language in the dataset
- A large number of records had missing genre information, which led to dropping the column as it couldn't provide any useful analytical information.
- Book series contributed some of the highest sales values
- Publication activity was much more concentrated in modern decades than in earlier centuries
- Sales values were stored as text and needed significant cleaning before they could be analyzed numerically

## Challenges Encountered
During the project, I faced a few issues:

- `pandas.read_html()` required additional parser support such as `lxml` or `html5lib`
- Directly reading the Wikipedia URL sometimes caused HTTP-related issues
- The source page contained multiple tables with inconsistent columns
- Some columns contained missing values, citations, notes, and mixed formatting
- Certain visualizations were noisy until the data was grouped more effectively

These challenges were solved through dependency installation, HTML fetching with headers, column standardization, and additional data cleaning logic.

## Skills Demonstrated
This project demonstrates:
- Web scraping from HTML tables
- Data cleaning and transformation
- Handling missing values
- String manipulation and regex cleaning
- Data merging and concatenation
- Exploratory data analysis
- Data visualization
- End-to-end project documentation

## Conclusion
This project was a good exercise in building a complete data workflow from raw web data to cleaned insights. It also showed the importance of careful data cleaning when working with public web data, especially when tables are inconsistent and values are stored in text-heavy formats.

Overall, the project helped strengthen my skills in scraping, cleaning, analyzing, and presenting data in a structured and meaningful way.

## Author
**Oluwatimilehin Olugbade**
