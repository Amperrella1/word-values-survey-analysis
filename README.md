# Exploring cross-country attitudes with the World Values Survey

Can a single dimension summarize how survey respondents differ in their attitudes toward family, work, religion, trust, and democracy? This project uses Python and World Values Survey Wave 7 responses to explore that question. It examines patterns among individual respondents, then compares average scores across country samples.

## Analysis

- **Principal component analysis (PCA)** measures how much variation a smaller set of components captures. A parallel analysis compares the observed eigenvalues with those from 500 independently shuffled datasets.
- **Factor analysis** examines which survey items tend to move together. Varimax and promax rotations show how the interpretation changes when factors are allowed to correlate.
- **Independent component analysis (ICA)** provides a second way to summarize the responses. Country-level heatmaps show how the resulting profiles compare with those from factor analysis.

## Findings

In the complete-case analysis of 14 survey and demographic variables, the first principal component captured **15.0%** of the variation across respondents. The first six together captured **59.1%**, and all six exceeded the 95th-percentile benchmark from the parallel analysis. A single score would therefore discard much of the variation in these responses.

Sample coverage also matters. The source extract contains **19,364 respondents from 10 countries**. Political orientation was not asked in China, so requiring complete responses on all 14 variables leaves **11,919 respondents from nine countries**. The country profiles summarize the respondents included in each analysis. Demographic differences and the mix of binary, ordinal, and continuous measures also affect their interpretation.

## Data and reproducibility

The analysis uses the World Values Survey Wave 7 country-pooled datafile, version 6.0 (2017–2022). The course extract is restricted from public redistribution. To run the notebook, place an authorized copy of the 16-column extract named `wvs_data.csv` beside it and run the cells in order. The notebook recodes negative survey response codes as missing and standardizes the analysis variables.

The Python workflow uses pandas, NumPy, SciPy, scikit-learn, factor_analyzer, Pingouin, Matplotlib, and seaborn.

**Data citation:** Haerpfer, C. et al. (eds.). 2022. *World Values Survey: Round Seven – Country-Pooled Datafile Version 6.0*. JD Systems Institute & WVSA Secretariat. [Dataset DOI](https://doi.org/10.14281/18241.24) · [Wave 7 documentation](https://www.worldvaluessurvey.org/WVSDocumentationWV7.jsp)
