# Netflix Movies and TV Shows
## Exploratory Data Analysis (EDA) Report

**Project:** CodeAlpha Internship — Task 2  
**Analysis:** Exploratory Data Analysis  
**Dataset:** Netflix Movies and TV Shows  
**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn  
**Notebook:** `notebooks/netflix_eda.ipynb`

---

## 1. Executive Summary

This project explores the Netflix Movies and TV Shows dataset to identify patterns, trends, and data quality issues.

The dataset contains 8,807 titles and 12 columns. The analysis examines content distribution, country-wise title entries, release-year trends, content ratings, and movie durations.

Data cleaning techniques, statistical summaries, and visualizations were used to understand the dataset and communicate the findings.

## 2. Project Objectives

The main objectives are:

- Understand the structure and characteristics of the dataset.
- Analyze the distribution of Movies and TV Shows.
- Identify countries with the highest number of title entries.
- Explore release-year trends.
- Examine content rating distributions.
- Analyze movie duration statistics.
- Detect and correct data quality issues.
- Communicate insights through visualizations and statistical summaries.

## 3. Dataset Description

The Netflix dataset contains information about movies and television shows.

**Dataset dimensions:**
- Total records: 8,807
- Total columns: 12

**Important columns:**

| Column | Description |
|---|---|
| show_id | Unique title identifier |
| type | Movie or TV Show |
| title | Title name |
| director | Director name |
| cast | Cast information |
| country | Country or countries associated with the title |
| date_added | Date added to Netflix |
| release_year | Original release year |
| rating | Content rating |
| duration | Movie duration or TV Show seasons |
| listed_in | Content categories |
| description | Title description |

## 4. Data Cleaning and Preparation

The dataset was inspected using Pandas functions such as `info()`, `describe()`, `isnull().sum()`, and `duplicated()`.

### Missing values identified

| Column | Missing values | Percentage |
|---|---:|---:|
| director | 2,634 | 29.91% |
| cast | 825 | 9.37% |
| country | 831 | 9.44% |
| date_added | 10 | 0.11% |
| rating | 4 | 0.05% |
| duration | 3 | 0.03% |

### Cleaning operations

- Created a separate cleaned dataset using a copy of the original data.
- Replaced missing director, cast, country, and rating values with `Unknown`.
- Investigated three inconsistent rating entries.
- Found that `74 min`, `84 min`, and `66 min` were incorrectly stored in the rating column.
- Moved these values into the duration column and corrected their ratings to `Unknown`.
- Retained the 10 missing `date_added` values rather than inventing dates.

The cleaned dataset retained all 8,807 records.

## 5. Exploratory Data Analysis

### 5.1 Movies vs TV Shows

| Content type | Number of titles | Percentage |
|---|---:|---:|
| Movies | 6,131 | 69.62% |
| TV Shows | 2,676 | 30.38% |
| Total | 8,807 | 100% |

**Finding:** Movies represent the majority of titles, accounting for approximately 69.62% of the dataset. The number of Movies is approximately 2.29 times the number of TV Shows.

### 5.2 Country-wise Content Distribution

Top 10 countries by title-country entries:

| Country | Count |
|---|---:|
| United States | 3,690 |
| India | 1,046 |
| United Kingdom | 806 |
| Canada | 445 |
| France | 393 |
| Japan | 318 |
| Spain | 232 |
| South Korea | 231 |
| Germany | 226 |
| Mexico | 169 |

**Finding:** The United States has the highest number of title-country entries, followed by India and the United Kingdom.

**Note:** A title associated with multiple countries is counted once for each country. These values do not represent mutually exclusive country totals.

### 5.3 Release-Year Analysis

The dataset contains titles released between 1925 and 2021.

Important statistical summaries:

| Statistic | Value |
|---|---:|
| Mean release year | 2014.18 |
| Median release year | 2017 |
| Standard deviation | 8.82 |
| Minimum release year | 1925 |
| 25th percentile | 2013 |
| 75th percentile | 2019 |
| Maximum release year | 2021 |

The release-year analysis from 2007 onward showed the following important results:

- 2018 had the highest count, with 1,147 titles.
- 2017 had 1,032 titles.
- 2019 had 1,030 titles.
- 2020 had 953 titles.
- 2016 had 902 titles.

