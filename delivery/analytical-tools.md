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

1. [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) - A navigator for an HTML document

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

Optical character recognition (OCR) has been around a long time.
Early on it worked "well enough" to be useful, but not 100% reliable.
Its accuracy was eventually improved by using machine learning to train models.

Today, a fairly accurate, open source OCR engine is available to anyone through Tesseract.

### Goals

1. Extract useful text from an image

### Tools

1. [Tesseract](https://github.com/tesseract-ocr/tesseract) - The OCR engine
1. [Pillow](https://python-pillow.org/) - A library for reading images
1. [pytesseract](https://github.com/madmaze/pytesseract) - A wrapper for Tesseract

### Examples

```python
import os

import PIL
import pytesseract

image = PIL.Image.open(local_file)

print(pytesseract.image_to_string(image))
```

### Further reading

1. https://en.wikipedia.org/wiki/Tesseract_(software)
1. https://github.com/tmbdev/ocropy

---

## Cleaning text

__skill level__ Beginner to Intermediate

Computers are fast, but not that smart.
Some processes will go faster, or yield better results if they are fed prepared data.

### Goals

1. Convert text to ASCII.  This can be as simple as removing "smart quotes" from a Word document
1. Convert text to lowercase
1. Remove punctuation
1. Remove excess whitespace
1. Remove stopwords
1. Find [lemmas](https://en.wikipedia.org/wiki/Lemma_(morphology)#Lexicography)
1. Apply [stemming](https://en.wikipedia.org/wiki/Stemming)

### Tools

1. [spaCy](https://spacy.io/) - An open-source NLP toolkit
1. [nltk](https://www.nltk.org/) - The original NLP toolkit started at Stanford University

### Examples

1. https://github.com/susanli2016/NLP-with-Python/blob/master/Cleaning%20Text.ipynb
1. https://github.com/STSILABS/uscis-bdso-demo/blob/issue-3/jupyter/src/toolkit/to_sentences.py
1. https://github.com/JeffreyMFarley/hew/blob/master/hew/normalizer.py

### Further reading

1. :grin:

---

## Match similar strings into a common form

__skill level__ Beginner to Intermediate

### Goals
### Tools
### Examples
### Further reading

---

## Find clusters in the data

__skill level__ Intermediate to Advanced

### Goals
### Tools
### Examples

1. https://github.com/JeffreyMFarley/clustersplaining

### Further reading

---

## Find the topics of a document

__skill level__ Intermediate

### Goals
### Tools
### Examples
### Further reading

---

## See what items frequently occur together

__skill level__ Intermediate to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Highlight the proper nouns of a document


__skill level__ Beginner to Intermediate

### Goals
### Tools
### Examples
### Further reading

---

## Categorize words

__skill level__ Intermediate to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Determine if text is "positive" or "negative"

__skill level__ Beginner to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Scrape information from one form and input into another

__skill level__ Beginner to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Predict what text should be displayed next


__skill level__ Beginner to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Generate text similar to an existing set of documents

__skill level__ Beginner to Advanced

### Goals
### Tools
### Examples
### Further reading

---

## Determine how two things are related


__skill level__ Beginner to Advanced

### Goals
### Tools
### Examples
### Further reading

