# Mind in the Feed
### Topic Modeling Reddit Mental Health Communities

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sharyali05/Reddit-Text-Analysis/blob/main/notebook.ipynb)

As a student interested in the field of Psychology and having studied it in undergrad, I have always been interested in the many Mental Health Communities that exist in Reddit. A text analysis project applying **LDA** and **BERTopic** across two chunking strategies to Reddit mental health posts, with supervised classification and comprehensive evaluation.

---

## Dataset

**Source:** [`solomonk/reddit_mental_health_posts`](https://huggingface.co/datasets/solomonk/reddit_mental_health_posts) via HuggingFace  
**Size:** 151k posts total, subsampled to **2,000 per subreddit** (10,000 total)  
**Subreddits:** r/depression · r/anxiety · r/ocd · r/ptsd · r/adhd  
**Label:** Subreddit name (free, naturalistic classification target)

---

## Methods

| Config | Model | Chunking Strategy | C_v Coherence |
|--------|-------|-------------------|---------------|
| A1 | LDA | Post-as-document | *run notebook* |
| A2 | LDA | Sliding window 100w / 25w step | *run notebook* |
| B1 | BERTopic | Post-as-document | *run notebook* |
| B2 | BERTopic | Sliding window 100w / 25w step | *run notebook* |

**Classifier:** Logistic Regression + Linear SVM on TF-IDF features  
**Evaluation:** C_v coherence, chi-square topic–label alignment, qualitative inspection

---

## Project Structure

```
├── index.html      ← GitHub Pages project report
├── notebook.ipynb  ← Full runnable code (Google Colab)
└── README.md
```

---

## Running the Notebook

Open directly in Colab with the badge above — no local setup needed. The first cell installs all dependencies automatically.

To run locally:
```bash
pip install datasets gensim bertopic sentence-transformers umap-learn hdbscan pyLDAvis spacy
python -m spacy download en_core_web_sm
jupyter notebook notebook.ipynb
```

---

## View the Report

Enable GitHub Pages: **Settings → Pages → main branch / root**  
Then visit: `https://sharyali05.github.io/Reddit-Text-Analysis`

---

## References

- Grootendorst, M. (2022). BERTopic: Neural topic modeling with a class-based TF-IDF procedure. *arXiv*.
- Blei, D. M., Ng, A. Y., & Jordan, M. I. (2003). Latent Dirichlet Allocation. *JMLR*.
- Low, D. M. et al. (2020). Natural Language Processing Reveals Vulnerable Mental Health Support Groups on Reddit During COVID-19. *JMIR*.
