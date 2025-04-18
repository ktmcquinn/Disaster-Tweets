# 📄 Dataset Description

This project uses data from the [Kaggle NLP Disaster Tweets competition](https://www.kaggle.com/competitions/nlp-getting-started).

## 🗃️ Files Included

### `train.csv`
- 7,613 tweets
- Each row includes:
  - `id`: Unique identifier for the tweet
  - `keyword`: A relevant disaster-related keyword (e.g. "fire", "earthquake") — may contain missing values
  - `location`: User-submitted location — may contain missing values
  - `text`: The content of the tweet
  - `target`: Label indicating if the tweet is about a real disaster (`1`) or not (`0`)

### `test.csv`
- 3,263 tweets without labels
- Structure is the same as `train.csv`, excluding the `target` column

### `sample_submission.csv`
- Template showing the expected submission format:
  - `id`: Matches the test set
  - `target`: Your model’s prediction (0 or 1)

## 🔍 Observations

- `keyword` and `location` columns contain missing data
- `text` is short-form and often informal, noisy, or includes hashtags, links, and emojis
- `target` is moderately imbalanced (~43% are real disaster tweets)

## 📌 Notes

- Preprocessing focuses on the `text` column
- The model only uses text input; `keyword` and `location` were not used in modeling
