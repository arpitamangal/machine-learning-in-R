# False Discovery Rate

The code:
* Produces a 10,000 x 1001 matrix of random numbers drawn from a standard normal distribution.
* Treats the first column as “y” and the remaining 1000 columns as x’s.
* Regress y on x’s.
* Identifies the significant variables regression yield. (In reality do not expect to see any significant variable as the data is randomly generated.)
* Uses the BH procedure to control the FDR with a q of 0.1.


### False Discovery: A variable is found useful but in reality it is not.

When we run regression on high dimensional data (1000s of co-variates), we have Problem of Multiplicity. This leads to false discovery.

### Problem of Multiplicity: Conducting multiple statistical tests simultaneously raises the risk of getting false positives or Type I errors.

We say a variable is useful based on statistical significance. The concept of statistical significance goes wrong when we have many  variables.This happens because statistical significance is based on cut off value. If the likelihood of the observed result happening by chance is low, we call it a "true finding" and consider it statistically significant using hypothesis testing. However, The cut-off is for a single test. If we repeat the test many times, about cut-off × 100% of the null tests will erroneously pop up as significant. Leading to false discovery.

### False Discovery Proportion: proportion of false positive results among all statistically significant results

FDP = # false Positives /  # significant test 
We don't know this in reality as we if our model says 10 variables are significant. In reality, we don't know how many of those 10 are true findings

### False Discovery Rate: expected value of (FDP)

we can control for the expected value of FDP.

### BH-procedure: Control the false discovery rate (FDR)

The BH procedure works by adjusting the p-values for each hypothesis test based on the number of tests being conducted and the desired FDR level. The adjusted p-values are termed as q-values. Any hypothesis with a q-value below the FDR threshold is considered statistically significant, while those above the threshold are not. By controlling the FDR, the BH procedure aims to limit the proportion of false discoveries among all the significant results.
