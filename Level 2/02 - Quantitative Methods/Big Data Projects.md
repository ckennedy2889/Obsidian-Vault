---
title: "CFA L2 - Big Data Projects"
subject: "Quantitative Methods"
tags: [CFA-L2, quantitative-methods, big-data, NLP, feature-engineering, data-wrangling, alternative-data]
aliases: ["Module 7", "Alternative Data", "NLP Finance", "Data Pipeline", "Text Analysis"]
---

# Module 7 — Big Data Projects

## The Data Explosion in Finance

Not long ago, a portfolio manager's data universe was straightforward: quarterly earnings reports, price history, and maybe some macroeconomic indicators. The edge came from being smarter about the same information everyone else had.

Today, that world barely exists. Satellites photograph every Walmart parking lot every day and count cars in real time. Natural language models parse 10,000 earnings call transcripts per quarter, scoring the emotional tone of every sentence. Credit card transaction records reveal exactly what millions of consumers are spending money on — weeks before a company reports its sales.

This is **[[Big Data]]** (also called alternative data in investment contexts), and learning to extract signal from it — while filtering out the noise — is one of the most valuable skills in modern quantitative finance.

---

## The 3 (or 4) Vs of Big Data

Big Data is defined not just by its size but by a cluster of characteristics:

### Volume: The Scale Problem

```
Scale of Data:
  1 KB   = This text file
  1 MB   = A short novel
  1 GB   = ~250,000 songs
  1 TB   = 500 hours of video
  1 PB   = 500 billion pages of text
  1 EB   = 1,000 PB

Modern firms generate petabytes per day.
```

The sheer volume means traditional spreadsheet tools fail completely. Big data requires distributed computing infrastructure — storing and processing data across thousands of machines simultaneously.

**Finance context:** A single day of NYSE trade data contains billions of transactions. A quant firm tracking satellite imagery of 10,000 retail locations globally generates terabytes daily.

### Variety: Structured vs. Unstructured

```
STRUCTURED DATA                    UNSTRUCTURED DATA
─────────────────────────────────────────────────────
Spreadsheets, databases            Text (emails, transcripts,
Financial ratios                   tweets, analyst reports)
Price histories                    Images (satellite photos,
Accounting data                    product photos)
Economic indicators                Audio (earnings calls)
                                   Video (surveillance, traffic)
Easy to process                    Requires NLP/computer vision
                                   to extract numbers
```

About 80% of the world's data is unstructured. Most of the alpha-generating signals in alternative data come from this harder-to-process category.

### Velocity: Real-Time vs. Batch

Some data must be analyzed as it arrives — **data in motion**. High-frequency trading systems must process millions of messages per second and make trading decisions in microseconds. News sentiment algorithms must parse a surprise earnings announcement and generate a trade signal before the market can fully price it.

Velocity separates simple historical analysis (batch processing) from real-time systems that require entirely different infrastructure.

### Veracity: The Reliability Problem

The fourth V — and arguably the most important for investment decisions.

**Veracity** = the trustworthiness and reliability of the data.

```
Sources of bad data in finance:
  ├── Social media: 10-15% of accounts may be bots
  ├── Web scraping: inconsistent formatting, missing values
  ├── Satellite data: cloud cover, resolution changes
  ├── Transcripts: OCR errors, speaker misidentification
  └── Historical databases: survivorship bias, restatements
```

A model trained on unreliable data learns to fit the noise. Investment decisions based on low-veracity data can be catastrophically wrong.

---

## The Data Preparation Pipeline

Before any machine learning model can run, the raw data must be cleaned, organized, and transformed. This pipeline is often called **data wrangling** and typically consumes 60–80% of a data scientist's time on any project.

```
RAW DATA
   │
   ▼ (Step 1: Data Collection)
INGESTION: Collect from sources (APIs, web scraping, vendors)
   │
   ▼ (Step 2: Data Cleansing)
CLEANING: Fix errors, handle missing values, remove duplicates
   │
   ▼ (Step 3: Data Wrangling / Preprocessing)
TRANSFORMATION: Reshape, aggregate, convert to usable format
   │
   ▼ (Step 4: Feature Engineering)
FEATURES: Create new variables that capture the signal
   │
   ▼
CLEAN DATASET → Ready for machine learning model
```

### Step 1 — Data Cleansing: The Quality Check

Raw financial data is almost never clean. Common problems and their fixes:

| Problem | Description | Fix |
|---------|-------------|-----|
| **Missing values (incompleteness)** | A company has no reported P/E for a year | Imputation (replace with mean/median) or flag as missing |
| **Duplicate entries** | Same transaction appears twice | Deduplication |
| **Invalid data** | Negative revenue, 500% return flagged as data point | Remove or investigate |
| **Outliers** | One extreme value that distorts statistics | Winsorize (cap at 99th percentile) or investigate |
| **Inconsistent formats** | Dates as "2024-01-15" in some rows, "Jan 2024" in others | Standardize format |

**Real-world example:** A credit database of 10,000 borrowers has 8% missing income values and 3% duplicate loan applications. Before training any model, these must be addressed — otherwise the model learns from a distorted picture of reality.

