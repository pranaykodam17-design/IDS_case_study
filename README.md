# 🎮 Video Game Sales Analysis & Success-Category Prediction
### *Introduction to Data Science (IDS) Case Study*

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pranaykodam17-design/IDS_case_study/blob/main/Video_Game_Sales_Case_Study_Colab_LIME_Logistic.ipynb)
[![Language: R](https://img.shields.io/badge/Language-R-276DC3?logo=r)](https://www.r-project.org/)
[![Notebook: Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter)](https://jupyter.org/)
[![ML: Decision Tree & Logistic Regression](https://img.shields.io/badge/ML-Decision%20Tree%20%26%20Logistic%20Regression-success)](https://cran.r-project.org/web/packages/rpart/index.html)
[![XAI: LIME](https://img.shields.io/badge/XAI-LIME%20Explainability-blueviolet)](https://github.com/thomasp85/lime)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 📌 Project Overview

This repository contains the complete case study for **Introduction to Data Science (IDS)** analyzing historical video game sales across global markets. 

Using exploratory data analysis (EDA), data visualization, and machine learning in **R**, this project uncovers sales dynamics across genres, gaming platforms, publishers, release years, and geographic territories (North America, Europe, Japan, and Rest of World). It further establishes a predictive framework to classify commercial success into **High Sales** and **Low Sales** categories and applies **LIME (Local Interpretable Model-agnostic Explanations)** to explain individual model predictions.

---

## 🎯 Objectives

1. **Data Audit & Hygiene**: Inspect structure, missingness, schema validation, and duplicate row detection.
2. **Exploratory Analysis**: Examine global and regional sales distributions across:
   - **Genres** (Action, Sports, Shooter, Role-Playing, etc.)
   - **Platforms** (PS2, X360, PS3, Wii, DS, etc.)
   - **Publishers** (Nintendo, Electronic Arts, Activision, Sony, etc.)
   - **Temporal Trends** (Sales evolution from 1980 to 2020)
3. **Supervised Classification**:
   - Construct a binary target variable (**High Sales** vs. **Low Sales**) defined by the training-set median of global sales.
   - Prevent target leakage by strictly excluding regional and raw sales attributes from predictive feature sets.
   - Train and compare two baseline models: **Decision Tree (`rpart`)** and **Logistic Regression (`glm`)**.
4. **Evaluation & Verification**: Evaluate performance using confusion matrices, classification accuracy, precision, recall, and F1-score.
5. **Model Explainability (XAI)**: Employ **LIME** to generate local, human-interpretable explanations of individual game predictions.

---

## 📊 Dataset Description

The analysis is based on the classic **Video Game Sales** dataset:
- **Source**: Kaggle ([Video Game Sales Dataset](https://www.kaggle.com/datasets/anandshaw2001/video-game-sales))
- **File**: `vgsales.csv` (~16,598 records)

| Field | Type | Description |
|---|---|---|
| `Rank` | Integer | Ranking of overall sales |
| `Name` | Character | Name of the video game title |
| `Platform` | Categorical | Gaming platform/console (e.g., PS3, X360, Wii, PC) |
| `Year` | Numeric | Release year of the game |
| `Genre` | Categorical | Genre category of the game (e.g., Action, Sports, RPG) |
| `Publisher` | Categorical | Publishing entity/company |
| `NA_Sales` | Numeric | Sales in North America (millions of units) |
| `EU_Sales` | Numeric | Sales in Europe (millions of units) |
| `JP_Sales` | Numeric | Sales in Japan (millions of units) |
| `Other_Sales` | Numeric | Sales in the rest of the world (millions of units) |
| `Global_Sales` | Numeric | Total worldwide sales (millions of units) |

---

## 📂 Repository Structure

```text
IDS_case_study/
├── vgsales.csv                                                    # Complete benchmark dataset
├── Video_Game_Sales_Case_Study_Colab_LIME_Logistic.ipynb         # Interactive Google Colab / Jupyter notebook (R)
├── Video_Game_Sales_Case_Study.Rmd                               # Comprehensive R Markdown analytical report
├── Video_Game_Sales_Conclusion_Dataset_Links_Updated_Repo.docx   # Structured case study summary & reference documentation
├── IDS_Conclusion_and_Dataset_Links_Clickable.docx               # Academic project details and dataset citations
├── Video_Game_Sales_Analysis_Presentation.pptx                   # Executive presentation slide deck
├── Video_Game_Sales_Analysis_Presentation_Themed.pptx            # Themed presentation deck
├── Video_Game_Sales_Project_Review.pptx                          # Project review slides
├── Video_Game_Sales_Project_Review_Reference_Format.pptx         # Reference-format review deck
├── .gitignore                                                    # Standard Git ignore rules
└── README.md                                                     # Project documentation and guide
```

---

## 🚀 How to Run the Analysis

### Option 1: In Google Colab (Fastest & Zero Setup)
1. Click the badge: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pranaykodam17-design/IDS_case_study/blob/main/Video_Game_Sales_Case_Study_Colab_LIME_Logistic.ipynb)
2. In Google Colab, verify that the runtime is set to **R**.
3. Run the cells in order from top to bottom. The notebook will automatically find the bundled `vgsales.csv` or fetch it from the public mirror.
4. Generated charts, models, and LIME interpretation plots are saved in `video_game_sales_outputs/`.

### Option 2: In RStudio
1. Clone this repository:
   ```bash
   git clone https://github.com/pranaykodam17-design/IDS_case_study.git
   cd IDS_case_study
   ```
2. Open RStudio and set the working directory to this folder.
3. Install required R libraries (if not already installed):
   ```R
   install.packages(c("ggplot2", "rpart", "rpart.plot", "lime", "knitr", "rmarkdown"))
   ```
4. Open and Knit `Video_Game_Sales_Case_Study.Rmd` to generate the HTML report.

---

## 🔬 Methodology & Modeling

### 1. Data Cleaning & Preparation
- Filter out records with incomplete years or missing crucial predictors.
- Consolidate rare/low-frequency platforms and publishers into informative grouping tiers to prevent high cardinality issues.
- Calculate median threshold from training split to partition games into `High` vs. `Low` commercial sales.

### 2. Machine Learning Classifiers
- **Decision Tree (`rpart`)**: Non-linear, rule-based classification providing global transparency and visual decision paths.
- **Logistic Regression (`glm`)**: Probabilistic binary classification model estimating log-odds of high sales based on platform, genre, and release era.

### 3. Local Model Explainability (LIME)
- Explains specific individual predictions produced by the Logistic Regression classifier.
- Quantifies which features contributed positively or negatively to classifying a game as `High Sales`.

---

## 📄 Deliverables & Documents

- **Notebook**: [`Video_Game_Sales_Case_Study_Colab_LIME_Logistic.ipynb`](Video_Game_Sales_Case_Study_Colab_LIME_Logistic.ipynb)
- **R Markdown Report**: [`Video_Game_Sales_Case_Study.Rmd`](Video_Game_Sales_Case_Study.Rmd)
- **Executive Review Decks**:
  - `Video_Game_Sales_Analysis_Presentation.pptx`
  - `Video_Game_Sales_Project_Review.pptx`
- **Documentation**:
  - `Video_Game_Sales_Conclusion_Dataset_Links_Updated_Repo.docx`
  - `IDS_Conclusion_and_Dataset_Links_Clickable.docx`

---

## 👤 Author

- **Pranay Kodam** ([@pranaykodam17-design](https://github.com/pranaykodam17-design))
- Subject: **Introduction to Data Science (IDS)**
