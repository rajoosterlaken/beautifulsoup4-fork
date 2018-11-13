Beautiful Soup is a library that makes it easy to scrape information
from web pages. It sits atop an HTML or XML parser, providing Pythonic
idioms for iterating, searching, and modifying the parse tree.

# Differences
This is an extension of the original BS4 v4.6.3 that extends the `Tag` object
with `startPosition` and `endPosition` attributes, that will return the string indices where the underlying parser begins and ends with parsing the tag.
The goal is to replicate the extension made in [this repository](https://github.com/tvogels/jsoup).

# Quick start

```
  >>> from bs4 import BeautifulSoup
  >>> soup = BeautifulSoup("<p>Some<b>bad<i>HTML")
  >>> print soup.prettify()
  <html>
   <body>
    <p>
     Some
     <b>
      bad
      <i>
       HTML
      </i>
     </b>
    </p>
   </body>
  </html>
  >>> soup.find(text="bad")
  u'bad'

  >>> soup.i
  <i>HTML</i>

  >>> soup = BeautifulSoup("<tag1>Some<tag2/>bad<tag3>XML", "xml")
  >>> print soup.prettify()
  <?xml version="1.0" encoding="utf-8">
  <tag1>
   Some
   <tag2 />
   bad
   <tag3>
    XML
   </tag3>
  </tag1>
```

To go beyond the basics, [comprehensive documentation is available](http://www.crummy.com/software/BeautifulSoup/bs4/doc/).

# Links

* [Homepage](http://www.crummy.com/software/BeautifulSoup/bs4/)
* [Documentation](http://www.crummy.com/software/BeautifulSoup/bs4/doc/)
* [Discussion group](http://groups.google.com/group/beautifulsoup/)
* [Development](https://code.launchpad.net/beautifulsoup/)
* [Bug tracker](https://bugs.launchpad.net/beautifulsoup/)
* [Complete changelog](https://bazaar.launchpad.net/~leonardr/beautifulsoup/bs4/view/head:/NEWS.txt)

# Building the documentation

The bs4/doc/ directory contains full documentation in Sphinx
format. Run `make html` in that directory to create HTML
documentation.

# Running the unit tests

Beautiful Soup supports unit test discovery from the project root directory:

```
 $ nosetests
```

```
 $ python -m unittest discover -s bs4 # Python 2.7 and up
```

If you checked out the source tree, you should see a script in the
home directory called test-all-versions. This script will run the unit
tests under Python 2.7, then create a temporary Python 3 conversion of
the source and run the unit tests again under Python 3.