**Finding:** The analyzed release-year distribution is concentrated in more recent years, with 2018 having the highest title count.

### 5.4 Content Rating Analysis

The five most common content ratings were:

| Rating | Count |
|---|---:|
| TV-MA | 3,207 |
| TV-14 | 2,160 |
| TV-PG | 863 |
| R | 799 |
| PG-13 | 490 |

**Finding:** TV-MA is the most common rating, followed by TV-14. This indicates a large representation of mature and older-teen content in the dataset.

### 5.5 Movie Duration Analysis

Movie duration was extracted from the duration column and converted into numeric minutes for analysis.

| Statistic | Result |
|---|---:|
| Average duration | 99.56 minutes |
| Shortest duration | 3 minutes |
| Longest duration | 312 minutes |
| Most common duration | 90 minutes |

**Finding:** The average movie duration is approximately 100 minutes, while 90 minutes is the most frequently occurring duration.

## 6. Statistical Analysis

The analysis included:

- Frequency distributions.
- Percentage distributions.
- Mean and median.
- Standard deviation.
- Minimum and maximum values.
- Quartiles and percentiles.
- Interquartile range (IQR) for potential movie-duration outlier detection.

The release-year analysis showed a mean of approximately 2014 and a median of 2017.

The movie-duration analysis showed an average duration of 99.56 minutes.

These statistics provide an overview of the dataset's distribution and central tendencies.

## 7. Data Quality Issues

The analysis identified the following issues:

1. Missing director information.
2. Missing cast information.
3. Missing country information.
4. Missing date-added values.
5. Missing ratings and durations.
6. Three inconsistent rating entries containing movie durations.

The three inconsistent rating entries were corrected during data cleaning.

The remaining missing date-added values were retained because their original dates could not be determined from the dataset.

## 8. Visualizations

Five visualizations were generated and exported as PNG files.

| Visualization | File |
|---|---|
| Movie vs TV Show distribution | `content_distribution.png` |
| Top 10 countries | `top_countries.png` |
| Release-year trend | `release_year_trend.png` |
| Content ratings | `content_ratings.png` |
| Movie duration distribution | `movie_duration.png` |

All five visualization files were verified in the project's `visualizations` directory.

## 9. Key Findings

The major findings from the analysis are:

- The dataset contains 8,807 Netflix titles.
- Movies account for 69.62% of all titles.
- TV Shows account for 30.38%.
- The United States leads in title-country entries.
- India ranks second in title-country entries.
- 2018 has the highest release-year count in the analyzed data.
- TV-MA is the most common content rating.
- The average movie duration is approximately 99.56 minutes.
- The most common movie duration is 90 minutes.
- Three inconsistent rating records were identified and corrected.

## 10. Limitations

- The dataset represents a particular snapshot and should not be interpreted as Netflix's current catalogue.
- The latest release year present is 2021.
- Country counts can include the same title under multiple countries.
- Missing values were handled without inventing unavailable information.
- Release-year and duration patterns describe this dataset and do not establish causal relationships.
- Statistical summaries describe the available records and may not represent all Netflix content.

## 11. Conclusion

This Exploratory Data Analysis project successfully examined the Netflix Movies and TV Shows dataset using Python.

The analysis identified the distribution of content types, leading countries by title-country entries, release-year patterns, common content ratings, and movie duration characteristics.

Data cleaning helped correct inconsistent records and handle missing information. Statistical summaries and five visualizations made the dataset easier to understand.

Overall, this project demonstrates practical skills in data inspection, cleaning, statistical analysis, anomaly detection, visualization, and insight generation using Python.

## 12. Project Structure

```text
G-Task-2/
│
├── dataset/
│   ├── netflix_titles.csv
│   └── netflix_cleaned.csv
│
├── notebooks/
│   └── netflix_eda.ipynb
│
├── visualizations/
│   ├── content_distribution.png
│   ├── top_countries.png
│   ├── release_year_trend.png
│   ├── content_ratings.png
│   └── movie_duration.png
│
├── reports/
│   └── Netflix_EDA_Report.md
│
├── src/
├── requirements.txt
└── README.md
```

---

**End of Report**