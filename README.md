
# 1. Overview of Problem Statement

The popularity of online news articles, often measured by the number of shares it receives, depends on various factors such as the article’s content, publication timing, and metadata. Predicting whether an article will become popular is a challenging yet valuable task for news publishers aiming to optimize their content strategies and boost reader engagement. This project leverages machine learning to address this problem using a dataset of online news articles.

# 2. Objective

The goal of this project is to build an accurate machine learning model to predict whether an online news article will be popular, defined here as achieving a number of shares equal to or exceeding a threshold (e.g., 1400 shares), based on its features.

# 3. Data Description:

The Online News Popularity Dataset contains various features related to articles published by Mashable. The objective is to classify articles as Popular or Not Popular based on their content characteristics, metadata, and social signals.
Key Attributes and Description

1. URL & Temporal Features

    url: The link to the news article.
    timedelta: Days between the article's publication date and the dataset collection date.
    Purpose:
    -The recency of an article may influence its likelihood of becoming popular.

2. Content-Based Features

    n_tokens_title: Number of words in the article's title.
    n_tokens_content: Number of words in the article's content.
    n_unique_tokens: Ratio of unique words to total words in the content.
    n_non_stop_words: Ratio of non-stopwords to total words.
    n_non_stop_unique_tokens: Ratio of unique non-stopwords to total words.
    Purpose:
        These features indicate the content length and uniqueness, which may influence popularity.

3. Link and Media Features

    num_hrefs: Number of hyperlinks in the article.
    num_self_hrefs: Number of internal links (links to the same website).
    num_imgs: Number of images embedded in the article.
    num_videos: Number of videos embedded.
    Purpose:
        Media-rich content with images and videos often attracts more attention and shares.

4. Keyword and Topic Features

    num_keywords: Number of keywords used for SEO optimization.
    data_channel_is_lifestyle: 1 if the article is categorized under lifestyle, 0 otherwise.
    data_channel_is_entertainment: 1 if categorized under entertainment.
    data_channel_is_bus: 1 if categorized under business.
    data_channel_is_socmed: 1 if categorized under social media.
    data_channel_is_tech: 1 if categorized under technology.
    data_channel_is_world: 1 if categorized under world news.
    Purpose:
        These features represent article categories, which may impact the shareability.

5. Keyword Statistics Features

    kw_min_min: Minimum value of shares across keywords in the article.
    kw_max_min: Maximum value of shares across keywords.
    kw_avg_min: Average value of shares across keywords.
    kw_min_max: Minimum value of shares across all articles containing the same keywords.
    kw_max_max: Maximum value of shares across all articles with the same keywords.
    kw_avg_max: Average value of shares across articles with the same keywords.
    kw_min_avg: Minimum of average keyword shares.
    kw_max_avg: Maximum of average keyword shares.
    kw_avg_avg: Average of average keyword shares.
    Purpose:
        These features capture keyword effectiveness in driving article popularity.

6. Self-Reference Shares

    self_reference_min_shares: Minimum shares for the article's referenced articles.
    self_reference_max_shares: Maximum shares for the referenced articles.
    self_reference_avg_sharess: Average shares for referenced articles.
    Purpose:
        Helps identify whether referencing popular articles impacts the current article's popularity.

7. Temporal Features

    weekday_is_monday: 1 if the article was published on Monday, 0 otherwise.
    weekday_is_tuesday: 1 if published on Tuesday.
    weekday_is_wednesday: 1 if published on Wednesday.
    weekday_is_thursday: 1 if published on Thursday.
    weekday_is_friday: 1 if published on Friday.
    weekday_is_saturday: 1 if published on Saturday.
    weekday_is_sunday: 1 if published on Sunday.
    is_weekend: 1 if published on the weekend, 0 otherwise.
    Purpose:
        Allows the model to consider whether posting day influences popularity.

8. Latent Dirichlet Allocation (LDA) Features

    LDA_00: Topic 1 distribution score.
    LDA_01: Topic 2 distribution score.
    LDA_02: Topic 3 distribution score.
    LDA_03: Topic 4 distribution score.
    LDA_04: Topic 5 distribution score.
    Purpose:
        These features represent the topic distribution of the article, indicating its thematic focus.

9. Sentiment & Subjectivity Features

    global_subjectivity: Average subjectivity of the article (0 = objective, 1 = highly subjective).
    global_sentiment_polarity: Average sentiment polarity (-1 = negative, 1 = positive).
    global_rate_positive_words: Rate of positive words in the content.
    global_rate_negative_words: Rate of negative words.
    rate_positive_words: Ratio of positive words to total words.
    rate_negative_words: Ratio of negative words to total words.
    avg_positive_polarity: Average polarity of positive words.
    min_positive_polarity: Minimum polarity of positive words.
    max_positive_polarity: Maximum polarity of positive words.
    avg_negative_polarity: Average polarity of negative words.
    min_negative_polarity: Minimum polarity of negative words.
    max_negative_polarity: Maximum polarity of negative words.
    title_subjectivity: Subjectivity of the article's title.
    title_sentiment_polarity: Sentiment polarity of the title.
    abs_title_subjectivity: Absolute value of the title's subjectivity.
    abs_title_sentiment_polarity: Absolute value of the title's sentiment polarity.
    Purpose:
        These features capture sentiment and tone, which may influence article popularity.

10. Target Variable

    popularity: Binary classification of articles as Popular (1) or Not Popular (0).
    Purpose:
        This is the target variable for prediction.
        The popularity column was derived from the shares column by applying a threshold to classify articles into Popular or Not Popular categories.

Key Insights from the Dataset

    Content length, media richness, and SEO keyword usage play a vital role in determining popularity.
    Sentiment and subjectivity features indicate whether emotional or factual content drives more shares.
    The weekday and weekend flags allow for temporal trend analysis.

4. Data Collection:

Source: UCI Machine Learning Repository

Dataset-link: https://archive.ics.uci.edu/dataset/332/online+news+popularity


