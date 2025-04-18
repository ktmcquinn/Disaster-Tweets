# NLP Disaster Tweet Classification

## Problem Description
This project aims to classify tweets as either related to a **real disaster (target = 1)** or not (target = 0). It uses natural language processing (NLP) to understand short, noisy social media text.

## Dataset Overview
- `train.csv`: 7,613 labeled tweets (includes `keyword`, `location`, `text`, `target`)
- `test.csv`: 3,263 tweets without labels
- `sample_submission.csv`: template for submission

### Missing Data
| Column    | Missing (Train) | Missing (Test) |
|-----------|------------------|----------------|
| keyword   | ~0.8%            | ~0.8%          |
| location  | ~33%             | ~34%           |

## Exploratory Data Analysis (EDA)

- Disaster tweets tend to be longer (~100 characters)
- Word clouds show disaster tweets contain terms like *fire*, *emergency*, *evacuation*
- Cleaned text using:
  - Lowercasing, removing punctuation, stopwords, and URLs

## Model Architecture

- **Embedding Layer** using pre-trained **GloVe 100d**
- **LSTM Layer** with 64 units
- **Dropout Layer** for regularization
- **Dense Layer** with sigmoid output for binary classification
- Loss: `binary_crossentropy`, Optimizer: `Adam`

##  Word Embeddings
We used GloVe, which maps words to dense vectors where similar words are close in vector space.

##  Results & Tuning

- Trained with 5 epochs, batch size 32
- Achieved strong validation accuracy (~80-85%)
- Hyperparameters tuned: LSTM units, dropout rate, embedding size

### Comparison:
| Model                 | Accuracy (Val) |
|-----------------------|----------------|
| TF-IDF + Logistic Reg | ~73%           |
| LSTM + GloVe          | ~84%           |

##  Test Prediction
Generated predictions on test set using the trained LSTM. Saved submission file in correct Kaggle format.

##  Conclusion

- LSTM + GloVe is effective for tweet classification
- Preprocessing and embeddings matter a lot
- Future: try Bidirectional LSTM, attention, or BERT-based models