### Step 2 — Data Wrangling: Reshaping the Data

**Data wrangling (preprocessing)** transforms the data into a form the model can digest:

- **Extraction:** Deriving a new variable from existing ones — compute a borrower's age from their birth year, or compute revenue growth from two periods of revenue
- **Aggregation:** Combining multiple rows into summary statistics — average daily volume over 20 days, sum of monthly transactions per customer
- **Normalization/Scaling:** Some models (like SVM and neural networks) are sensitive to the scale of variables — a variable ranging 0–1 and one ranging 0–1,000,000 will be treated very differently. Standardizing (subtracting mean, dividing by standard deviation) puts all variables on equal footing

### Step 3 — Feature Engineering: The Art of Signal Extraction

**[[Feature engineering]]** is creating new, meaningful input variables ("features") from your raw data. It's where domain knowledge turns raw numbers into investable signals.

**Examples in finance:**

```
Raw variable: Stock price
     ↓ Feature engineering
Derived features:
  • 20-day momentum = (price today / price 20 days ago) - 1
  • 52-week high dummy = 1 if price > 52-week high (0 otherwise)
  • Volatility = 20-day rolling standard deviation of returns

Raw variable: Earnings call transcript
     ↓ NLP feature engineering
Derived features:
  • Positive word count
  • Management sentiment score (-1 to +1)
  • Frequency of uncertainty words ("may," "could," "uncertain")
```

**One-hot encoding** is a specific type of feature engineering for categorical variables — converting "Industry: Technology" into dummy variables (covered in [[Extensions of Multiple Regression]]).

---

## Text Data Analysis: NLP in Finance

Perhaps the most exciting frontier in financial big data is **[[Natural Language Processing (NLP)]]** — using machine learning to turn human language into numbers.

### Why Text Data Matters

Every quarter, executives hold earnings calls and speak thousands of words about their company's prospects. Analysts write thousands of research reports. CEOs send letters to shareholders. Before NLP, processing this information required armies of human readers. Today, algorithms do it in seconds.

The insight: **language carries information that numbers don't**. A CEO who says "We expect solid performance" is sending a different signal than one who says "We hope to manage through current headwinds."

### Step 1 — Tokenization: Breaking Language Apart

**Tokenization** is the first step: splitting a text into individual units (**tokens**), usually words.

```
Input: "Earnings declined sharply due to margin pressure."

After tokenization:
["Earnings", "declined", "sharply", "due", "to", "margin", "pressure"]

After preprocessing (lowercase, remove stop words like "to"):
["earnings", "declined", "sharply", "margin", "pressure"]
```

### Step 2 — Bag of Words (BOW): Counting

The **[[Bag of Words]]** model ignores word order and simply counts how often each word appears in a document. The result is a vector of word counts.

```
Document 1: "Revenue grew strongly. Outlook is positive."
Document 2: "Revenue declined. Costs increased. Outlook uncertain."

Vocabulary: [revenue, grew, strongly, outlook, positive, declined, costs, increased, uncertain]

BOW vectors:
Doc 1: [1, 1, 1, 1, 1, 0, 0, 0, 0]
Doc 2: [1, 0, 0, 1, 0, 1, 1, 1, 1]
         ↑                           ↑
    "revenue" appears in both      "uncertain" only in Doc 2
```

Simple but surprisingly effective for sentiment classification.

### Step 3 — TF-IDF: Finding the Meaningful Words

The problem with raw word counts: common words like "the," "company," "quarter" appear everywhere and carry no information. **TF-IDF (Term Frequency-Inverse Document Frequency)** weights words by their *specificity* — high score if the word appears often in *this* document but rarely across *all* documents:

$$\text{TF-IDF}(t, d) = \underbrace{\frac{\text{count of } t \text{ in } d}{\text{total words in } d}}_{\text{Term Frequency}} \times \underbrace{\log\frac{\text{total documents}}{\text{documents containing } t}}_{\text{Inverse Document Frequency}}$$

Words that are **frequent in one document but rare overall** = signature words with high TF-IDF scores.

**Finance example:** "Litigation" has high TF-IDF in a company's 10-K if it appears repeatedly while being rare across the full document corpus. That's a flag worth reading further.

### Sentiment Analysis in Finance

**Sentiment analysis** classifies text as positive, negative, or neutral:

```
Earnings call transcript → NLP model → Sentiment score

"We delivered exceptional results and remain confident in our 
long-term growth trajectory." → Score: +0.82 (strongly positive)

"Headwinds persist and we are cautious about near-term outlook." 
→ Score: -0.35 (mildly negative)
```

**Research finding:** Studies show that negative earnings call sentiment predicts stock underperformance in the following weeks, even after controlling for the headline numbers — the *tone* of management carries information beyond the quantitative results.

### Named Entity Recognition (NER)

**NER** automatically identifies and classifies entities in text:

```
"Apple CEO Tim Cook announced a new partnership with Samsung in Seoul."

Entities:
  Apple  → Organization
  Tim Cook → Person
  Samsung → Organization  
  Seoul → Location
```

