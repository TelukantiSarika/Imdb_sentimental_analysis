# movie review prediction using Machine Learning and NLP (sentiment analysis)
- This project is for prediction whether the text is positive, negative or neutral.
- Dataset available [here](https://drive.google.com/file/d/1-Vs-z4bqtnqIAPgEtTdB_UXO0USNq5K2/view?usp=sharing)
## **What is sentiment analysis?**
Sentiment analysis (or opinion mining) is a natural language processing technique used to determine whether data is positive, negative or neutral.


## **Data Description**:

```
_______________________________________________________________________
                                              review sentiment
0  One of the other reviewers has mentioned that ...  positive
1  A wonderful little production. <br /><br />The...  positive
2  I thought this was a wonderful way to spend ti...  positive
49997  I am a Catholic taught in parochial elementary...  negative
49998  I'm going to have to disagree with the previou...  negative
49999  No one expects the Star Trek movies to be high...  negative
```

```
Data columns (total 2 columns):
 #   Column     Non-Null Count  Dtype 
---  ------     --------------  ----- 
 0   review     50000 non-null  object
 1   sentiment  50000 non-null  object
dtypes: object(2)
memory usage: 781.4+ KB
```
## **Data preprocessing**:

In this section I used different operations to optaine cleaned text:
- **Remove panctuation:** '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
- **Tokenization:** to Tokenize words
- **Remove stopwords:** such that ['i', 'me', 'my', 'myself', 'we', 'our', ... , 'shouldn', "shouldn't", 'wasn', "wasn't", 'weren', "weren't", 'won', "won't", 'wouldn']
- **Lemetizing:** to Lemetize words



## **Models Implementation**:

```
Using : TfidfVectorizer() to deal with text and extract features
from sklearn.feature_extraction.text
```

### Models:

**Naive bayes**

- MNB_clf = MultinomialNB() 
- with accurecy = 0.86

**LogisticRegression**

- logreg = LogisticRegression(random_state=42)
- with accurecy = 0.90


## **Validation**:

- Using k-fold cross validation:

```
skfold = StratifiedKFold(n_splits=10, random_state=100)
results_model = cross_val_score(model, train_vectors, y_train, cv=skfold)
```
