# Tl;dr

## Inspiration ##
We've all seen it: huge blocks of dense text that pop up before you install a new piece of software or sign up for a new service. These days, End User License Agreements are everywhere but most of the time are too long and full of jargon for consumers to feasibly read. We wanted to create something that would help consumers stay informed on what they are agreeing to and how their data is being used by companies. Users cannot reasonably be expected to read dozens of pages of text for every product they use, but we hope to help prevent people from inadvertently agreeing to dubious privacy violations and signing away their rights.

**tl;dr:** what haven't you been reading in the Terms of Services you agree to?

## What It Does ##

Our application, Tl;dr, finds the most notable sections of such a legal document — namely, sections which seem unusual and do not align with typical EULAs — and compiles them into a brief summary. It is a Chrome Extension that users can use directly from their browser when they encounter one of these legal documents. A user would highlight the text they wish to be summarized and would subsequently see a brief summary that lists the most noteworthy parts of the document. 

## How It Works ##

We created an algorithm to process the text. It transforms the text into separate sentences and then transforms words to vectors based on a corpus of text of the English language taken from the NLTK module on Python. From there, we compare our sentences with sentences present in some standard EULAs. We use cosine similarity between vectors to find the sentences in our text that were most unusual given the ground truth and rank them.

## How To Use It ##

### Installing the Chrome extension:

Visit chrome://extensions/, click the "Load Unpacked" button, and select the ```extensions``` folder when prompted.

### To use the Chrome extension:

Highlight your target text, right-click and select "Simplify" in the context menu. The summary should appear in the bottom-right corner of your screen.

## Built With ##

- [Flask](http://flask.pocoo.org/docs/1.0/)
- [Natural Language Toolkit (NLTK)](https://www.nltk.org/index.html)
- [scikit learn](https://scikit-learn.org/stable/documentation.html)
- [Gunicorn](http://docs.gunicorn.org/en/stable/index.html)
