# What Drives Developer Pay? Stack Overflow Developer Survey 2024

A data science project that explores what drives developer salaries around the world and builds a model that predicts whether a developer earns above the median salary. It follows the CRISP-DM process.

## Motivation

Anyone planning a tech career wants to know which choices actually affect pay. Using the 2024 Stack Overflow Developer Survey (65,437 responses), this project asks four questions:

1. How much does salary grow with years of professional experience?
2. Do remote developers earn more than hybrid or in-person developers?
3. How much does the country a developer lives in affect their pay?
4. Can we predict whether a developer earns above the median salary, and which factors matter most?

## Libraries used

- Python 3.10+
- pandas, numpy: data loading and cleaning
- matplotlib, seaborn: charts
- scikit-learn: preprocessing pipelines, Logistic Regression, Random Forest, evaluation metrics, permutation importance
- Jupyter Notebook

Install everything with:

```bash
pip install -r requirements.txt
```

## Files in this repository

| File | Description |
|---|---|
| `stackoverflow_salary_analysis.ipynb` | Main notebook with the full CRISP-DM analysis: exploration, cleaning, the three questions, model training, evaluation, and a prediction scenario. |
| `q1_experience.png` to `q4_importance.png` | Charts produced by the notebook and used in the blog post. |
| `cover_image.png` | Cover image for the blog post. |
| `blog_post.md` | Draft of the non-technical blog post. |
| `requirements.txt` | Python libraries needed to run the notebook. |
| `survey_results_public.zip` | The 2024 survey answers (65,437 responses). Zipped from 160 MB to 17 MB to fit GitHub's limit; the notebook reads it directly. |
| `survey_results_schema.csv` | The full question text behind each column name. |
| `.gitignore` | Stops large unzipped data files from being uploaded by mistake. |

## How to run

1. Clone or download this repository. The dataset is already included (`survey_results_public.zip` and `survey_results_schema.csv`).
2. Install the libraries: `pip install -r requirements.txt`
3. Open `stackoverflow_salary_analysis.ipynb` and run all cells from top to bottom.

The original data comes from https://survey.stackoverflow.co/ (2024, **Data (CSV)**).

## Summary of results

After cleaning, the analysis uses 15,787 professional developers employed full-time who reported a salary.

- **Experience:** median pay rises from about $36k (0 to 2 years) to $74k (6 to 10 years) and $109k (20+ years).
- **Remote work:** remote developers have the highest median salary ($82k), compared with hybrid ($71k) and in-person ($48k). The gap also appears within the same country, for example in the USA ($155k remote vs $112k in-person).
- **Location:** country is the strongest factor. The median US developer earns $149k, compared with $75k in Germany and $18k in India (in US dollars, not adjusted for cost of living).
- **Model:** Logistic Regression predicts above- or below-median pay with **83% accuracy, 85% precision, 80% recall and ROC AUC 0.90**, against a 50% baseline. A Random Forest performed almost identically. Country and years of experience are by far the most important features.

These findings are correlations, not proof of cause. Salaries are self-reported, and survey respondents are not a perfect random sample of all developers.

## Blog post
https://medium.com/@ralbusaidi3/where-you-live-matters-more-than-your-degree-what-16-000-developers-reveal-about-pay-a00468ed8161?sharedUserId=ralbusaidi3
## Acknowledgements

- Data: [Stack Overflow Annual Developer Survey 2024](https://survey.stackoverflow.co/2024/), licensed under the Open Database License (ODbL). Thanks to Stack Overflow and the 65,000+ developers who took part.
- This project was completed as part of a data science course.
