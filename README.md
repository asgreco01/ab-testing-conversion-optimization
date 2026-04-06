# A/B Testing for Conversion Optimization

## End-to-End Analysis Using Frequentist and Bayesian Approaches

### Project Overview
In digital products and e-commerce, even small improvements in conversion rates can lead to meaningful revenue growth. A/B testing is one of the most widely used methods to evaluate whether a product change improves user behavior.

This project simulates an A/B test comparing two versions of a product experience:

- **Version A** = control
- **Version B** = treatment

The purpose of the analysis is to determine whether version B produces a higher conversion rate than version A, and whether the available evidence is strong enough to support a rollout decision.

---

## Business Question
**Should the company roll out version B based on the available experimental evidence?**

---

## Project Objective
The goal of this project is to evaluate whether the observed difference in conversion rates between the two groups is statistically and practically meaningful.

To answer this question, the analysis includes:

- Exploratory Data Analysis (EDA)
- Frequentist hypothesis testing
- Confidence interval estimation
- Power analysis
- Segmentation analysis by device
- Bayesian A/B testing
- Final business recommendation

---

## Dataset
This project uses a **simulated dataset** designed to reflect a realistic A/B testing scenario.

### Features
- `user_id`: unique identifier for each user
- `group`: experiment group (`A` or `B`)
- `device`: user device (`mobile` or `desktop`)
- `converted`: conversion outcome (`0` = no conversion, `1` = conversion)

### Simulation logic
- Approximately 1,000 users
- Users assigned to group A or B
- Users split between mobile and desktop
- Conversion behavior simulated as a binary outcome

---

## Methodology

### 1. Data Preparation
The dataset was generated and structured to simulate a realistic product experiment. The data was then stored in CSV format for reproducibility and portfolio presentation.

### 2. Exploratory Data Analysis (EDA)
Initial analysis focused on:
- user distribution across groups
- device distribution
- overall conversion rate
- conversion rates by group
- conversion rates by device and by segment

This step was used to identify preliminary signals before running statistical tests.

### 3. Hypothesis Testing (Frequentist Approach)
A one-tailed **z-test for proportions** was used to compare conversion rates between group A and group B.

- **Null hypothesis (H0):** conversion rate of A = conversion rate of B
- **Alternative hypothesis (H1):** conversion rate of B > conversion rate of A

### 4. Confidence Interval Estimation
A 95% confidence interval was calculated for the difference in conversion rates between group B and group A.

This helped quantify the uncertainty around the estimated effect.

### 5. Power Analysis
A power analysis was conducted to determine whether the experiment had sufficient sample size to detect the observed effect.

This is a critical step because a non-significant result may occur not only because there is no real effect, but also because the experiment is underpowered.

### 6. Segmentation Analysis
The results were analyzed separately for:
- mobile users
- desktop users

This was done to identify whether the treatment effect might be stronger in a specific user segment.

### 7. Bayesian A/B Testing
In addition to the frequentist approach, a Bayesian analysis was performed using Beta distributions to estimate the probability that version B outperforms version A.

This provided a probability-based interpretation of the treatment effect.

### 8. Business Conclusion
The final step translated the statistical findings into a practical product recommendation.

---

## Key Results

### Overall result
Version B showed a slightly higher conversion rate than version A, but the difference was **not statistically significant** based on the z-test.

### Confidence interval
The 95% confidence interval for the difference in conversion rates included zero, indicating uncertainty about whether the true effect is positive or negative.

### Power analysis
The power analysis suggested that the experiment was **underpowered**.

- Required sample size per group: **~5005**
- Actual sample size per group: **~500**

This means the experiment likely did not include enough users to reliably detect a small effect.

### Segmentation analysis
The segmented analysis suggested that version B appeared to perform slightly better on **desktop**, but the evidence was not strong enough to support a confident conclusion.

### Bayesian result
The Bayesian approach provided an additional probability-based view of the experiment, but the evidence still did not support a strong rollout decision.

---

## Final Recommendation
Based on the available evidence, **version B should not be fully rolled out at this stage**.

Although version B showed a small numerical improvement in conversion rate, the result was not statistically significant, and the experiment was likely underpowered. This means the current evidence is not strong enough to justify a product decision.

A better next step would be to:

- run the experiment with a much larger sample size
- continue monitoring performance by device
- further investigate the desktop segment as a possible area of opportunity

---

## Why This Project Matters
This project demonstrates not only how to run an A/B test, but also how to interpret uncertainty and make business decisions responsibly.

It shows the ability to:

- apply statistical testing to product data
- interpret p-values and confidence intervals
- evaluate sample size adequacy with power analysis
- investigate segment-level insights
- combine frequentist and Bayesian approaches
- translate analysis into business recommendations

---

## Tools and Libraries
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels

---

## Repository Structure

```text
ab-testing-conversion-optimization/
│
├── data/
│   └── ab_test_data.csv
│
├── notebook/
│   └── ab_test_analysis.ipynb
│
├── images/
│   ├── conversion_rate_by_group.png
│   ├── conversion_rate_by_device_and_group.png
│   ├── confidence_interval_plot.png
│   └── bayesian_posterior_distributions.png
│
├── requirements.txt
│
└── README.md

## Author: Andrea S. Greco
