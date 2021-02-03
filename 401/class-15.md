# Web Scraping

Web scraping is where we automatically access and extract large amounts of information from a website. To get started we will use turnstile data.

> Note: Make sure that we read the website's terms and conditions before using their data. 

If we inspect the website, we are able to extract the txt files in the `<a>` tag.

To start off, we import our libraries,

```
import requests
import urllib.request
import time
from bs4 import BeautifulSoup
```

Then we set the url,
```
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```
We type in `response` and if we get 200, then it means that we are successful.

We use BeautifulSoup to locate all of our data,

```
soup.findAll('a')
# finds all a tags  
```

We test out the first link,

```
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
```

We use urllib.request library to download to our local machine,
```
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```

Finally, we use `time.sleep(1)` to prevent us from making multiple requests to the website.

We can download all the files using a loop. 
