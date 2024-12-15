# Creating a Web Scraping Program
* This will be an introduction on how to create a basic web scraping program

# Operating System Used
* Windows 11

# Programs
1. Thonny (easy to use Python environment)
# Python Libraries
1. BeautifulSoup
2. Requests
# Websites
1. Quotes to Scrape
# Steps Overview
1. Download the libraries by using their respective websites
2. Install the libraries into Thonny
3. Find information to scrape
4. Retrieve the HTML and define authors and quotes
5. Write code and test

# Download the Package Libraries
1.https://www.crummy.com/software/BeautifulSoup/#Download

 ![Screenshot 2024-12-14 111034](https://github.com/user-attachments/assets/559dcf2d-98fd-4416-8760-653e9d6fb931)

2.https://docs.python-requests.org/en/latest/index.html

 ![Screenshot 2024-12-14 111425](https://github.com/user-attachments/assets/4f09dd56-6978-489f-ad3f-e9b966e69554)

* Both package libraries are required in order to retrieve (BeautifulSoup) then parse (Requests) the HTML

# Install the Libraries into Thonny
 1. Find the tar.gz files inside your downloads (now is a good time to mention that you can pip install these libraries using Command Prompt, but it's much easier and foolproof to download then install as local files when using Thonny)

![Screenshot 2024-12-14 112925](https://github.com/user-attachments/assets/85c313b3-656e-4f79-b82a-177044b5c3a9)

2. Open Thonny, click "Tools" tab then "Manage packages"

![Screenshot 2024-12-14 112250](https://github.com/user-attachments/assets/b3e4977d-d22e-4e3f-baed-68f63b61a9ba)

3. In the "INSTALL" tab look for "Install from local file" and click "here".

![Screenshot 2024-12-14 112359](https://github.com/user-attachments/assets/cc2e4824-4cdc-4f52-b831-b31e3883372c)

# Finding HTML to Scrape
1.Scraping from websites is a lot like Copyright law, in that you must find a website okay with scraping. This project will be using https://quotes.toscrape.com/ which is a wonderful website built for the purpose of testing Scrape programs.

![Screenshot (1)](https://github.com/user-attachments/assets/e3ac5050-051f-4758-9c0c-6bd4cd5283db)

2. Right click the quote and look for the HTML with the tag "text". This will be the quote we scrape.

![text](https://github.com/user-attachments/assets/1e63ffb2-e0ce-4d4d-9d3f-1318e43d552f)

3. Now we will do the same for the author section

![Screenshot 2024-12-15 102549](https://github.com/user-attachments/assets/352e804a-9aa1-456d-8051-322e3eff303b)

# Writing the Code
Now to write our code. We will start with telling the program to use the packages we downloaded earlier, then tell it what website we are scraping from, use BeautifulSoup to start scraping, define quotes and authors, and use zip to properly organize the information.

```python
 from bs4 import BeautifulSoup
import requests

page_to_scrape = requests.get("http://quotes.toscrape.com")
soup = BeautifulSoup (page_to_scrape.text, "html.parser")
quotes = soup.findAll ("span", attrs={"class":"text"})
authors = soup.findAll("small", attrs={"class":"author"})

for quote, author in zip(quotes, authors):
    print(quote.text + "-" + author.text)

```
# Final Result

![Screenshot 2024-12-15 040851](https://github.com/user-attachments/assets/cd82dba7-7586-4b3f-8212-d9240cf3bfe2)





