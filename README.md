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

## Privacy and Ethics

No personally identifiable information is included in this repository. Data collection and use were conducted for non-commercial academic research and were reviewed by the Burapha University Human Research Ethics Committee (Exemption Determination, Certificate No. IRB2-011/2567).

## Citation

If you use this dataset or code, please cite the associated publication (details to be added upon publication).
