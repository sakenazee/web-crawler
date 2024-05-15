

# Web Crawler App

This is a simple Django-based web crawler application that fetches content from a given URL, extracts the text from `<p>` tags, and counts the frequency of the words. The results are cached in the database to avoid repeated crawling of the same URL.

## Features

- Crawl a webpage and extract text content from `<p>` tags.
- Perform word frequency analysis by counting the occurrence of each word.
- Store crawled data (URL and word frequency) in a database to avoid redundant requests.
- Retrieve word count from the database if the URL has already been processed.
- A simple user interface to input the URL and view the results.

## Technologies Used

- **Django**: Web framework
- **BeautifulSoup**: HTML parsing library
- **Requests**: Library for making HTTP requests
- **SQLite**: Default Django database used for storing URL data and word frequency

## How It Works

1. **Input a URL**: The user provides a URL to be crawled in the web form.
2. **Check for Cached Data**: 
   - The application checks if the URL has already been crawled and exists in the database.
   - If the URL exists, it retrieves the word count from the database and displays it.
3. **Crawl the Webpage**: 
   - If the URL is not found in the database, the app sends a request to the URL and extracts the content from all `<p>` tags.
   - The extracted content is then processed to count the frequency of words, ignoring case and punctuation.
4. **Store Results**: 
   - The URL and word frequency data are saved to the database for future reference.
5. **Display Results**: 
   - The word count for the URL is displayed on the result page.

## How to Run the Application

### Prerequisites

- Python 3.10
- Django
- Required Python libraries (`requests`, `beautifulsoup4`) etc

### Installation Steps

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd web-crawler-app
   ```

2. **Set up a virtual environment** (optional but recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations** to set up the database:
   ```bash
   python manage.py migrate
   ```

5. **Run the development server**:
   ```bash
   python manage.py runserver
   ```

6. **Open the app** in your browser by navigating to `http://127.0.0.1:8000`.

### Usage

1. On the homepage, enter the URL of the website you want to crawl.
2. The app will either display the word count from the database (if the URL has already been crawled) or fetch the webpage, process the content, and display the results.
3. The results page will show the word frequency for the crawled page.

### Example

- Input: `https://example.com`
- Output: A table or list of the most common words and their counts.

### File Structure

- **views.py**: Contains the main logic for handling the URL input, crawling, and processing.
- **models.py**: Defines the `Mail` model for storing the URL and word frequency data.
- **forms.py**: Defines the input form for users to submit URLs.
- **templates**: HTML files for rendering the homepage and result page.

## Future Enhancements

- Add more detailed error handling for invalid URLs or request failures.
- Improve UI for better user experience.
- Add support for crawling and analyzing more content (e.g., headings, links).
- Add a feature to visualize word frequency using charts or graphs.

## License

This project is licensed under the MIT License.

---
