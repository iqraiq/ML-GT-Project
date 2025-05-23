# Document Classification Using Word Co-occurrence Graphs

## Project Overview

This project focuses on **document classification** using **word co-occurrence graphs**, integrating **web scraping**, **graph construction**, and **machine learning** techniques to classify textual content efficiently.

---

## 🔍 Problem Statement

To classify documents based on their content using a graph-based representation that captures the semantic structure of texts, leveraging Maximum Common Subgraph (MCS) similarity and the K-Nearest Neighbors (KNN) algorithm.

---

## 🛠 Methodology

### 1. Web Scraping
- Read URLs from `url_links.txt`.
- Fetch and parse HTML using `requests` and `BeautifulSoup`.
- Extract `<p>` tag content.
- Combine and store text data into individual `.txt` files.

### 2. Data Cleaning & Preprocessing
- Tokenization, case normalization.
- Removal of punctuation, digits, and stopwords (using NLTK).
- Lemmatization via `WordNetLemmatizer`.
- Truncate each document to first 500 words.

### 3. Graph Construction
- Use `networkx.DiGraph()` to build word co-occurrence graphs.
- Nodes: tokens (words).
- Edges: adjacency relationships between tokens (with weights).

### 4. Maximum Common Subgraph (MCS)
- Compare each test graph with training graphs.
- Measure similarity using number of common edges.
- Extract largest connected component as MCS.

### 5. Classification using KNN
- K = 5
- Use MCS-based similarity to determine closest graphs.
- Assign labels based on majority voting.
- Evaluate using confusion matrix.

---

## 📊 Results

| Metric     | Score         |
|------------|---------------|
| Precision  | 91.67%        |
| Recall     | 88.89%        |
| F1-Score   | 88.57%        |
| Accuracy   | 88.89%        |

---

## 🚀 Future Work
- **Parameter Optimization**: Tune KNN hyperparameters.
- **Graph Enhancement**: Use advanced graph algorithms and word importance-based weighting.
- **Deep Learning Integration**: Add CNNs, RNNs, or graph neural networks.
- **Multi-modal Classification**: Incorporate additional data types like images or audio.

---

## 📂 Folder Structure

```
project/
│
├── url_links.txt               # List of URLs to scrape
├── scraped_data/               # Folder for extracted raw text
├── cleaned_data/               # Cleaned and preprocessed data
├── graphs/                     # Word co-occurrence graphs
├── results/                    # Evaluation metrics and outputs
└── README.md                   # Project documentation
```
