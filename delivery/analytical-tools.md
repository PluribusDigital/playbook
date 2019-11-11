# Analytical Tools

People talk about artificial intelligence (AI), machine learning (ML) or natural language processing (NLP),
but what specifically can these tools be used for?

This guide will clarify how we use those concepts at STSI by listing specific analytical tasks and how AI is used to accomplish it.

## Scrape text from the web

__skill level__ Beginner

Most NLP tasks will require plain text files as input.
While there is a lot of text out in the internet, it is not in a useful form.
It has headers, navigation bars, ads, social links, scripts and dozens of other "extra" elements.

Scraping text into a useful form is the first job for any analysis.

### Goals

1. Extract useful text from web pages "in the wild".

### Tools

1. [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

### Examples

```python
import io
import requests
from bs4 import BeautifulSoup

# Get the HTML page
r = requests.get('https://en.wikipedia.org/wiki/Grace_Hopper')

soup = BeautifulSoup(r.content, "html.parser")

# The string that goes in `soup.select` will be specific to each web page
# It can be found by right-clicking on the main text and choosing "Inspect"
# to get the style path
for section in soup.select('div.mw-parser-output p'):
    print(section.get_text())
```

---

## Extract text from an image

__skill level__ Beginner to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Cleaning text
## Match similar strings into a common form
## Find clusters in the data
## Find the topics of a document
## See what items frequently occur together
## Highlight the proper nouns of a document
## Categorize words
## Determine if text is "positive" or "negative"
## Scrape information from one form and input into another
## Predict what text should be displayed next
## Generate text similar to an existing set of documents
## Determine how two things are related


