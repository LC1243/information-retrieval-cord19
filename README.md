# Information Retrieval on CORD-19

An information retrieval system for scientific literature, developed as a
group project for **Information Processing and Retrieval (PRI)** at IST, during the 2024/2025 academic year.

The project explores document indexing, information retrieval models,
unsupervised clustering, and graph-based ranking using the CORD-19 collection
of COVID-19 scientific literature.

## Project Overview

The goal was to develop and evaluate an information retrieval system capable
of ranking scientific articles according to their relevance to a given query.

The project was developed in two deliveries, progressively extending the
retrieval system with additional text analysis and ranking techniques.

### Delivery 1 — Information Retrieval

The first delivery focused on building and evaluating the core retrieval
system.

Key components:

- **Text preprocessing:** tokenization, normalization, stopword removal,
  lemmatization, and stemming.
- **Inverted indexing:** efficient indexing of document terms and their
  frequencies.
- **Boolean retrieval:** document retrieval based on query terms.
- **TF-IDF:** vector-space retrieval with different term-weighting schemes.
- **BM25:** probabilistic ranking with parameter tuning.
- **Reciprocal Rank Fusion (RRF):** combination of rankings produced by
  different retrieval models.
- **Evaluation:** quantitative comparison of retrieval effectiveness using
  MAP, nDCG, nDCG@10, and P@10.

The experiments investigated how preprocessing choices and retrieval models
affect ranking quality and retrieval performance.

**Artifacts:**

- [Jupyter Notebook](p1/G09_notebook.ipynb)
- [Project Report](p1/G09_report.pdf)

### Delivery 2 — Clustering and Graph-Based Ranking

The second delivery extended the project by investigating unsupervised
document organisation and graph-based ranking.

Key components:

- **Document clustering:** TF-IDF representations and K-Means clustering
  to investigate the thematic organisation of the document collection.
- **Query clustering:** analysis of similarities and relationships between
  information needs.
- **Cluster evaluation:** silhouette coefficients to assess cluster cohesion
  and separation.
- **Document similarity graphs:** graph construction using cosine similarity
  between TF-IDF document representations.
- **PageRank:** graph-based document ranking using relationships between
  candidate documents.
- **Weighted PageRank:** incorporation of BM25 scores as prior information.
- **Hybrid ranking:** combination of BM25 and weighted PageRank scores.
- **Experimental evaluation:** comparison of ranking effectiveness and
  computational cost across different approaches.

The graph-based methods were evaluated against the BM25 baseline to
investigate whether document relationships could improve retrieval quality.

**Artifacts:**

- [Part 1 Notebook](p2/G09_P1_notebook.ipynb)
- [Part 2 Notebook](p2/G09_P2_notebook.ipynb)
- [Project Report](p2/G09_report.pdf)

## Results and Findings

The experiments highlighted several trade-offs between retrieval
effectiveness and computational cost.

- **BM25** provided a strong baseline among the evaluated retrieval models.
- **Reciprocal Rank Fusion** improved some overall ranking metrics compared
  with the individual TF-IDF and BM25 rankings, although the best results
  depended on the evaluation metric.
- **Clustering** revealed thematic structure in the document collection,
  although many clusters exhibited limited cohesion or separation.
- **Unweighted PageRank** underperformed BM25 in the evaluated setting.
- **Weighted PageRank and hybrid ranking** produced results comparable to
  BM25, but required additional computation.

These findings illustrate the importance of evaluating information retrieval
methods empirically rather than assuming that more complex models necessarily
produce better results.

For detailed metrics, experimental configurations, and analysis, see the
project reports.

## Dataset

The project uses **CORD-19**, a collection of scientific literature related
to COVID-19, and the TREC-COVID evaluation collection.

The retrieval task uses a set of information needs (queries) and associated
relevance judgments to evaluate the quality of the ranked results.

The first delivery primarily uses document metadata, including titles and
abstracts. The second delivery investigates clustering and graph-based
ranking over document representations.

Dataset information:

- [CORD-19 and TREC-COVID on ir_datasets](https://ir-datasets.com/cord19.html)

## Technologies

- **Python**
- **Jupyter Notebook**
- **scikit-learn**
- **NLTK**
- **NetworkX**

## Repository Structure

```text
.
├── LICENSE
├── p1/
│   ├── G09_notebook.ipynb
│   └── G09_report.pdf
├── p2/
│   ├── G09_P1_notebook.ipynb
│   ├── G09_P2_notebook.ipynb
│   └── G09_report.pdf
├── ProjectPRI_2024_25_v0.1.pdf
└── README.md
