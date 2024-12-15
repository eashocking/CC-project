# Creating a web scraping program
* This will be a intro on how to create a basic web scraping program

# Operating System used
* Windows 11

# Programs
1. Thonny (easy to use python enviroment)
# Python libraries
1. Beautiful soup
2. Request
# Websites
1. Quotes to Scrape
# Steps Overview
1. Download the librarys by using their respected websites
2. Instal the librarys into Thonny
3. Finding info to scrape
4. Retreave the HTML and define authers and quotes
5. Write code and test

# Download the package libraries
1.https://www.crummy.com/software/BeautifulSoup/#Download

 ![Screenshot 2024-12-14 111034](https://github.com/user-attachments/assets/559dcf2d-98fd-4416-8760-653e9d6fb931)

2.https://docs.python-requests.org/en/latest/index.html

 ![Screenshot 2024-12-14 111425](https://github.com/user-attachments/assets/4f09dd56-6978-489f-ad3f-e9b966e69554)

* These are requered in order to both retreave then parse the HTML

# intal the Libraries into Thonny
 1. Find the tar.gz files inside your downloads (now is a good time to mention you can pip instal these librarys using command prompt but its much easier and foolproof to download then instal as local files when using Thonny)

![Screenshot 2024-12-14 112925](https://github.com/user-attachments/assets/85c313b3-656e-4f79-b82a-177044b5c3a9)

2. Open Thonny and open the tools tab clicking manage packagaes

![Screenshot 2024-12-14 112250](https://github.com/user-attachments/assets/b3e4977d-d22e-4e3f-baed-68f63b61a9ba)

3. In the "INSTAL" tab look for "instal from local files" and click "here".

![Screenshot 2024-12-14 112359](https://github.com/user-attachments/assets/cc2e4824-4cdc-4f52-b831-b31e3883372c)

# finding HTML to scrape
1.Scraping from websites is alot like Copyright law in you must find a website that is okay with scraping. This Project will be using https://quotes.toscrape.com/ a wonderful website built for the perpose of testing Scrape programs.

![Screenshot (1)](https://github.com/user-attachments/assets/e3ac5050-051f-4758-9c0c-6bd4cd5283db)

2. Right click the the quote and look for the HTML with the tag "text". This will be the quote we scrape.

![text](https://github.com/user-attachments/assets/1e63ffb2-e0ce-4d4d-9d3f-1318e43d552f)

3. Now we will do the same for the author section

![text](https://github.com/user-attachments/assets/fc6f7269-2fe4-4962-87e3-3b2347d52aeb)

# Writing the Code
We now will write our code, we will start with telling the program to use the packages we downloaded earlier, we will then tell it what website we are scraping from, use beautifulsoup to start scraing, define quotes and authers, then use zip to prperly orgonize the info.

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
# Final result

![Screenshot 2024-12-15 040851](https://github.com/user-attachments/assets/cd82dba7-7586-4b3f-8212-d9240cf3bfe2)





