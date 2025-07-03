# Amazon Food Reviews: Sentiment & Feature Analysis

## Overview
This project analyzes Amazon Fine Food Reviews using both traditional NLP and generative AI (GPT-4) techniques. The workflow includes data preprocessing, sentiment analysis, feature (aspect) extraction, and visualization of insights. The goal is to compare the effectiveness of classical models (VADER, TextBlob, SpaCy) with GPT-4 for sentiment and aspect extraction.

## Dataset
- **Source:** [Amazon Fine Food Reviews (Kaggle)](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
- **Size:** 568,454 reviews, 10 columns
- **Fields:** ProductId, UserId, ProfileName, Helpfulness, Score, Time, Summary, Text, etc.

## Workflow
### 1. Data Loading & Preprocessing
- Downloaded via `kagglehub`.
- Cleaned text (lowercased, removed punctuation/numbers/stopwords).
- Removed rows with missing summaries.

### 2. Sentiment Labeling
- Mapped ratings to sentiment: 1-2 = Negative, 3 = Neutral, 4-5 = Positive.

### 3. Sentiment Analysis Approaches
- **VADER:** Rule-based sentiment analysis.
- **TextBlob:** Polarity-based sentiment analysis.
- **GPT-4:** Used OpenAI API to classify 1,000 sampled reviews.

### 4. Feature (Aspect) Extraction
- **GPT-4:** Extracted top 3 aspects per review using prompt engineering.
- **SpaCy:** Extracted noun phrases as baseline aspects.

### 5. Evaluation & Visualization
- Compared model performance (precision, recall, F1-score).
- Visualized confusion matrices, sentiment distributions, and word clouds.
- Analyzed most frequent product aspects.

## Results
- **GPT-4 outperformed VADER and TextBlob** in sentiment accuracy (90% vs. 79%/69% on sample).
- **Top aspects**: taste, price, flavor, packaging, texture, availability, etc.
- Visualizations: Sentiment pie charts, word clouds, aspect frequency bar plots.

## How to Run
1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
2. **Download NLTK data:**
   - The notebook will auto-download required NLTK corpora (stopwords, vader_lexicon).
3. **Set up OpenAI API key:**
   - Replace `openai.api_key` in the notebook with your key for GPT-4 features.
4. **Run the notebook:**
   - Open `Amazon_Food_Reviews.ipynb` in Jupyter and execute cells sequentially.

## Dependencies
See `requirements.txt` for full list. Key packages:
- pandas, numpy, matplotlib, seaborn
- scikit-learn, nltk, textblob, spacy
- openai, kagglehub, wordcloud

## File Structure
- `Amazon_Food_Reviews.ipynb` — Main analysis notebook
- `requirements.txt` — Python dependencies
- `README.md` — Project documentation

## Acknowledgments
- [Kaggle: Amazon Fine Food Reviews](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
- [OpenAI GPT-4](https://platform.openai.com/)
- [SpaCy](https://spacy.io/), [NLTK](https://www.nltk.org/), [TextBlob](https://textblob.readthedocs.io/en/dev/)