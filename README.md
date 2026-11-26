# Eastern Marine Tourism — Sentiment Analysis Dataset and Code

This repository contains the dataset and analysis code supporting the study *"Visitor Sentiment Patterns Across Tourism Lifecycle Stages: A Sentiment Analysis of Marine Destinations in Eastern Thailand."* The study analyzes TripAdvisor reviews from seven marine tourism destinations across four provinces in Eastern Thailand (Chon Buri, Rayong, Chanthaburi, and Trat) collected between 2014 and 2023.

## Repository Contents

### 1. `Sentiment_Data_Scraping.ipynb`
Python notebook used to collect review data from TripAdvisor for each destination. Extracts review text, rating, date, and reviewer metadata from destination listing and review pages.

### 2. `Sentiment_Clean_and_Predict.ipynb`
Python notebook used to clean the collected review data and classify sentiment using the VADER (Valence Aware Dictionary and sEntiment Reasoner) lexicon-based algorithm. Reviews are classified as Positive (compound score ≥ 0.05), Neutral (−0.05 to 0.05), or Negative (≤ −0.05).

### 3. `All_Reviews_Dataset.xlsx`
The processed dataset used in the published analysis, containing 13,183 reviews. To protect reviewer privacy, review text and all personally identifiable information (e.g., reviewer name, location) have been removed; only the fields below are included.

| Column | Description |
|---|---|
| `Review_ID` | Anonymous unique identifier (R00001–R13183) |
| `Destination` | One of seven marine tourism destinations |
| `Province` | Chon Buri, Rayong, Chanthaburi, or Trat |
| `Review_Date` | Date the review was posted (YYYY-MM-DD) |
| `Rating` | Star rating given by the reviewer (1–5) |
| `VADER_Compound_Score` | VADER sentiment score (−1 to +1) |
| `Sentiment_Category` | Positive, Neutral, or Negative |

### 4. `Sentiment_Validation.ipynb`
Python notebook that validates VADER sentiment classifications against star-rating-derived ground truth labels, using `All_Reviews_Dataset.xlsx` directly. Ratings of 4-5 stars are treated as Positive, 3 stars as Neutral, and 1-2 stars as Negative, and this ground truth is compared against the `Sentiment_Category` column across the complete dataset (n = 13,183). Running this notebook reproduces the validation results (overall agreement, precision, recall, and F1-score by class) reported in the manuscript.

### 5. `Problem_Category_Counts.csv`
The destination-by-category counts underlying Table 3 of the manuscript: the number of coded issue mentions in each of five problem categories (pollution and littering, inadequate infrastructure, poor service quality, overcrowding and noise disturbances, accessibility challenges) at each of the seven destinations, based on manual coding of the 1,458 negative reviews by three independent coders (see coding protocol, S1 File).

### 6. `TALC_Analysis.ipynb`
Python notebook that reproduces the statistical analyses underlying Table 2, Table 4, and related results in the manuscript, using `All_Reviews_Dataset.xlsx` and `Problem_Category_Counts.csv`: Wilson score 95% confidence intervals for sentiment proportions, a chi-square test of independence with Cramér's V comparing sentiment across TALC stage groupings, Location Quotient values identifying the predominant problem category at each destination, and a robustness check comparing pre-pandemic (2014-2019) and full-period (2014-2023) negative sentiment proportions.

## Privacy and Ethics

No personally identifiable information is included in this repository. Data collection and use were conducted for non-commercial academic research and were reviewed by the Burapha University Human Research Ethics Committee (Exemption Determination, Certificate No. IRB2-011/2567).

## Citation

If you use this dataset or code, please cite the associated publication (details to be added upon publication).
