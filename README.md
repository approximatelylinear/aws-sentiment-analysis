# AWS Sentiment Analysis

This compares two models for determining the sentiment of Amazon product reviews

Problem: Given the text and title of a product review, how likely are people to judge it a good or bad review?

Goals: 

1. Learn about training and deploying models with SageMaker: Compare two or three models and allow users to interact in a simple web-interface. 
2. Learn about AWS tools: Explore Glue or SageMaker airflow for ETL.

# Project Plan

## Dataset

We plan to use the Amazon polarity dataset

### Dataset format

The dataset consists of multiple lines. Each line is a product review and contains a comma-separated list with: 
1. The sentiment ("1": Negative or "2": Positive)
2. The title
3. The content of the review

### Dataset preprocessing

1. Translate the classes into integers and create a mapping back to the class labels. 
2. Concatenate the title and the content and tokenize into characters and words. 
3. Create training, validation, and test datasets.

## Modeling strategies

### 1. Blazingtext

1. Generate word embeddings
2. Train a softmax classifier on the embedded sentences
3. Output class softmax "probabilities"

Potential drawback: Blazingtext does not (afawk) represent sequences. 

### 2. Character-level RNN

1. Use an RNN that operates on sequences of characters
  - Input layer
  - Single hidden layer 
  - Softmax analysis
  - Output layer
2. Output class softmax "probabilities"

Some initial code can be found here: https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html

### 2. Character-level embeddings
1. Generate character embeddings
2. Train a softmax classifier on the embeddings

Some initial code: https://github.com/zhangxiangxiao/Crepe


## Application delivery

Webpage that allows users to type text into a form and see the estimated sentiment.

# Resources

Jupyter notebook: https://mj-notebook-2.notebook.us-east-1.sagemaker.aws/notebooks/blazingtext_word2vec_subwords_text8_2018-12-19/Sentiment%20Analysis.ipynb