Investment use: Automatically tracking which companies are mentioned together, which executives are being discussed, and which geographies are implicated in news stories — across thousands of articles simultaneously.

---

## The Model Training Pipeline

Once features are engineered, you enter the model training phase. This is an iterative process:

```
CLEAN DATASET
      │
      ▼
 ┌────────────┐
 │  SPLIT     │ Training (60%) / Validation (20%) / Test (20%)
 └────────────┘
      │
      ▼
 ┌────────────┐
 │  TRAIN     │ Fit model on training data
 └────────────┘
      │
      ▼
 ┌────────────────┐
 │  TUNE          │ Adjust hyperparameters using validation set
 │ (Hyperparams)  │ (penalty strength, number of trees, layers, etc.)
 └────────────────┘
      │
      ▼
 ┌────────────┐
 │  EVALUATE  │ Final performance check on test set (use ONCE)
 └────────────┘
      │
      ▼
 ┌────────────┐
 │  DEPLOY    │ Use model on new real-world data
 └────────────┘
      │
      ▼
 Monitor → Retrain when model degrades
```

### Train / Validation / Test Split

The **test set** is sacred — it represents the "real world" of future data the model has never seen. Never tune the model based on test set results (this is called "data snooping" or "test set contamination" and is a serious research integrity violation).

### K-Fold Cross-Validation

When data is limited, use **k-fold cross-validation** for more reliable performance estimates (covered in [[Machine Learning]]). Every data point gets evaluated exactly once as a validation observation, preventing [[Overfitting|overfitting]] to a single hold-out set.

### Model Selection

The "best" model depends on the objective:

| Objective | Preferred Approach |
|-----------|-------------------|
| Interpretability required (e.g., regulatory) | Logistic regression, CART |
| Raw predictive accuracy (large dataset) | Random Forest, Neural Network |
| Text/image data | Neural Network, SVM |
| High-dimensional data, variable selection | LASSO |
| Sentiment classification | Logistic regression, SVM, fine-tuned LLM |

---

## The Full Investment Research Pipeline: A Worked Example

**Goal:** Build a model to predict which S&P 500 companies will beat earnings estimates next quarter.

```
Step 1 — Data Collection
  ├── Quantitative: EPS surprise history, analyst forecast revisions, 
  │   short interest, insider buying, option flow
  └── Text: Earnings call transcripts (6 quarters back)

Step 2 — Cleaning
  ├── Missing EPS surprise data for 12 companies → impute with sector median
  └── 3 duplicate transcript rows → deduplicate

Step 3 — Feature Engineering
  ├── Quantitative: 
  │   • "Estimate revision momentum" = % change in analyst estimates (last 30 days)
  │   • "Surprise streak" = number of consecutive EPS beats
  │   • "Short interest ratio" = short shares / average daily volume
  └── Text:
       • Management confidence score from last earnings call (NLP)
       • Frequency of forward-looking positive language
       • Named entity count for new customer/partnership announcements

Step 4 — Model Training
  ├── Target: Beat estimate = 1, Miss = 0
  ├── Algorithm: Random Forest with cross-validation
  └── Evaluation: AUC = 0.71 on test set (better than 0.5 coin flip)

Step 5 — Portfolio Construction
  └── Overweight stocks with predicted probability > 0.65
      Underweight stocks with predicted probability < 0.35
```

---

## Data Ethics and Quality Controls

Working with alternative data raises important ethical and practical considerations:

| Issue | Description | Impact |
|-------|-------------|--------|
| **Survivorship bias** | Historical database only includes companies that survived | Model learns from a distorted sample, overestimates returns |
| **Look-ahead bias** | Using data in the past that wasn't actually available then | Model looks better than it will in real-time |
| **Veracity / fake data** | Social media bots, fabricated reviews | Model learns from noise |
| **Privacy concerns** | Credit card, location, email data | Regulatory and reputational risk |
| **Overfitting to backtest** | Tuning model until it "works" on historical data | No out-of-sample performance |

---

## Exam Traps

> [!danger] Common Mistakes
> - **Veracity = data reliability**, not just volume/variety/velocity — know all 4 Vs
> - **TF-IDF rewards rare words** — a word appearing everywhere has low IDF and low TF-IDF
> - **Feature engineering precedes modeling** — the model can only use what you give it; garbage in, garbage out
> - **Test set used ONCE** — evaluating on test set multiple times constitutes [[Data snooping|data snooping]]
> - **[[Survivorship bias|Survivorship bias]] overestimates returns** — models trained on surviving firms look better than real-world performance

---

## Related Concepts

- [[Machine Learning]] — the algorithms that run on these engineered datasets
- [[Extensions of Multiple Regression]] — dummy variables, one-hot encoding
- [[Logistic Regression]] — the classification algorithm [[Underlying|underlying]] many sentiment models
- [[NLP]] — natural language processing for text data
- [[Feature Engineering]] — transforming raw data into signals
- [[Overfitting]] — the central danger in big data model building
- [[Cross-Validation]] — honest model evaluation on unseen data
