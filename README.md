# Twitter Location Prediction

A machine learning project that predicts a user's location based on the text content of their tweets. It combines natural language processing with classic classification algorithms through an intuitive desktop GUI.

---

## Overview

Social media text carries surprisingly strong geographic signals — regional slang, local topics, and language patterns all hint at where a tweet originates. This project leverages those signals to build a location classifier trained on real Twitter data.

The application walks through the full ML pipeline:

1. **Upload** a labeled tweet dataset
2. **Preprocess** the text using NLP techniques
3. **Train & evaluate** three machine learning classifiers
4. **Visualize** their accuracy side-by-side
5. **Predict** locations from new, unseen tweets

---

## Features

- Text cleaning with stopword removal, punctuation stripping, and lemmatization
- TF-IDF vectorization with unigrams and bigrams
- Three classifiers compared head-to-head:
  - Naive Bayes
  - Support Vector Machine (SVM)
  - Decision Tree
- Accuracy comparison bar chart via Matplotlib
- Simple, interactive Tkinter desktop interface
- Supports 14 location classes across multiple continents

**Supported Locations:** Arizona, Brazil, Brooklyn, Chennai, Florida, India, Indonesia, Kerala, Kirkwall, Pune, Sweden, United States, Mexico, UK
<img width="2048" height="2048" alt="SA" src="https://github.com/user-attachments/assets/a282faf7-2b8a-43ce-82a4-2ae8179338eb" />

---

## Project Structure

```
TwitterLocationPrediction/
├── TwitterLocationPrediction/
│   ├── Dataset/
│   │   ├── tweets.csv        # Training dataset
│   │   └── testData.csv      # Test dataset
│   ├── Main.py               # Main application (GUI + ML pipeline)
│   ├── run.bat               # Windows launcher script
│   └── SCREENS.docx          # Application screenshots
└── README.md
```

---

## Tech Stack

| Category | Libraries / Tools |
|---|---|
| Language | Python 3 |
| GUI | Tkinter |
| NLP | NLTK (stopwords, WordNetLemmatizer) |
| ML | scikit-learn (TF-IDF, SVM, Naive Bayes, Decision Tree) |
| Data | Pandas, NumPy |
| Visualization | Matplotlib |

---

## Getting Started

### Prerequisites

Make sure you have Python 3 installed, then install the required packages:

```bash
pip install pandas numpy scikit-learn nltk matplotlib
```

Download the necessary NLTK data:

```python
import nltk
nltk.download('stopwords')
nltk.download('wordnet')
```

### Running the Application

**Option 1 — Windows (easiest):**

```
Double-click run.bat
```

**Option 2 — Command line:**

```bash
cd TwitterLocationPrediction
python Main.py
```

### Using the App

1. Click **Upload Tweets Dataset** and select `tweets.csv`
2. Click **Preprocess Dataset** to clean and vectorize the text
3. Click **Run Machine Learning Algorithm** to train all three models and see their accuracy scores
4. Click **Accuracy Comparison Graph** to view a visual comparison
5. Click **Predict Location from Test Tweets** and select `testData.csv` to run predictions

---

## Dataset Format

The training dataset (`tweets.csv`) should contain at minimum these two columns:

| Column | Description |
|---|---|
| `text` | The raw tweet content |
| `location` | The user's location label |

The test dataset (`testData.csv`) should contain a single `text` column with tweets you want to classify.

---

## How It Works

1. **Text Preprocessing** — Each tweet is lowercased, stripped of punctuation and stopwords, and lemmatized to its root form.
2. **Feature Extraction** — A TF-IDF vectorizer converts the cleaned text into numerical feature vectors using both unigrams and bigrams.
3. **Classification** — Three models are trained on an 80/20 train-test split. Accuracy is computed for each and displayed in the UI.
4. **Prediction** — New tweets go through the same preprocessing pipeline before being classified by the best-performing model (Decision Tree by default).

## Applications

This project has practical value across several real-world domains:

| Use Case | Description |
|---|---|
| **Geographic Profiling** | Identify the likely origin of anonymous or pseudonymous accounts based on their writing patterns |
| **Targeted Advertising** | Help marketers serve region-specific content and ads based on inferred user location |
| **Regional Trend Analysis** | Understand how topics, sentiments, and language vary across geographic regions |
| **Disaster Response** | Quickly map where distress-related tweets are coming from during emergencies |
| **Content Localization** | Automatically route users to region-appropriate content or language settings |
| **Research & Analytics** | Study linguistic patterns and cultural differences across countries and cities |

---

## License

This project is open source and available under the [MIT License](LICENSE).
