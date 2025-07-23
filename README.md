# 🔍 Python Quote Scraper

This project scrapes quotes from http://quotes.toscrape.com using Python and BeautifulSoup.

## How to Run
```bash
pip install requests beautifulsoup4
python scraper.py
4. Scroll down and *Commit changes*

---

### 🔹 Step 3: Create the scraper.py file
1. On the repo main page, tap *“Add file” > “Create new file”*
2. In the filename box, type: scraper.py
3. Paste this Python code:

```python
import requests
from bs4 import BeautifulSoup

url = 'http://quotes.toscrape.com/page/1/'
response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')
quotes = soup.find_all('div', class_='quote')

for quote in quotes:
    text = quote.find('span', class_='text').text
    author = quote.find('small', class_='author').text
    print(f'"{text}" — {author}') # python-quote-scraper
