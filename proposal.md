## Title: Text and data mining scientific articles with allofplos

## Short Abstract
Mining scientific articles is hard when many of them are inaccessible behind paywalls. The Public Library of Science (PLOS) is a non-profit Open Access science publisher of the single largest journal (*PLOS ONE*), whose articles are all freely available to read and re-use. allofplos is a Python package for maintaining a constantly growing collection of PLOS's 227,000+ articles. It also quickly and easily parses these article files into Python data structures.
This talk will cover how allofplos keeps your articles up-to-date, and how it analyzes common article metadata to fuel your meta-research.
## Long Abstract
### Background/motivation
#### Why mine scientific articles?
* Science articles represent scientific knowledge
* XML is version of articles for machines, while PDF is for humans
* Tool for meta-research and meta-science
* Quickly identify sets of articles of interest
* Identify research literature trends over time (study findings, jargon usage, citation networks)
#### PLOS and its article corpus
* 220,000+ scientific articles from a wide array of research fields, focusing on the medical and life sciences
* Publisher since 2003
* Open Access: free to read, free to re-use
* Creative Commons license (CC-BY, CC0)
* Many other scientific articles are behind a paywall
### allofplos
#### What it is
* Python package for both downloading and parsing PLOS XML articles
* Turns PLOS XML articles into Python data structures
* Doesn't require knowledge of XML to use
* Focuses on article metadata (e.g., title, authors, date of publication)
#### How it works
* Initialize a corpus with a folder of articles (ships with.a starter directory)
* Initialize an article object w/DOI or XML filename
* Metadata follows intuitive property structure (article.title, article.journal, article.authors)
* Parser uses lxml under the hood
* Article class memoizes the lxml ElementTree object for rapid querying of multiple properties
### On XML elements, JATS, and lxml
#### XML
XML elements have four key properties in the lxml.etree library:
`element = <alt-title alt-title-type="running-head">Essay</alt-title>`
>>> element.tag  
'alt-title'
>>> element.text
'Essay'  
>>> element.attrib  # is a dictionary  
{'alt-title-type': 'running-head'}
>>> element.tail  # for any text that comes directly after closing tag and before another tag  
* XML elements can have sub-elements
>>> element.getchildren()
#### XPath returns a list of search results



### Relevant external links
* allofplos on [GitHub](https://github.com/PLOS/allofplos)
* allofplos on [PyPI](https://pypi.python.org/pypi/allofplos)
* allofplos [tutorial](https://github.com/eseiver/xml_tutorial) and [slides](https://github.com/eseiver/xml_tutorial/blob/master/allofplos_presentation%20slides.pdf) from The Hacker Within at UC Berkeley, Nov 2017
* Lead author's presentation at Peer Review Congress, Sep 2017: https://www.youtube.com/watch?v=3wxsLIpcg80

