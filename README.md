# Movie-Review-Sentiment-Analysis

# 0. Repository Contents
## Did "Barbie” (2023) receive more favorable audience ratings and reviews on IMDb compared to "Oppenheimer” (2023) among viewers in the United States within the first three months of release? Which movie did audiences prefer? This repository contains a sentiment analysis approach towards answering that question, contained in a number of Jupyter notebooks. In the SCRIPTS directory there is a querying script (queryFromRequests.ipynb) that performs web scraping on IMDb, and writes that data into DATA/barbie_reviews.csv and DATA/oppenheimer_reviews.csv. Also in scripts is sentiment_analysis.ipynb which performs sentiment analysis on the cleaned data, and writes back that data with new sentiment (POSITIVE, NEGATIVE, NEUTRAL) and numerical sentiment score features into DATA/barbie_reviews_sentiment.csv and DATA/oppenheimer_reviews_sentiment.csv. From these data files, final statistical analysis is performed in SCRIPTS/statistical_tests.ipynb, including a two-sample proportion test, permutation analysis, and random multi-variate analysis.

# 1. Software and Platform
We are writing our scripts in Jupyter notebooks for readability. Notable packages we used were HuggingFace transformers and tensorflow for sentiment analysis; sklearn for clustering; selenium for making web requests; and Numpy, Pandas, and Matplotlib for working with data. We chose VSCode Mac/Windows as our preferred IDE and Git for version control.

# 2. File Tree
```
├── DATA
│   ├── barbie_reviews.csv
│   ├── barbie_reviews_sentiment.csv
│   ├── oppenheimer_reviews.csv
│   └── oppenheimer_reviews_sentiment.csv
├── OUTPUTS
├── README.md
└── SCRIPTS
    ├── analysis_plan.png
    ├── queryFromRequests.ipynb
    ├── sentiment_analysis.ipynb
    └── statistical_tests.ipynb
```

# 3. Reproducing Results
1. Review the SCRIPTS/analysis_plan.png
2. Run the SCRIPTS/queryFromRequests.ipynb notebook to write the barbie_reviews.csv and oppenheimer_reviews.csv (or alternatively simply use those existing files in the DATA directory)
3. Run the SCRIPTS/sentiment_analysis.ipynb notebook to write the barbie_reviews_sentiment.csv and oppenheimer_reviews_sentiment.csv. The notebook will also display graphs and graphics about the distribution of POSITIVE/NEGATIVE/NEUTRAL scores across the two movies, and other data visualization such as sentiments for individual reviews and distributions about the effect of review text length on sentiment score.
4. Once the data is pre-processed, run the SCRIPTS/statistical_tests.ipynb notebook to glean p-values obtained from the two-sample proportion test, distributions of null p-values and z-scores for the permutation analysis, and comparisons between average Barbie/Oppenheimer reviews versus their assigned sentiment scores.
5. OR: run the master script SCRIPTS/master_script.ipynb to run all of the above steps in sequential order.