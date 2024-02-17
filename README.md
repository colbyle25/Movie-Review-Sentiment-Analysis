[![Contributors][contributors-shield]][contributors-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<br />
<div stye="text-align: center;">

  <a href="https://docs.google.com/document/d/1s_uNuLqHY8VSd5b8DqdTbM0EI1HgTjLh-ZQbCcThVfA/edit?usp=sharing">
    <img src="SCRIPTS/analysis_plan.png" style="margin: auto;" width="700" alt="Analysis Plan"></img>
  </a>
</div>
<br />

# Barbenheimer Sentiment Analysis

<details>
  <summary><strong>Table of Contents</strong></summary>
  <ol>
    <li><a href="#authors">Authors</a></li>
    <li><a href="#repository-contents">Repository Contents</a></li>
    <li><a href="#software-and-platform">Software and Platform</a></li>
    <li><a href="#file-tree">File Tree</a></li>
    <li><a href="#reproducing-results">Reproducing Results</a></li>
  </ol>
</details>
<br />

## Authors: 
Maajid Husain - mah2ksc@virginia.edu <br />
Colby Le - ncc9kn@virginia.edu <br />
Mohammad Murad - vdr4jr@virginia.edu

## Repository Contents
Did "Barbie” (2023) receive more favorable audience ratings and reviews on IMDb compared to "Oppenheimer” (2023) among viewers in the United States within the first three months of release? Which movie did audiences prefer? This repository contains a sentiment analysis approach towards answering that question, contained in a number of Jupyter notebooks. In the SCRIPTS directory there is a querying script ([`queryFromRequests.ipynb`](SCRIPTS/queryFromRequests.ipynb) that performs web scraping on IMDb, and writes that data into [`DATA/barbie_reviews.csv`](DATA/barbie_reviews.csv) and [`DATA/oppenheimer_reviews.csv`](DATA/oppenheimer_reviews.csv). Also in scripts is `sentiment_analysis.ipynb` which performs sentiment analysis on the cleaned data, and writes back that data with new sentiment (POSITIVE, NEGATIVE, NEUTRAL) and numerical sentiment score features into [`DATA/barbie_reviews_sentiment.csv`](DATA/barbie_reviews_sentiment.csv) and [`DATA/oppenheimer_reviews_sentiment.csv`](DATA/oppenheimer_reviews_sentiment.csv). From these data files, final statistical analysis is performed in [`SCRIPTS/statistical_tests.ipynb`](SCRIPTS/statistical_tests.ipynb), including a two-sample proportion test, permutation analysis, and random multi-variate analysis.

## Software and Platform
We are writing our scripts in Jupyter notebooks for readability. Notable packages we used were HuggingFace transformers and tensorflow for sentiment analysis; sklearn for clustering; selenium for making web requests; and Numpy, Pandas, and Matplotlib for working with data. We chose VSCode Mac/Windows as our preferred IDE and Git for version control.

## File Tree
```
.
├── DATA
│   ├── Data Dictionary.pdf
│   ├── barbie_reviews.csv
│   ├── barbie_reviews_sentiment.csv
│   ├── oppenheimer_reviews.csv
│   └── oppenheimer_reviews_sentiment.csv
├── LICENSE
├── OUTPUT
│   ├── Average Sentiment Score.png
│   ├── Barbie Sentiment Distribution.png
│   ├── Clustering of Barbie Sentiments.png
│   ├── Clustering of Oppenheimer Sentiments.png
│   ├── Clustering of Sentiments.png
│   ├── Mean Reviewer Score.png
│   ├── Null Distribution of P-Value.png
│   ├── Null Distribution of Z-Statistic.png
│   ├── Oppenheimer Sentiment Distribution.png
│   ├── Sentiment Distribution.png
│   └── Text Length VS Sentiment.png
├── README.md
└── SCRIPTS
    ├── analysis_plan.png
    ├── master_script.ipynb
    ├── queryFromRequests.ipynb
    ├── sentiment_analysis.ipynb
    └── statistical_tests.ipynb
```

## Reproducing Results
1. Review the SCRIPTS/analysis_plan.png
2. Run the SCRIPTS/queryFromRequests.ipynb notebook to write the barbie_reviews.csv and oppenheimer_reviews.csv (or alternatively simply use those existing files in the DATA directory)
3. Run the SCRIPTS/sentiment_analysis.ipynb notebook to write the barbie_reviews_sentiment.csv and oppenheimer_reviews_sentiment.csv. The notebook will also display graphs and graphics about the distribution of POSITIVE/NEGATIVE/NEUTRAL scores across the two movies, and other data visualization such as sentiments for individual reviews and distributions about the effect of review text length on sentiment score.
4. Once the data is pre-processed, run the SCRIPTS/statistical_tests.ipynb notebook to glean p-values obtained from the two-sample proportion test, distributions of null p-values and z-scores for the permutation analysis, and comparisons between average Barbie/Oppenheimer reviews versus their assigned sentiment scores.
5. OR: run the master script SCRIPTS/master_script.ipynb to run all of the above steps in sequential order.

[contributors-shield]: https://img.shields.io/github/contributors/colbyle25/Movie-Review-Sentiment-Analysis.svg?style=for-the-badge
[contributors-url]: https://github.com/colbyle25/Movie-Review-Sentiment-Analysis/graphs/contributors
[stars-shield]: https://img.shields.io/github/stars/colbyle25/website.svg?style=for-the-badge
[issues-shield]: https://img.shields.io/github/issues/colbyle25/Movie-Review-Sentiment-Analysis.svg?style=for-the-badge
[issues-url]: https://github.com/colbyle25/Movie-Review-Sentiment-Analysis/issues
[license-shield]: https://img.shields.io/github/license/colbyle25/Movie-Review-Sentiment-Analysis.svg?style=for-the-badge
[license-url]: https://github.com/colbyle25/Movie-Review-Sentiment-Analysis/blob/master/LICENSE
[product-screenshot]: public/Images/_Common