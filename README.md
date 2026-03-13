## World Happiness Report — Region Classification

A Jupyter notebook that uses the **World Happiness Report (WHR) 2018** dataset to explore supervised machine learning classification with scikit-learn.

### Overview

The project trains classifiers to predict a country's **world region** based on numerical happiness indicators (GDP, social support, life expectancy, freedom, generosity, corruption, positive/negative affect). It compares the performance of two different algorithms across many random train/test splits.

### Data

- **Source:** `WHR2018Chapter2OnlineData.xls` (sheets: `Table2.1` and `SupportingFactors`)
- **Features (9):** Happiness, LogGDP, Support, Life, Freedom, Generosity, Corruption, Positive, Negative
- **Target:** World region (10 categories, e.g. Western Europe, South Asia, Sub-Saharan Africa)
- **Samples:** 152 countries (mean values averaged across available years)

### Pipeline

1. Load and merge WHR data with region labels
2. Standardize features using `StandardScaler`
3. Split into train/test sets with `train_test_split`
4. Train and evaluate two classifiers:
   - **Support Vector Classifier** (`svm.SVC`) — ~71% accuracy
   - **Decision Tree** (`tree.DecisionTreeClassifier`) — ~65–70% accuracy
5. Run 1,000 random splits to compare classifier distributions via overlapping histograms

### Requirements

```
pandas, numpy, matplotlib, scikit-learn, openpyxl
```

### Key Finding

The SVC classifier generally outperforms the Decision Tree across random splits, though neither achieves high accuracy — some countries are genuine regional outliers based on their happiness indicators.
