[README-abtest.md](https://github.com/user-attachments/files/24358025/README-abtest.md)
# A/B Testing and Causal Inference for an E-Commerce Website

## Project Overview
This project evaluates whether a redesigned landing page increases user conversion on an e-commerce website. Using data from nearly 300,000 users, A/B testing and causal inference analysis were performed to assess the effectiveness of the new design.

---

## Business Problem
Website design often influences customers' purchase decisions. The goal of this project is to determine if the treatment (redesigned landing page) leads to a higher conversion rate compared to the control (existing page).

**Null Hypothesis:** The conversion rate is the same for users exposed to the control and treatment pages.

**Alternative Hypothesis:** Users exposed to the treatment page have a higher probability of conversion than users exposed to the control page.

---

## Data Description
- **Source:** Kaggle - E-commerce A/B testing - https://www.kaggle.com/datasets/ahmedmohameddawoud/ecommerce-ab-testing
- **Users:** 290,584
- **Features:** user id, treatment vs. control, time spent on website, country, whether or not they converted

---

## Methodology
1. Sample Validation: 
    - Checked for balanced group assignment using Sample Ratio Mismatch (SRM).
2. A/B Testing:
    - Two-sample proportion z-test to compare conversion rates.
    - Calculated observed effect size and minimum detectable effect (MDE).
3. Causal Inference:
    - Built a logistic regression model controlling for covariates.

---

## Results

**A/B Test:**

- Control Conversion Rate: 12.04%
- Treatment Conversion Rate: 11.88%
- P-value: 0.207
- Z-statistic: 1.26
95% Confidence Intervals:
  - Control: (0.1187, 0.1220)
  - Treatment: (0.1172, 0.1205)
- Effect Size: 0.0049
- Minimum Detectable Effect (MDE) at 80% power: 0.030

The p-value (0.207) is greater than the significance threshold (0.05) and the z-statistic (1.26) is below 1.96, so we fail to reject the null hypothesis. There is no statistically significant difference between control and treatment conversion rates.

**Logistic Regression:**

- LLR p-value: 0.27
- All coefficients had p-values > 0.05

No statistically significant treatment effect was detected after controlling for covariates, suggesting insufficient evidence to conclude that the redesigned page causally impacts conversion.

---

## Recommendations

- Do not roll out the redesigned page globally at this time.
- Consider exploring alternative design iterations.
- Target high-engagement user segments in future experiments, where exploratory analysis may indicate stronger effects.

---

## Tools & Technologies
- **Python**
- **pandas**, **NumPy** – data manipulation  
- **statsmodels** – statistical analysis  
- **Jupyter Notebook** – analysis and documentation  

---

## Repository Structure
```
├── AB Testing and Causal Inference Executive Summary.pdf
├── AB Testing and Causal Inference.ipynb
├── E-commerce AB testing - Kaggle.zip
├── README.md
```

---

## Contact
If you’d like to discuss this project or explore related work, feel free to connect with me on LinkedIn or view my other repositories.
