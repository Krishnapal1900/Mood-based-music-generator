
# Project Report: Probability Analysis of Sample Means

Author: [Your Name]  
Date: [Project Date]  

---

## 1. Introduction

This project analyzes the probability of sample means exceeding certain thresholds based on given population parameters. 
The focus is on determining the likelihood of the average amount of an attribute (e.g., oil bottle contents, game duration) 
exceeding a certain value given a sample, based on assumptions about the population distribution and its parameters.

---

## 2. Problem Statements

### Problem 1: Probability of Sample Mean of Oil Bottles Exceeding a Threshold
An oil bottle claims to contain 1000 ml. A sample of 30 bottles is taken, and the mean amount found is 1000.25 ml. Given that:
   - Population mean (μ) = 1000 ml
   - Population standard deviation (σ) = 0.143 ml

We want to determine the probability that a sample mean will exceed 1000.25 ml for a sample of 30 bottles.

---

## 3. Methodology

### 3.1 Central Limit Theorem and Sampling Distribution
For both problems, we assume that the sample means are normally distributed due to the Central Limit Theorem, 
which states that for sufficiently large sample sizes, the sampling distribution of the sample mean will be approximately 
normal, regardless of the shape of the population distribution.

### 3.2 Standard Error of the Mean (SEM)
The SEM measures the expected spread of sample means around the population mean. It is calculated as:
SEM = σ / √n
where σ is the population standard deviation, and n is the sample size.

### 3.3 Z-Score Calculation
The Z-score tells us how many standard deviations away our target sample mean is from the population mean. The formula is:
Z = (X - μ) / SEM
where X is the target sample mean.

### 3.4 Probability Calculation
Using the Z-score, the cumulative distribution function (CDF) for a normal distribution gives the probability that a sample 
mean will be less than a certain value. To find the probability of exceeding a threshold, we subtract this value from 1.

---

## 4. Calculations

### Problem 1: Probability for Oil Bottles
Given:
   - μ = 1000 ml, σ = 0.143 ml, n = 30
   - Target sample mean X = 1000.25 ml

#### Step-by-Step Calculation:

1. Standard Error of the Mean (SEM):
   SEM = 0.143 / √30 = 0.0261

2. Z-Score Calculation:
   Z = (1000.25 - 1000) / 0.0261 ≈ 9.58

3. Probability:
   Using the normal distribution CDF, the probability that a sample mean exceeds 1000.25 ml is:
   P(X > 1000.25) = 1 - norm.cdf(9.58) ≈ 0.0000

This extremely low probability suggests that observing a sample mean of 1000.25 ml or more is very unlikely if the population 
mean truly is 1000 ml with a standard deviation of 0.143 ml.

---

## 5. Python Code

Here is the Python code used to perform the above calculations:

```python
from scipy.stats import norm
import numpy as np

# Given values
mu = 1000          # Population mean in ml
sigma = 0.143      # Population standard deviation in ml
n = 30             # Sample size
sample_mean = 1000.25 # Target sample mean to exceed

# Step 1: Calculate the Standard Error of the Mean (SEM)
sem = sigma / np.sqrt(n)

# Step 2: Calculate the Z-score
z_score = (sample_mean - mu) / sem

# Step 3: Calculate the probability that the sample mean will exceed 1000.25 ml
probability = 1 - norm.cdf(z_score)

# Output the results
print(f"Z-score: {z_score}")
print(f"Probability that the sample mean exceeds 1000.25 ml: {probability:.5f}")
```

---

## 6. Results and Interpretation

- The calculated probability of the sample mean exceeding 1000.25 ml is approximately **0.0000**.
- This extremely low probability indicates that the observed sample mean of 1000.25 ml is unlikely to occur by random chance if 
  the population mean is indeed 1000 ml.

---

## 7. Conclusion

In this project, we demonstrated how to calculate the probability that a sample mean exceeds a specified value based on population 
parameters. By applying the Central Limit Theorem, standard error calculations, and Z-score analysis, we determined that observing 
a sample mean of 1000.25 ml or greater is highly improbable, suggesting that the sample mean may not reflect the stated 
population parameters.

---

## 8. References

- [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem)
- [Normal Distribution](https://en.wikipedia.org/wiki/Normal_distribution)
- [SciPy Documentation](https://docs.scipy.org/doc/scipy/)

---
DATA SET LINK - https://www.kaggle.com/datasets/msambare/fer2013?resource=download
