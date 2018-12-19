# AWS Sentiment Analysis

This compares two models for determining the sentiment of Amazon product reviews

Problem: Given the text and title of a product review, how likely are people to judge it a good or bad review?

# Project Plan

## Dataset

We plan to use the Amazon polarity dataset

### Dataset format

TBD

### Dataset preprocessing

TBD

## Modeling strategies

### 1. Blazingtext

1. Generate word embeddings
2. Train a softmax classifier on the embedded sentences

### 2. Character-level RNN

1. Use an RNN that operates on sequences of characters
  - Input layer
  - Single hidden layer 
  - Softmax analysis
  - Output layer

### 2. Character-level embeddings
1. Generate character embeddings
2. Train a softmax classifier on the embeddings
