# FOMC Sentiment Analysis

## Overview
This project analyzes the sentiment of Federal Open Market Committee (FOMC) minutes using Natural Language Processing (NLP) techniques. The goal is to classify the minutes as either *hawkish* or *dovish* based on key phrases, and to expand the analysis over time by incorporating more advanced text analysis methods.

## Current Features
- **Sentiment Classification**: Uses predefined lists of *hawkish* and *dovish* phrases given by ChatGPT to count occurrences and determine sentiment.
- **Web Scraping**: Automatically retrieves FOMC meeting minutes from the Federal Reserve website.
- **Normalization**: Sentiment scores are normalized by the total number of classified phrases.
- **Phrase Matching**: Utilizes the `spaCy` PhraseMatcher to efficiently detect key phrases.

## Planned Enhancements
1. **TF-IDF Integration**
   - Implement TF-IDF (Term Frequency-Inverse Document Frequency) to identify the most prominent phrases in FOMC minutes.
   - Use TF-IDF in conjunction with sentiment analysis to refine *hawkish* and *dovish* classifications.

2. **Text Scraping for Phrase Expansion**
   - Expand the *hawkish* and *dovish* phrase lists by automatically scraping a broader dataset of FOMC minutes and economic reports to find the most found phrases in the minutes to then categorise by hawkish vs dovish.
   - Dynamically update the phrase lists based on significant terms identified through TF-IDF analysis.
  
2. **Quantify Data**
   - Currently, it is grouped by hawkish and dovish.
   - Plans to assign phrases a value from -1 to 1 based on the extent to which it is hawkish/dovish.

4. **Include More Recent Data**
   - Currently, the script processes minutes from 2014 onwards. Plan to include minutes beyond 2020.
   - Ensure compatibility with any format changes in the Federal Reserve's website structure.

5. **Graphical Representation of Sentiment Trends**
   - Plot *hawkish* vs *dovish* sentiment over time using visualization tools (e.g., Matplotlib, Seaborn, or Plotly).
   - Annotate points on the graph with the most important discussion topics (e.g., rates, bonds, stocks, inflation) using extracted keywords.

## Dependencies
- `requests`: For fetching FOMC minutes from the Federal Reserve website.
- `BeautifulSoup`: For parsing HTML and extracting text.
- `spaCy`: For NLP processing and phrase matching.
- `TextBlob`: For TF-IDF calculations.
- `nltk`: For additional text preprocessing.
- `matplotlib/seaborn/plotly` (planned): For data visualization.

## How to Run
1. Install dependencies:
   ```bash
   pip install requests beautifulsoup4 spacy textblob nltk matplotlib seaborn plotly
   ```
2. Download the `en_core_web_sm` model for spaCy:
   ```bash
   python -m spacy download en_core_web_sm
   ```
3. Run the script:
   ```bash
   python analyze_fomc.py
   ```

## Future Considerations
- Improve entity recognition to identify the key topics discussed in each FOMC meeting.
- Use machine learning techniques to improve sentiment classification beyond predefined keyword matching.
- Optimize scraping methods to handle changes in website structure dynamically.

This project aims to evolve into a comprehensive tool for tracking monetary policy sentiment and its implications on financial markets.

