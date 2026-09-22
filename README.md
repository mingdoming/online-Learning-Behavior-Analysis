# Online Learning Behavior Analysis

Learning Speed Analysis Based on LMS Clickstream Data

## Overview

This project analyzes online learning behavior using LMS clickstream data and investigates the relationship between learning speed and academic performance.

The study quantitatively defines **Learning Speed** based on the temporal progression of cumulative clicks and uses K-means clustering to classify learners into different learning-speed groups.

The academic performance of each group is then compared using statistical analysis.

## Research Objective

The main objectives of this study are:

- To quantitatively define learners' learning speed using clickstream data.
- To classify learners into groups based on learning speed.
- To compare academic performance across different learning-speed groups.
- To examine whether differences in academic performance between groups are statistically significant.

## Dataset

The **Open University Learning Analytics Dataset (OULAD)** was used for the analysis.

The following datasets were used:

- `studentVle`: LMS clickstream data
- `studentAssessment`: Academic assessment data
- `studentInfo`: Learner information

The `studentVle` dataset was primarily used to analyze learners' click behavior, while `studentAssessment` was used to calculate academic performance.

## Data Preprocessing

The preprocessing procedure consisted of the following steps:

1. Aggregate daily click counts for each learner.
2. Calculate cumulative click counts over time.
3. Remove learners with insufficient behavioral data.
4. Handle missing values and outliers.
5. Prepare the processed data for learning-speed calculation and clustering.

Learners with five or fewer available data points were excluded to improve the stability of the analysis.

## Learning Speed Definition

Learning Speed was defined based on the relationship between cumulative clicks and time.

For each learner, a linear regression model was fitted using date as the independent variable and cumulative clicks as the dependent variable.

`CumulativeClick = β₀ + β₁Date + ε`

The slope of the regression line was defined as the learner's **Learning Speed**.

`LearningSpeed = β₁`

A larger slope indicates a faster increase in cumulative learning activity over time.

## Analysis Method

### K-means Clustering

K-means clustering was applied to classify learners according to their Learning Speed.

The number of clusters was set to **3**, and the resulting groups were reordered according to their cluster centers:

- Slow
- Moderate
- Fast

The average Learning Speed of each group was:

| Group | Average Learning Speed |
|---|---:|
| Slow | 3.69 |
| Moderate | 13.95 |
| Fast | 34.09 |

## Academic Performance Analysis

Each learner's average academic score was calculated using the `studentAssessment` data and then combined with the learning-speed cluster information.

The results showed differences in average academic performance across the three groups.

| Cluster | Learning Speed Level | Number of Learners | Average Score |
|---|---|---:|---:|
| Cluster 0 | Slow | 16,354 | 71.33 |
| Cluster 1 | Moderate | 5,637 | 77.82 |
| Cluster 2 | Fast | 987 | 81.60 |

The fast learning-speed group showed the highest average academic score, while the slow learning-speed group showed the lowest average score.

## Statistical Analysis

One-way ANOVA was performed to examine whether the differences in academic performance between the learning-speed groups were statistically significant.

- **F-statistic:** 662.42
- **p-value:** < 0.001

The analysis identified statistically significant differences in academic performance between the learning-speed groups.

## Key Findings

- Learning Speed can be quantitatively derived from LMS clickstream data using the slope of cumulative clicks over time.
- K-means clustering classified learners into three learning-speed groups.
- The fast learning-speed group had the highest average academic score.
- The slow learning-speed group showed greater variation in academic performance.
- ANOVA indicated statistically significant differences in academic performance between the groups.

## Research Significance

This study provides a behavioral-data-based approach to quantitatively analyzing the learning process.

Rather than focusing only on the total amount of learning activity, the study considers the **progression and speed of learning activity over time**.

The results suggest that Learning Speed can be used as a behavior-based indicator for analyzing differences in academic performance and may provide a basis for further research on personalized learning support and learning strategies.

## Future Research

Future research can extend the analysis by incorporating:

- Additional learning behavior variables
- Time-series analysis of learning patterns
- More diverse learner characteristics
- Deep learning-based learner behavior prediction

## Technologies

- Python
- Pandas
- NumPy
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Project Structure

    online-learning-behavior-analysis/
    ├── README.md
    ├── online-learning-behavior-analysis.ipynb
    └── .gitignore

## Research Publication

**Title:**  
온라인 학습 행동 데이터를 활용한 학습 속도 분석 및 학업 성과와의 관계 연구

**English Title:**  
Analysis of Learning Speed Based on Online Learning Behavior and Its Relationship with Academic Performance

**Authors:**  
Somin Yim, Jihoon Seo

**Conference:**  
2025 한국정보기술학회 하계 종합학술대회

**Keywords:**  
Learning Speed, Learning Analytics, Clickstream Data, Clustering Analysis, Academic Performance

## Author

**Somin Yim**

Undergraduate Student  
Kangnam University  
Data Science
