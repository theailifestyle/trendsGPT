

# **TrendsGPT**

TrendsGPT is an automated AI agent designed for data analysis and market research. It identifies trending news articles from Reddit, determines sentiment, extracts article content, identifies key trending keywords, and even suggests T-shirt ideas based on the article content!

## **Table of Contents**

- Features
- Requirements
- Installation
- How to Use
- Code Overview
- Function Descriptions

## **Features**

1. **Sentiment Analysis**: Uses OpenAI's GPT-4 to determine the sentiment of Reddit headlines.
2. **Content Extraction**: Extracts the content of selected articles.
3. **Keyword Identification**: Recognizes top keywords from the article content.
4. **Trend Analysis**: Checks the popularity of the identified keywords using Google Trends.
5. **Idea Generation**: Suggests T-shirt ideas based on trending keywords and article content.

## **Requirements**

- Python 3.x
- Praw, OpenAI, Requests, BeautifulSoup4, Pytrends, Pandas

## **Installation**

1. Clone this repository:
```bash
git clone <repository-link>
```
2. Navigate to the directory and install required Python packages:
```bash
cd <repository-name>
pip install praw openai requests beautifulsoup4 pytrends pandas
```

## **How to Use**

1. Set up your API keys:
    - For Reddit (`CLIENT_ID`, `CLIENT_SECRET`), get them [here](https://www.reddit.com/prefs/apps).
    - For OpenAI (`OPENAI_API_KEY`), get it from the [OpenAI website](https://www.openai.com/).
2. Run the main script:
```bash
python <script-name>.py
```
3. Results will be saved in a CSV file named `memeworthy_articles.csv`.

## **Code Overview**

The code follows these steps:

1. **Initialization**: Set up Reddit and OpenAI clients.
2. **Article Collection**: Fetch top weekly articles from Reddit's `nba` subreddit.
3. **Sentiment Analysis**: Analyze sentiment of headlines using OpenAI.
4. **Content Extraction**: Extract and summarize article content.
5. **Keyword Identification**: Recognize top keywords from the article content.
6. **Trend Analysis**: Analyze keyword popularity using Google Trends.
7. **Idea Generation**: Suggest T-shirt ideas using OpenAI.
8. **Data Storage**: Store all findings in a DataFrame and export it to a CSV.

## **Function Descriptions**

1. **`get_sentiment(headline)`**:
    - **Input**: A string containing a headline.
    - **Output**: Sentiment of the headline ("positive", "neutral", or "negative").
    - Uses OpenAI to determine the sentiment of a given headline.

2. **`fetch_article_content(url, headline)`**:
    - **Input**: URL of the article, and its headline.
    - **Output**: Extracted content of the article.
    - Uses `requests` and `BeautifulSoup` to extract article content.

3. **`get_keywords_from_article(article)`**:
    - **Input**: A string containing article content.
    - **Output**: List of top keywords from the article.
    - Uses OpenAI to identify and extract the top keywords from the provided article content.

4. **`check_google_trends(keyword)`**:
    - **Input**: A keyword string.
    - **Output**: Popularity score of the keyword using Google Trends.
    - Utilizes `pytrends` to fetch the trend score of a given keyword.

5. **`get_tshirt_ideas(keywords, article_text)`**:
    - **Input**: List of keywords and the article content.
    - **Output**: T-shirt ideas based on the keywords and article content.
    - Leverages OpenAI to suggest T-shirt ideas.

6. **`get_article_summary(article)`**:
    - **Input**: A string containing article content.
    - **Output**: Summarized version of the article.
    - Uses OpenAI to generate a concise summary of the given article content.

## **Note**

Please be mindful of API rate limits, especially when making frequent requests.
