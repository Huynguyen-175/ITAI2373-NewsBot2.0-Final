# 🤖 NewsBot Intelligence System 2.0

**ITAI 2373 — Natural Language Processing | Final Project | HCC Spring 2026**  
**Student:** Huy Nguyen &nbsp;|&nbsp; **Group:** Solo &nbsp;|&nbsp; **Built on:** NewsBot 1.0 (Midterm)

---

## Overview

NewsBot 2.0 is an end-to-end intelligent news analysis system built on top of the NewsBot 1.0 midterm foundation. It extends the original LinearSVC classifier and spaCy/VADER pipeline with four advanced NLP modules covering topic modeling, extractive summarization, multilingual analysis, and a conversational interface.

The system is trained on the BBC News dataset (~2,225 articles across 5 categories) and achieves **97% classification accuracy** with support for **12 languages**.

---

## Modules

| Module | Name | Capabilities |
|--------|------|-------------|
| **A** | Advanced Content Analysis | LDA topic modeling (10 topics), NMF topic modeling (8 topics), enhanced text preprocessing |
| **B** | Language Understanding | TF-IDF extractive summarization, semantic search with cosine similarity, category filtering |
| **C** | Multilingual Intelligence | Automatic language detection (12 languages), Google Translate integration, cross-lingual pipeline |
| **D** | Conversational Interface | 9-intent classifier (SEARCH, SUMMARIZE, SENTIMENT, CLASSIFY, TRANSLATE, TOPICS, ENTITIES, STATS, HELP), natural language query routing |

---

## Repository Structure

```
NewsBot2_HuyNguyen.ipynb          ← Main notebook (run this)
README.md                         ← This file
FP_TechnicalDoc_...pdf            ← Full technical documentation
FP_ExecutiveSummary_...pdf        ← Executive summary & ROI analysis
FP_Presentation_...pptx           ← 12-slide presentation deck
FP_ReflectiveJournal_...pdf       ← Individual reflective journal
```

---

## Quick Start

### Option 1 — Google Colab (Recommended)

1. Open `NewsBot2_HuyNguyen.ipynb` in [Google Colab](https://colab.research.google.com)
2. Run **Cell 1** to install all dependencies (takes ~2–3 minutes)
3. Run all remaining cells in order (Runtime → Run all)

### Option 2 — Local Jupyter

```bash
# 1. Clone the repo
git clone https://github.com/Huynguyen-175/ITAI2373-NewsBot-Final
cd ITAI2373-NewsBot-Final

# 2. Install dependencies
pip install spacy scikit-learn nltk pandas numpy matplotlib seaborn \
            wordcloud datasets tqdm gensim langdetect deep-translator \
            sentence-transformers pyLDAvis scipy

# 3. Download spaCy model
python -m spacy download en_core_web_sm

# 4. Launch notebook
jupyter notebook NewsBot2_HuyNguyen.ipynb
```

---

## Dependencies

| Package | Purpose |
|---------|---------|
| `scikit-learn` | LinearSVC classifier, TF-IDF, NMF |
| `spacy` | Named entity recognition, POS tagging, syntax parsing |
| `nltk` | Tokenization, stopwords, VADER sentiment |
| `gensim` | LDA topic modeling |
| `langdetect` | Automatic language identification |
| `deep-translator` | Google Translate integration |
| `sentence-transformers` | Semantic embeddings |
| `pyLDAvis` | Interactive LDA visualization |
| `datasets` | BBC News corpus (HuggingFace `SetFit/bbc-news`) |
| `wordcloud`, `seaborn`, `matplotlib` | Visualization |

**Python version:** 3.8+ &nbsp;|&nbsp; **Tested on:** Google Colab (Python 3.10)

---

## Notebook Walkthrough

| Cell | Description |
|------|-------------|
| 1 | Install all packages |
| 2 | Core imports |
| 3 | Load BBC News dataset from HuggingFace |
| 4 | `EnhancedTextPreprocessor` — clean, tokenize, lemmatize (43% vocab reduction) |
| 5 | `TopicModeler` — LDA + NMF with 4-panel visualization |
| 6 | `IntelligentSummarizer` — TF-IDF scoring + positional bias heuristic |
| 7 | `SemanticSearchEngine` — cosine similarity search with category filter |
| 8 | `MultilingualAnalyzer` — language detection + translation pipeline |
| 9 | `IntentClassifier` + `ConversationalNewsBot` — full conversational interface |
| 10 | `NewsBotIntelligenceSystem2` — unified facade class |
| 11 | Live demo (Business, Tech, Sport test articles) |
| 12 | 9-panel evaluation dashboard |

---

## Performance

| Metric | Value |
|--------|-------|
| Classification accuracy | 97% |
| Dataset size | 2,225 articles |
| Categories | Business, Entertainment, Politics, Sport, Tech |
| Languages supported | 12 |
| Summarization compression | ~70% (3:1 ratio) |
| Topic coherence (LDA) | 0.42 |
| Intents handled | 9 |

---

## Example Usage

```python
# Initialize and train the system
bot = NewsBotIntelligenceSystem2()
bot.train()

# Analyze a single article
result = bot.analyze(article_text)
print(result)

# Use the conversational interface
bot_chat = ConversationalNewsBot(bot)
bot_chat.chat("summarize the latest tech articles")
bot_chat.chat("translate this article to Spanish")
bot_chat.chat("what are the top topics this week?")
```

---

## Known Limitations

- The BBC News corpus covers **2004–2005** — the classifier may underperform on modern topics (AI, crypto, social media)
- Language detection requires a **minimum of ~20 characters** for reliable identification
- Summarization is **extractive only** — sentences are selected, not generated
- Translation requires an **active internet connection** via Google Translate API

---

## NewsBot 1.0 → 2.0 Enhancements

| Feature | v1.0 (Midterm) | v2.0 (Final) |
|---------|---------------|-------------|
| Classification | ✅ LinearSVC 97% | ✅ Retained + enhanced preprocessing |
| Sentiment | ✅ VADER | ✅ Retained |
| NER | ✅ spaCy | ✅ Retained |
| Topic Modeling | ❌ | ✅ LDA + NMF |
| Summarization | ❌ | ✅ Extractive + positional bias |
| Semantic Search | ❌ | ✅ TF-IDF cosine similarity |
| Multilingual | ❌ | ✅ 12 languages |
| Conversational UI | ❌ | ✅ 9-intent classifier |

---

## Midterm Foundation

NewsBot 1.0 source: [github.com/Huynguyen-175/ITAI2373-NewsBot-Midterm](https://github.com/Huynguyen-175/ITAI2373-NewsBot-Midterm)

---

## Course Information

**Course:** ITAI 2373 — Natural Language Processing  
**Institution:** Houston Community College  
**Semester:** Spring 2026  
**Instructor:** *Anna Devarakonda*

---

*NewsBot Intelligence System 2.0 — Huy Nguyen — HCC Spring 2026*
