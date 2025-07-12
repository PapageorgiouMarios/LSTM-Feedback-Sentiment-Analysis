# 📘 LSTM Feedback Sentiment Analysis
[![Accuracy](https://img.shields.io/badge/accuracy-87%25-brightgreen.svg)](#) [![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](#) [![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](#)

## 🔍 Overview
This project implements a **Long Short-Term Memory (LSTM)** neural network for sentiment analysis on users' reviews. By leveraging pre-trained GloVe embeddings and a custom tokenizer, the model produces a score which defines the feedback as:

1) Positive😄
2) Negative😠
3) Neutral😐
   
---

## 📊 Results
After many tests, it was concluded that the model reaches **87% accuracy**

## 🧠 What’s an LSTM?
An LSTM is a type of **Recurrent Neural Network (RNN)** specially designed to remember long-range dependencies in sequence data. It maintains a **cell state** and **hidden state** per timestep, dynamically controlled by:
- **Forget Gate** – Removes old irrelevant information.
- **Input Gate** – Decides which new information to add.
- **Output Gate** – Determines the output.

This makes it ideal for tasks where context matters over words.

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/598922d2-561e-4719-b059-855dfae3057a" />

## 📁 File Overview
The project was developed in a Google Colab Notebook using Google Drive mount. Inside Google Drive 3 files were added and 1 is produced:
### Input
- **a1_IMDB_Dataset.csv**: Dataset of reviews + sentiment labels

- **a2_glove.6B.100d.txt**: Pre-trained 100D GloVe embeddings. GloVe is an unsupervised learning algorithm for obtaining vector representations for words. This specific filke contains 6B tokens 400K vocab, uncased, with 100-dimensional vector

- **edited_tokenizer.json**: Custom tokenizer used as a word-to-index map. In other words, it turns new input into a proper integer sequence

### Output
- **lstm_model_<acc>.h5**: When running the notebook, the model is saved as a .h5 file in a Results folder.

## 🛠️ How the Model Works
1) **Load and Pre-process Data**: Before using data, we preprocess their content (turn to lower case, remove tags, stopwords etc.)
2) **Tokenize & Split**: Convert text to sequences and pad them
3) **Build Embedding Matrix**: Populate with GloVe vectors aligned to indexed words
4) **Create LSTM model**: Using Tensorflow Keras we set the proper parameters to make our LSTM model
5) **Decide sentiment based on final score**: It is important to note here that our model produces a final score from 0 to 10. It is up to us to determine which score represents the user's sentiment the best
<img width="438" height="179" alt="{D32738BA-00B9-4C2D-897F-BBB752533B7C}" src="https://github.com/user-attachments/assets/6802a853-3f3a-46c4-8d06-00f3fd86d7cd" />


# 📜 License
This project is licensed under the **MIT** License
