# SAMPLE PRE-PROCESSING

## SAMPLE SIZE

General sample size formula is:

$$
n \propto \frac{(Z_{1-\alpha/2} + Z_{1-\beta})^2}{\Delta^2}
$$

**Where:**  
- $n$: required sample size  
- $Z_{1-\alpha/2}$: critical value corresponding to the chosen significance level  
- $Z_{1-\beta}$: critical value corresponding to the desired power  
- $\Delta$: the magnitude of difference or relationship effect in the study

To calculate sample size, significance level as 0.05/0.01 & power as 0.8/0.9 are known and also effect size must be defined by the researcher based on the study.

This general sample size formula also must be specialized to hypothesis test that applied because each hypothesis test has own sample size formula.

t-Test & Wilcoxons:

  - Independent t-Test & Wilcoxon Rank Sum:  

$$
n = 2 \left( \frac{(Z_{\alpha} + Z_{\beta}) \sigma}{d} \right)^2
\text{where } \sigma = \text{population standard deviation, } d = \text{effect size}
$$

  - Paired t-Test & Wilcoxon Signed Rank:  

$$
n = \left( \frac{(Z_{\alpha} + Z_{\beta}) \sigma_d}{d} \right)^2 \text{where } \sigma_d = \text{standard deviation of differences, } d = \text{effect size}
$$

One-Way ANOVA, One-Way RM ANOVA, Kruskal-Wallis & Friedman:  

$$
n = \frac{(Z_{\alpha} + Z_{\beta})^2}{f^2} \text{where } f = \text{Cohen's f (effect size)}
$$

Two-Way ANOVA, Two-Way RM ANOVA, SRH, Aligned Rank Transform, Chi-Square Homogeneity & Chi-Square Independence:  

$$
n = \frac{(Z_{\alpha} + Z_{\beta})^2}{f^2} \quad \text{where } f = \text{Cohen's f (or Cohen's w for chi-Square)}
$$

One-Way MANOVA, Two-Way MANOVA, One-Way RM MANOVA, Two-Way RM MANOVA, PERMANOVA One-Way, PERMANOVA Two-Way, Wilks Lambda One-Way & Wilks Lambda Two-Way:

$$
N = \frac{(Z_{\alpha} + Z_{\beta})^2 \cdot (u+v+1)}{u \cdot f^2} \text{where } u = \text{number of dependent variables, } v = \text{degrees of freedom denominator, } f = \text{effect size}
$$

Pearson & Spearman Correlation (Fisher-z):

$$
n = \frac{(Z_{\alpha} + Z_{\beta})^2}{\left( \frac{1}{2} \ln \frac{1+r}{1-r} \right)^2} \text{where } r = \text{expected correlation coefficient}
$$

## SAMPLE DISTRIBUTION

Shapiro-Wilk Test for Normality

To detect whether a continuous numerical variable follows a normal distribution for parametricity via Shapiro-Wilk stat (W).

Shapiro-Wilk stat (W) is:

$$
W = \frac{\left( \sum_{i=1}^{n} a_i x_{(i)} \right)^2}{\sum_{i=1}^{n} (x_i - \bar{x})^2}
$$

**Where:**

- $x_{(i)}$: Ordered sample values (from smallest to largest)  
- $x_i$: Original sample values  
- $\bar{x}$: Sample mean  
- $a_i$: Constants derived from the expected values of order statistics of a standard normal distribution  
- $n$: Sample size  

And its interpretation is:

$$
\begin{array}{c|l}
\textbf{W value} & \textbf{Normality} \\
\hline
W \approx 1 & \text{Data is approximately normal} \\
W < 0.95 & \text{Slight deviation from normality} \\
W < 0.90 & \text{Moderate deviation from normality} \\
W < 0.80 & \text{Strong deviation from normality} \\
\end{array}
$$

It is W-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population data of a continuous numerical variable **is not** anormally distributed.   
- **Alternative hypothesis (H1):** The population data of a continuous numerical variable **is** anormally distributed.  

To reject H0 (that is, to accept H1), applying hypothesis test.

**2. W to P-Value via Sample Size**

The Shapiro-Wilk test directly calculates p-value for W via sample size tables to use ready and the p-value is:  

- **Two-Tailed:**  

$$
p = P(\text{W observed} \le W)
$$

**3. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.

Here, $\alpha$ is theoretically assumed as 0.05-0.01 generally.

# CONFIRMATORY DATA ANALYSIS

CDA means analysis via **HYPOTHESIS TESTS**.

And the analysis via hypothesis tests can be categorized in 2 types hierarchically as **inter-group** & **inter-variable**.

## INTER-GROUP ANALYSIS

### Parametric Tests For Continuous Numerical Inter-Group

#### Independent t-Test

To detect whether there is a difference between two different continuous numerical groups via t-stat.

t-stat is:  

$$
t = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}}
$$


**Where:**

- $\bar{x}_1, \bar{x}_2$: Sample means of group 1 and group 2
- $s_1^2, s_2^2$: Sample variances of group 1 and group 2
- $n_1, n_2$: Sample sizes of group 1 and group 2

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{|t|}\ \textbf{value} & \textbf{Difference} \\
\hline
|t| < 1 & \text{No difference} \\
1 \le |t| < 2 & \text{Weak difference} \\
2 \le |t| < 3 & \text{Moderate difference} \\
3 \le |t| < 5 & \text{Strong difference} \\
|t| \ge 5 & \text{Very strong difference} \\
\end{array}
$$

It is t-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population difference between two different groups **is not** significantly different.

**Alternative hypothesis (H1):** The population difference between two different groups **is** significantly different.

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, every parametric distribution has a **degrees of freedom (df)** value, and for the t-stat, that is, the t-distribution, **df = n1 + n2 − 2**.

Under H0, the t-stat follows t-distribution and the probability density function (PDF) is:

$$
f(t) = \frac{\Gamma\left(\frac{df+1}{2}\right)}{\sqrt{df \pi}\, \Gamma\left(\frac{df}{2}\right)} \left(1 + \frac{t^2}{df}\right)^{-\frac{df+1}{2}}
$$

To integrate PDF to t as the cumulative distribution function (CDF) is:

$$
F(t) = \int_{-\infty}^{t} f(u)\,du
$$

**3. CDF to P-Value**

$$
F(t) = P(T \le t)
$$

It means the probability of values less than or equal to t.

- **One-Tailed:**  
  - Used when H0: parameter ≤ value, H1: parameter > value as **upper-tailed test** and the “extreme values” of interest are greater than t. Therefore, the p-value is:

$$
p = 1 - F(t)
$$

  - Used when H0: parameter ≥ value, H1: parameter < value as **lower-tailed test** and therefore, the p-value is directly:

$$
p = F(t)
$$

- **Two-Tailed:**  

  - Used when H0: parameter = value, H1: parameter ≠ value (i.e., "different") and to cover extreme values in both the upper and lower tails by using absolute value of t and formula multiplication by 2. Therefore, the p-value is:

$$
p = 2 \cdot (1 - F(|t|))
$$

**4. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

Here, $\alpha$ is theoretically assumed as 0.05-0.01 generally.

#### Paired t-Test

To detect whether there is a difference between two related continuous numerical groups via t-stat.

t-stat is:  

$$
t = \frac{\bar{d}}{s_d / \sqrt{n}}
$$

**Where:**

- $\bar{d}$: Mean of the differences between paired observations  
- $s_d$: Standard deviation of the differences  
- $n$: Number of pairs  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{|t|}\ \textbf{value} & \textbf{Difference} \\
\hline
|t| < 1 & \text{No difference} \\
1 \le |t| < 2 & \text{Weak difference} \\
2 \le |t| < 3 & \text{Moderate difference} \\
3 \le |t| < 5 & \text{Strong difference} \\
|t| \ge 5 & \text{Very strong difference} \\
\end{array}
$$

It is t-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population difference between two related groups **is not** significantly different.  

**Alternative hypothesis (H1):** The population difference between two related groups **is** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, every parametric distribution has a **degrees of freedom (df)** value, and for the paired t-stat, that is, the t-distribution,  

$$
df = n - 1
$$

Under H0, the t-stat follows t-distribution and the probability density function (PDF) is:  

$$
f(t) = \frac{\Gamma\left(\frac{df+1}{2}\right)}{\sqrt{df \pi}\, \Gamma\left(\frac{df}{2}\right)} \left(1 + \frac{t^2}{df}\right)^{-\frac{df+1}{2}}
$$

To integrate PDF to t as the cumulative distribution function (CDF) is:  

$$
F(t) = \int_{-\infty}^{t} f(u)\,du
$$

**3. CDF to P-Value**

$$
F(t) = P(T \le t)
$$

It means the probability of values less than or equal to t.  

- **One-Tailed:**  
  - H0: parameter ≤ value, H1: parameter > value (**upper-tailed test**):  

$$
p = 1 - F(t)
$$

  - H0: parameter ≥ value, H1: parameter < value (**lower-tailed test**):  

$$
p = F(t)
$$

- **Two-Tailed:**  
  - H0: parameter = value, H1: parameter ≠ value:  

$$
p = 2 \cdot (1 - F(|t|))
$$

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is theoretically assumed as 0.05–0.01 generally.

#### One-Way ANOVA Test

To detect whether there are differences between two or more different continuous numerical groups on an independent variable via F-stat.

F-stat is:  

$$
F = \frac{\text{MS}_{\text{between}}}{\text{MS}_{\text{within}}}
$$

**Where:**

- $\text{MS}_{\text{between}}$: Mean square between groups  
- $\text{MS}_{\text{within}}$: Mean square within groups  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population difference between two or more different groups on an independent variable **is not** significantly different.  

**Alternative hypothesis (H1):** The population difference between two or more different groups on an independent variable **is** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, F-distribution has **degrees of freedom (df1, df2)** values:  

- $df_1 = k - 1$ (between groups)  
- $df_2 = N - k$ (within groups)  

**Where:**

- $k$: Independent groups
- $N$: Sample size total

Under H0, the F-stat follows F-distribution and the probability density function (PDF) is:  

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

As is seen, to normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because of that F-stat is based on squared differences, so it cannot take negative values. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference and the lower-tailed test logic is not meaningful for F-test.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### Two-Way ANOVA Test

To detect whether there are differences between two or more different continuous numerical groups on two different independent variables via F-stat.

F-stat is:

$$
F = \frac{\text{MS}_{\text{effect}}}{\text{MS}_{\text{within}}}
$$

**Where:**

- $\text{MS}_{\text{effect}}$: Mean square for the effect (Factor A, Factor B, or A×B interaction)  
- $\text{MS}_{\text{within}}$: Mean square within groups (residual/error)  

And its interpretation is similar to One-Way ANOVA:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population difference between two or more different groups on two independent variables **is not** significantly different.  

**Alternative hypothesis (H1):** The population difference between two or more different groups on two independent variables **is** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, F-distribution has **degrees of freedom (df1, df2)** values:  

- $df_1 = k_{\text{effect}} - 1$ (between groups for that effect)  
- $df_2 = N - k_{\text{total}}$ (within groups / residual)

**Where:**

- $k_{\text{effect}}$: Number of levels in the factor or interaction  
- $k_{\text{total}}$: Total number of groups  
- $N$: Total sample size

Under H0, the F-stat follows F-distribution and the probability density function (PDF) is:  

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because the F-stat is based on squared differences, so it cannot take negative values. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### One-Way Repeated Measures ANOVA Test

To detect whether there are differences between two or more repeated continuous numerical measurements on the same group on an independent variable via F-stat.

F-stat is:  

$$
F = \frac{\text{MS}_{\text{between}}}{\text{MS}_{\text{residual}}}
$$

**Where:**

- $\text{MS}_{\text{between}}$: Mean square between repeated measures
- $\text{MS}_{\text{residual}}$: Mean square of residuals

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population difference between two or more repeated measurements on the same group on an independent variable **is not** significantly different.  

**Alternative hypothesis (H1):** The population difference between two or more repeated measurements on the same group on an independent variable **is** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, repeated measures F-distribution has **degrees of freedom (df1, df2)** values:

- $df_1 = k - 1$  
- $df_2 = (n - 1)(k - 1)$

**Where:**

- $k$: Number of repeated measurements  
- $n$: Number of subjects

Under H0, the F-stat follows F-distribution and the probability density function (PDF) is:  

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because the F-stat is based on squared differences, so it cannot take negative values. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### Two-Way Repeated Measures ANOVA Test

To detect whether there are differences between two or more repeated continuous numerical measurements on the same group on two independent variables via F-stat.

F-stat is:

$$
F = \frac{\text{MS}_{\text{effect}}}{\text{MS}_{\text{residual}}}
$$

**Where:**

- $\text{MS}_{\text{effect}}$: Mean square for the effect
- $\text{MS}_{\text{residual}}$: Mean square of residuals

And its interpretation is similar to One-Way Repeated Measures ANOVA:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population difference between two or more repeated measurements on the same group on two independent variables **is not** significantly different.  

**Alternative hypothesis (H1):** The population difference between two or more repeated measurements on the same group on two independent variables **is** significantly different.

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, repeated measures F-distribution has **degrees of freedom (df1, df2)** values:

- $df_1 = k_{\text{effect}} - 1$
- $df_2 = (n - 1)(k_{\text{effect}} - 1)$

**Where:**

- $k_{\text{effect}}$: Number of levels in the factor or interaction  
- $n$: Number of subjects

Under H0, the F-stat follows F-distribution and the probability density function (PDF) is:  

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because the F-stat is based on squared differences, so it cannot take negative values. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### One-Way MANOVA Test

To detect whether there are differences between two or more different continuous numerical groups on an independent variable & multiple dependent variables via multivariate F-stat.

Multivariate F-stat is:

$$
F = \frac{\text{MS}_{\text{between}}}{\text{MS}_{\text{within}}}
$$

**Where:**

- $\text{MS}_{\text{between}}$: Mean square between groups
- $\text{MS}_{\text{within}}$: Mean square within groups

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is multivariate F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population differences between two or more different continuous numerical groups on an independent variable & multiple dependent variables **are not** significantly different.  

**Alternative hypothesis (H1):** The population differences between two or more different continuous numerical groups on an independent variable & multiple dependent variables **are** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, multivariate F-distribution has **degrees of freedom (df1, df2)** values:

- $df_1 = p \cdot (k - 1)$   
- $df_2 = N - k - p + 1$

**Where:**

- $k$: Number of independent groups  
- $p$: Number of dependent variables  
- $N$: Total sample size

Under H0, the F-stat follows an approximate F-distribution and the probability density function (PDF) is:

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because F-stat is based on squared differences; negative values cannot occur. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### Two-Way MANOVA Test

To detect whether there are differences between two or more different continuous numerical groups on two independent variables & multiple dependent variables via multivariate F-stat.

Multivariate F-stat is:

$$
F = \frac{\text{MS}_{\text{effect}}}{\text{MS}_{\text{within}}}
$$

**Where:**

- $\text{MS}_{\text{effect}}$: Mean square for the effect
- $\text{MS}_{\text{within}}$: Mean square within groups

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is multivariate F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population differences between two or more different continuous numerical groups on two independent variables & multiple dependent variables **are not** significantly different.  

**Alternative hypothesis (H1):** The population differences between two or more different continuous numerical groups on two independent variables & multiple dependent variables **are** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, multivariate F-distribution has **degrees of freedom (df1, df2)** values:

- $df_1 = p \cdot (k_{\text{effect}} - 1)$
- $df_2 = N - k_{\text{effect}} - p + 1$

**Where:**

- $k_{\text{effect}}$: Number of levels in the factor or interaction  
- $p$: Number of dependent variables  
- $N$: Total sample size

Under H0, the F-stat follows an approximate F-distribution and the probability density function (PDF) is:

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because F-stat is based on squared differences; negative values cannot occur. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### One-Way Repeated Measures MANOVA Test

To detect whether there are differences between two or more repeated continuous measurements on the same group on an independent variable & multiple dependent variables via multivariate F-stat.

Multivariate F-stat is:

$$
F = \frac{\text{MS}_{\text{between}}}{\text{MS}_{\text{residual}}}
$$

**Where:**

- $\text{MS}_{\text{between}}$: Mean square between repeated measures
- $\text{MS}_{\text{residual}}$: Mean square of residuals  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is multivariate F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population differences between repeated measurements on the same group on an independent variable & multiple dependent variables **are not** significantly different.  

**Alternative hypothesis (H1):** The population differences between repeated measurements on the same group on an independent variable & multiple dependent variables **are** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, repeated measures multivariate F-distribution has **degrees of freedom (df1, df2)** values:

- $df_1 = p \cdot (k - 1)$  
- $df_2 = (n - 1) \cdot (k - 1)$  

**Where:**

- $k$: Number of repeated measurements  
- $n$: Number of subjects  
- $p$: Number of dependent variables  

Under H0, the F-stat follows an approximate F-distribution and the probability density function (PDF) is:

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because F-stat is based on squared differences; negative values cannot occur. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### Two-Way Repeated Measures MANOVA Test

To detect whether there are differences between repeated continuous measurements on the same group on two independent variables & multiple dependent variables via multivariate F-stat.

Multivariate F-stat is:

$$
F = \frac{\text{MS}_{\text{effect}}}{\text{MS}_{\text{residual}}}
$$

**Where:**

- $\text{MS}_{\text{effect}}$: Mean square for a main effect
- $\text{MS}_{\text{residual}}$: Mean square of residuals

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference} \\
1 < F < 3 & \text{Weak difference} \\
3 \le F < 5 & \text{Moderate difference} \\
5 \le F < 10 & \text{Strong difference} \\
F \ge 10 & \text{Very strong difference} \\
\end{array}
$$

It is multivariate F-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between repeated continuous measurements on the same group on two independent variables & multiple dependent variables **are not** significantly different.  
- **Alternative hypothesis (H1):** The population differences between repeated continuous measurements on the same group on two independent variables & multiple dependent variables **are** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Test Stat to Distribution via PDF to CDF**

Like t-distribution, repeated measures multivariate F-distribution has **degrees of freedom (df1, df2)** values with **two independent variables (A, B)**:

- **For Independent Variable A:** $df_1 = p \cdot (k_A - 1)$, $df_2 = (n - 1) \cdot (k_A - 1)$  
- **For Independent Variable B:** $df_1 = p \cdot (k_B - 1)$, $df_2 = (n - 1) \cdot (k_B - 1)$  
- **For Interaction A×B:** $df_1 = p \cdot (k_A - 1)(k_B - 1)$, $df_2 = (n - 1) \cdot (k_A - 1)(k_B - 1)$  

**Where:**

- $k_A$, $k_B$: Number of levels for independent variables A and B  
- $n$: Number of subjects  
- $p$: Number of dependent variables  

Under H0, the F-stat follows an approximate F-distribution and the probability density function (PDF) is:

$$
f(F) = \frac{\sqrt{\frac{(df_1 F)^{df_1} df_2^{df_2}}{(df_1 F + df_2)^{df_1 + df_2}}}}{F B\left(\frac{df_1}{2}, \frac{df_2}{2}\right)}
$$

To normalize PDF by Beta function:

$$
B\left(\frac{df_1}{2}, \frac{df_2}{2}\right) = \int_0^1 t^{\frac{df_1}{2}-1} (1-t)^{\frac{df_2}{2}-1} \, dt
$$

To integrate PDF to F as the cumulative distribution function (CDF) is:  

$$
F(F) = \int_{0}^{F} f(u)\,du
$$

**3. CDF to P-Value**

$$
p = P(F_{\text{obs}} \le F) = 1 - F(F_{\text{obs}})
$$

As is seen, the F-distribution is one-sided because F-stat is based on squared differences; negative values cannot occur. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a difference; lower-tailed test is not meaningful.

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

### Non-Parametric Tests For Numerical & Ordinal Categorical Inter-Group

#### Wilcoxon Rank-Sum Test For Independent t-Test

To detect whether there is a difference between two different numerical & ordinal groups via  rank-sum (U) stat.

Wilcoxon rank-sum stat (U) is:

$$
U = n_1 n_2 + \frac{n_1 (n_1 + 1)}{2} - R_1
$$

**Where:**
- $U$ : Wilcoxon rank-sum statistic  
- $n_1, n_2$ : Sample sizes of group 1 and group 2  
- $R_1$ : Sum of ranks for group 1  
- (Similarly, $U$ can be computed from $R_2$ for group 2, and $U_1 + U_2 = n_1 n_2$)

And its interpretation is:

$$
0 \leq U \leq n_1 \cdot n_2
$$

- The smallest $U$ (≈ 0) → one group completely dominates the other (large difference).  

- The largest $U$ (≈ $n_1 \cdot n_2$) → one group completely dominates the other (large difference).  

- The middle value (≈ $n_1 \cdot n_2 / 2$) → the groups are similar (no difference).  

It is Wilcoxon U-stat of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The two population difference between two different numerical & ordinal groups **is not** significantly different.  
- **Alternative hypothesis (H1):** The two population difference between two different numerical & ordinal groups **is** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Wilcoxon U Statistic via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate Wilcoxon U stat to get empirical probability distributions, not theoretical distributions like t-distribution.  

Randomly shuffle the group labels between the two samples. This simulates the null hypothesis H0, where no group difference exists.  

For each permutation $j$, compute a new Wilcoxon U stat:  

$$
U_{\text{perm}}^{(j)} = \text{WilcoxonRankSum}(X^{(j)}_1, X^{(j)}_2)
$$

Repeat this process N times (e.g., 10,000) to generate the null distribution of U under H0.  

**3. Wilcoxon U Stat to P-Value**

- **One-Tailed:**  
  - Upper-tailed (H1: Group1 > Group2):  

$$
p = \frac{\text{number of permutations where } U_{\text{perm}}^{(j)} \ge U_{\text{obs}}}{N}
$$

  - Lower-tailed (H1: Group1 < Group2):  

$$
p = \frac{\text{number of permutations where } U_{\text{perm}}^{(j)} \le U_{\text{obs}}}{N}
$$

- **Two-Tailed:**  
  - Used when H0: groups equal, H1: groups different. Both extremes are considered:  

$$
p = \frac{\text{number of permutations where } |U_{\text{perm}}^{(j)} - \mu_U| \ge |U_{\text{obs}} - \mu_U|}{N}
$$

Here, $\mu_U = \frac{n_1 n_2}{2}$ is the expected mean of $U$ under H0.  

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.  

#### Wilcoxon Signed-Rank Test For Paired t-Test

To detect whether there is a difference between two related numerical & ordinal groups via signed-rank (W) stat.  

Wilcoxon signed-rank statistic (W) is:  

$$
W = \sum_{i=1}^n \mathrm{sgn}(d_i)\,R_i
$$

**Where:**  
- $W$ : Wilcoxon signed-rank statistic  
- $n$ : Number of paired observations (excluding $d_i = 0$ ties)  
- $d_i = x_i - y_i$ : Difference between the paired values  
- $R_i$ : Rank of $|d_i|$ (absolute differences)
- $\mathrm{sgn}(d_i)$: Sign function (+1 if $d_i>0$, −1 if $d_i<0$)

And its interpretation is:  

- $W \approx 0$ → the two paired samples are similar (no difference).  

- Large positive $W$ (close to $+\tfrac{n(n+1)}{2}$) → the first sample tends to be larger than the second (large difference).  

- Large negative $W$ (close to $-\tfrac{n(n+1)}{2}$) → the second sample tends to be larger than the first (large difference).  

It is Wilcoxon W-stat of sample and to inference for population, hypothesis test must be used.  

**1. Hypotheses**

- **Null hypothesis (H0):** The population difference between two related numerical & ordinal groups **is not** significantly different.  
- **Alternative hypothesis (H1):** The population difference between two related numerical & ordinal groups **is** significantly different.

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Wilcoxon W Stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate Wilcoxon W stat to get empirical probability distributions, not theoretical distributions like t-distribution.  

Randomly flip the signs of $d_i$ (differences) with 50% probability. This simulates the null hypothesis H0, where no systematic difference exists.  

For each permutation $j$, compute a new Wilcoxon W stat:  

$$
W_{\text{perm}}^{(j)} = \text{WilcoxonSignedRank}(d_1^{(j)}, d_2^{(j)}, \dots, d_n^{(j)})
$$

Repeat this process N times (e.g., 10,000) to generate the null distribution of W under H0.  

**3. Wilcoxon W Stat to P-Value**

- **One-Tailed:**  
  - Upper-tailed (H1: group difference > 0):  

$$
p = \frac{\text{number of permutations where } W_{\text{perm}}^{(j)} \ge W_{\text{obs}}}{N}
$$

  - Lower-tailed (H1: group difference < 0):  

$$
p = \frac{\text{number of permutations where } W_{\text{perm}}^{(j)} \le W_{\text{obs}}}{N}
$$

- **Two-Tailed:**  
  - Used when H0: differences = 0, H1: differences ≠ 0. Both extremes are considered:  

$$
p = \frac{\text{number of permutations where } |W_{\text{perm}}^{(j)}| \ge |W_{\text{obs}}|}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.  

#### Kruskal–Wallis H Test For One-Way ANOVA Test

To detect whether there are differences between two or more different numerical & ordinal categorical groups on an independent variable via Kruskal–Wallis H stat.  

Kruskal–Wallis stat (H) is:  

$$
H = \frac{12}{N(N+1)} \sum_{j=1}^k \frac{R_j^2}{n_j} - 3(N+1)
$$

**Where:**  
- $H$ : Kruskal–Wallis test statistic  
- $k$ : Number of groups  
- $n_j$ : Sample size of group $j$  
- $N = \sum_{j=1}^k n_j$ : Total sample size  
- $R_j$ : Sum of ranks for group $j$  

And its interpretation is:  

- $H \approx 0$ → the groups are similar (no difference).  

- Large $H$ value → at least one group distribution tends to differ strongly from the others (large difference).  

It is Kruskal–Wallis H-stat of sample and to inference for population, hypothesis test must be used.  

**1. Hypotheses**  

- **Null hypothesis (H0):** The population differences between two or more different numerical & ordinal categorical groups on an independent variable **are not** significantly different.  
- **Alternative hypothesis (H1):** The population differences between two or more different numerical & ordinal categorical groups on an independent variable **are** significantly different.    

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Kruskal–Wallis H Stat via Resampling**  

Resampling simulations, such as permutation & bootstrap, can be used to recalculate Kruskal–Wallis H stat to get empirical probability distributions, not theoretical distributions like t-distribution.  

Randomly shuffle the group labels across all observations. This simulates the null hypothesis H0, where no group differences exist.  

For each permutation $j$, compute a new Kruskal–Wallis H stat:  

$$
H_{\text{perm}}^{(j)} = \text{KruskalWallis}(X^{(j)}_1, X^{(j)}_2, \dots, X^{(j)}_k)
$$

Repeat this process N times (e.g., 10,000) to generate the null distribution of H under H0.  

**3. Kruskal–Wallis H Stat to P-Value**  

- **Upper-tailed only (since $H \ge 0$):**  

$$
p = \frac{\text{number of permutations where } H_{\text{perm}}^{(j)} \ge H_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**  

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.  

#### Scheirer–Ray–Hare (SRH) Test For Two-Way ANOVA Test

To detect whether there are differences between two or more different numerical & ordinal categorical groups on two different independent variables via Scheirer–Ray–Hare H stat.  

Scheirer–Ray–Hare stat (H) is:

$$
H = \frac{12}{N(N+1)} \sum_{j=1}^{k} \frac{R_j^2}{n_j} - 3(N+1)
$$

**Where:**  
- $H$ : Scheirer–Ray–Hare test statistic for each factor or interaction  
- $k$ : Number of levels for the factor or interaction  
- $n_j$ : Sample size for level $j$  
- $N = \sum_{j=1}^{k} n_j$ : Total sample size  
- $R_j$ : Sum of ranks for level $j$  

And its interpretation is:  

- $H \approx 0$ → the groups/levels are similar (no difference).  
- Large $H$ value → at least one group/level distribution tends to differ strongly from the others (large difference).  

It is Scheirer–Ray–Hare H-stat of sample and to inference for population, hypothesis test must be used.  

**1. Hypotheses**  

- **Null hypothesis (H0):** The population differences between two or more different numerical & ordinal categorical groups on two different independent variables **are not** significantly different.  
- **Alternative hypothesis (H1):** The population differences between two or more different numerical & ordinal categorical groups on two different independent variables **are** significantly different.  

**To reject H0** (that is, to accept H1), applying hypothesis test.  

**2. Scheirer–Ray–Hare H Stat via Resampling**  

Resampling simulations, such as permutation & bootstrap, can be used to recalculate H stats to get empirical probability distributions, not theoretical distributions like t-distribution.

Randomly shuffle the group labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute new H stats for each factor and interaction:  

$$
H_{\text{perm}}^{(j)} = \text{ScheirerRayHare}(X^{(j)}_{\text{levels}})
$$

Repeat this process N times (e.g., 10,000) to generate the null distribution of H under H0.  

**3. H Stat to P-Value**  

- **Upper-tailed only (since $H \ge 0$):**  

$$
p = \frac{\text{number of permutations where } H_{\text{perm}}^{(j)} \ge H_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**  

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.  

#### Friedman Test For One-Way Repeated Measures ANOVA Test

To detect whether there are differences between two or more repeated numerical & ordinal categorical measurements on the same group on an independent variable via Friedman (Q) stat.

Friedman test stat (Q) is:

$$
Q = \frac{12}{n k (k+1)} \sum_{j=1}^{k} R_j^2 - 3 n (k+1)
$$

**Where:**
- $Q$ : Friedman test stat
- $n$ : Number of subjects
- $k$ : Number of repeated measurements
- $R_j$ : Sum of ranks for measurement $j$ (across subjects)

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{Q}\ \textbf{value} & \textbf{Difference} \\
\hline
Q \approx 0 & \text{Repeated measurements are similar (no difference)} \\
\text{Large } Q & \text{At least one measurement tends to differ strongly from others (large difference)} \\
\end{array}
$$

It is Friedman Q-stat of sample and to infer for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between two or more repeated numerical & ordinal categorical measurements on the same group on an independent variable **are not** significantly different.
- **Alternative hypothesis (H1):** The population differences between two or more repeated numerical & ordinal categorical measurements on the same group on an independent variable **are** significantly different.

To reject H0 (accept H1), applying hypothesis test.

**2. Friedman Q Stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate Friedman Q stat to get empirical probability distributions, not theoretical distributions like t-distribution.

Also in repeated measures, block permutation must be used: each block retains its repeated measurements together. Permutation is applied across subjects to preserve the dependency structure.

Randomly shuffle the group labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute a new Friedman Q:

$$
Q_{\text{perm}}^{(j)} = \text{FriedmanTest}(X_1^{(j)}, X_2^{(j)}, \dots, X_k^{(j)})
$$

Repeat N times (e.g., 10,000) to generate null distribution of $Q$ under H0.

**3. Friedman Q Stat to P-Value**

- Upper-tailed only (since $Q \ge 0$):

$$
p = \frac{\text{number of permutations where } Q_{\text{perm}}^{(j)} \ge Q_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

$\alpha$ is generally 0.05–0.01.

#### Aligned Rank Transform Test For Two-Way Repeated Measures ANOVA Test

To detect whether there are differences between two or more repeated numerical & ordinal categorical groups on two different independent variables via $F_E$ stat.

$F_E$ stat is:

$$
F_E = \frac{MS_E}{MS_{\text{Error}}}
$$

**Where:**
- $F_E$ : F-statistic for effect $E$ (main effect A, main effect B, or interaction $A \times B$)
- $MS_E$ : Mean square of aligned ranks for effect $E$
- $MS_{\text{Error}}$ : Mean square of error

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F_E}\ \textbf{value} & \textbf{Difference} \\
\hline
F_E \approx 0 & \text{Aligned ranks of groups are similar (no effect)} \\
\text{Large } F_E & \text{At least one group differs strongly (significant effect)} \\
\end{array}
$$

It is an $F_E$ stat of sample and to infer for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between two or more repeated numerical & ordinal categorical groups on two different independent variables **are not** significantly different.
- **Alternative hypothesis (H1):** The population differences between two or more repeated numerical & ordinal categorical groups on two different independent variables **are** significantly different.

To reject H0 (accept H1), applying hypothesis test.

**2. $F_E$ Stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate $F_E$ stat to get empirical probability distributions, not theoretical distributions like t-distribution.

Also in repeated measures, block permutation must be used: each block retains its repeated measurements together. Permutation is applied across subjects to preserve the dependency structure.

Randomly shuffle the group labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute a new $F_E$:

$$
F_{\text{perm}}^{(j)} = \text{ART-ANOVA}(X^{(j)})
$$

Repeat N times (e.g., 10,000) to generate null distribution of $F_E$ under H0.

**3. $F_E$ Stat to P-Value**

- Upper-tailed only (since $F \ge 0$):

$$
p = \frac{\text{number of permutations where } F_{\text{perm}}^{(j)} \ge F_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

$\alpha$ is generally 0.05–0.01.

#### One-Way PERMANOVA Test For One-Way MANOVA Test

To detect whether there are differences between two or more different numerical & ordinal categorical groups on an independent variable & multiple dependent variables via PERMANOVA F-stat.

PERMANOVA F-stat is:

$$
F = \frac{\text{SS}_{\text{between}} / (k-1)}{\text{SS}_{\text{within}} / (N-k)}
$$

**Where:**

- $\text{SS}_{\text{between}}$: Sum of squares between groups (based on distance matrix)  
- $\text{SS}_{\text{within}}$: Sum of squares within groups (based on distance matrix)  
- $k$: Number of groups  
- $N$: Total sample size  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No difference between groups} \\
F > 1 & \text{Greater differences between groups} \\
\end{array}
$$

It is a PERMANOVA F-stat of sample and to infer for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between two or more different numerical & ordinal categorical groups on an independent variable & multiple dependent variables **are not** significantly different.  
- **Alternative hypothesis (H1):** The population differences between two or more different numerical & ordinal categorical groups on an independent variable & multiple dependent variables **are** significantly different.   

To reject H0 (accept H1), applying hypothesis test.

**2. PERMANOVA F Stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate PERMANOVA F stat to get empirical probability distributions, not theoretical distributions like t-distribution.

Randomly shuffle the group labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute a new PERMANOVA F:

$$
F_{\text{perm}}^{(j)} = \text{PERMANOVA}(X^{(j)})
$$

Repeat N times (e.g., 10,000) to generate null distribution of $F$ under H0.

**3. PERMANOVA F Stat to P-Value**

- Upper-tailed only (since $F \ge 0$):

$$
p = \frac{\text{number of permutations where } F_{\text{perm}}^{(j)} \ge F_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### Two-Way PERMANOVA Test For Two-Way MANOVA Test

To detect whether there are differences between two or more different numerical & ordinal categorical groups on two independent variables & multiple dependent variables via Two-Way PERMANOVA F-stat.

Two-Way PERMANOVA F-stat is:

$$
F = \frac{\text{SS}_{\text{effect}} / df_{\text{effect}}}{\text{SS}_{\text{residual}} / df_{\text{residual}}}
$$

**Where:**

- $\text{SS}_{\text{effect}}$: Sum of squares for the tested factor (Factor A, Factor B, or interaction A×B, based on distance matrix)  
- $\text{SS}_{\text{residual}}$: Sum of squares of residuals (within-group variation, based on distance matrix)  
- $df_{\text{effect}}$: Degrees of freedom of the tested factor  
- $df_{\text{residual}}$: Degrees of freedom of residuals  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{F}\ \textbf{value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No effect of factor or interaction} \\
F > 1 & \text{Greater effect of factor or interaction} \\
\end{array}
$$

It is a Two-Way PERMANOVA F-stat of sample and to infer for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between two or more different numerical & ordinal categorical groups on two independent variables & multiple dependent variables **are not** significantly different.  
- **Alternative hypothesis (H1):** The population differences between two or more different numerical & ordinal categorical groups on two independent variables & multiple dependent variables **are** significantly different.  

To reject H0 (accept H1), applying hypothesis test.

**2. Two-Way PERMANOVA F Stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate Two-Way PERMANOVA F stat to get empirical probability distributions, not theoretical distributions like t-distribution.

Randomly shuffle the group labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute a new PERMANOVA F:

$$
F_{\text{perm}}^{(j)} = \text{PERMANOVA}(X^{(j)})
$$

Repeat N times (e.g., 10,000) to generate null distribution of $F$ under H0.

**3. Two-Way PERMANOVA F Stat to P-Value**

- Upper-tailed only (since $F \ge 0$):

$$
p = \frac{\text{number of permutations where } F_{\text{perm}}^{(j)} \ge F_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:  

$$
p < \alpha
$$

Otherwise, fail to reject H0.  

Here, $\alpha$ is generally assumed as 0.05–0.01.

#### One-Way Repeated Measures PERMANOVA Test For One-Way Repeated Measures MANOVA Test

To detect whether there are differences between two or more repeated numerical & ordinal categorical groups on an independent variable & multiple dependent variables via F-stat.

F-stat is:

$$
F = \frac{\text{SS}_{\text{between}} / \text{df}_{\text{between}}}{\text{SS}_{\text{within}} / \text{df}_{\text{within}}}
$$

**Where:**
- $F$ : PERMANOVA F-stat
- $\text{SS}_{\text{between}}$ : Sum of squares between repeated factor levels (based on multiple dependent variables)
- $\text{SS}_{\text{within}}$ : Sum of squares within repeated factor levels
- $\text{df}_{\text{between}}$ : Degrees of freedom between factor levels ($k-1$, $k$ = number of repeated levels)
- $\text{df}_{\text{within}}$ : Degrees of freedom within ($N-k$, $N$ = total observations)

And its interpretation is:

$$
\begin{array}{c|l}
\textbf{F value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{Repeated multivariate measurements are similar (no difference)} \\
F > 1 & \text{At least one measurement tends to differ strongly from others (large difference)} \\
\end{array}
$$

It is F-stat of sample and to infer for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between two or more repeated numerical & ordinal categorical groups on an independent variable & multiple dependent variables **are not** significantly different.
- **Alternative hypothesis (H1):** The population differences between two or more repeated numerical & ordinal categorical groups on an independent variable & multiple dependent variables **are** significantly different.

To reject H0 (accept H1), applying hypothesis test.

**2. F-stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate F-stat to get empirical probability distributions, not only theoretical distributions like t-distributions.

Also in repeated measures, block permutation must be used: each block retains its repeated measurements together. Permutation is applied across subjects to preserve the dependency structure.

Randomly shuffle the condition labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute a new F-stat:

$$
F_{\text{perm}}^{(j)} = \frac{\text{SS}_{\text{between}}^{(j)} / \text{df}_{\text{between}}}{\text{SS}_{\text{within}}^{(j)} / \text{df}_{\text{within}}}
$$

Repeat N times (e.g., 10,000) to generate null distribution of F-stat under H0.

**3. F-Stat to P-Value**

- Upper-tailed test (since larger F indicates stronger effect):

$$
p = \frac{\text{number of permutations where } F_{\text{perm}}^{(j)} \ge F_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

$\alpha$ is generally 0.05–0.01.

#### Two-Way Repeated Measures PERMANOVA Test For Two-Way Repeated Measures MANOVA Test

To detect whether there are differences between two or more repeated numerical & ordinal categorical groups on two independent variables & multiple dependent variables via F-stat.

F-stat is:

$$
F = \frac{\text{SS}_{\text{effect}} / \text{df}_{\text{effect}}}{\text{SS}_{\text{residual}} / \text{df}_{\text{residual}}}
$$

**Where:**
- $F$ : PERMANOVA F-stat
- $\text{SS}_{\text{effect}}$ : Sum of squares for the tested factor (Factor A, Factor B, or interaction A×B, based on distance matrix)
- $\text{SS}_{\text{residual}}$ : Sum of squares of residuals (within-group variation, based on distance matrix)
- $\text{df}_{\text{effect}}$ : Degrees of freedom of the tested factor
- $\text{df}_{\text{residual}}$ : Degrees of freedom of residuals

And its interpretation is:

$$
\begin{array}{c|l}
\textbf{F value} & \textbf{Difference} \\
\hline
F \approx 1 & \text{No effect of factor or interaction (groups are similar)} \\
F > 1 & \text{Greater effect of factor or interaction (groups differ)} \\
\end{array}
$$

It is F-stat of sample and to infer for population, hypothesis test must be used.

**1. Hypotheses**

- **Null hypothesis (H0):** The population differences between two or more repeated numerical & ordinal categorical groups on two independent variables & multiple dependent variables **are not** significantly different.
- **Alternative hypothesis (H1):** The population differences between two or more repeated numerical & ordinal categorical groups on two independent variables & multiple dependent variables **are** significantly different.

To reject H0 (accept H1), applying hypothesis test.

**2. F-stat via Resampling**

Resampling simulations, such as permutation & bootstrap, can be used to recalculate F-stat to get empirical probability distributions, not only theoretical distributions like t-distributions.

Also in repeated measures, block permutation must be used: each block retains its repeated measurements together. Permutation is applied across subjects to preserve the dependency structure.

Randomly shuffle the condition labels across all observations. This simulates the null hypothesis H0, where no group differences exist.

For each permutation $j$, compute a new F-stat:

$$
F_{\text{perm}}^{(j)} = \frac{\text{SS}_{\text{effect}}^{(j)} / \text{df}_{\text{effect}}}{\text{SS}_{\text{residual}}^{(j)} / \text{df}_{\text{residual}}}
$$

Repeat N times (e.g., 10,000) to generate null distribution of F-stat under H0.

**3. F-stat to P-Value**

- Upper-tailed only (since $F \ge 0$):

$$
p = \frac{\text{number of permutations where } F_{\text{perm}}^{(j)} \ge F_{\text{obs}}}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

$\alpha$ is generally 0.05–0.01.

### Non-Parametric Test For Nominal Categorical Inter-Group

#### Cramer’s V With Chi-Square Homogeneity Test

To detect whether there is a difference between two nominal categorical groups via Cramer’s V coefficient.

Cramer’s V coefficient is:

$$
V = \sqrt{\frac{\chi^2}{n \cdot (k-1)}}
$$

**Where:**

- $V$: Cramér's V coefficient
- $\chi^2$: Chi-square homogeneity test stat
- $n$: Total number of observations  
- $r$: Number of rows in the contingency table  
- $c$: Number of columns in the contingency table  
- $k = \min(r, c)$: The smaller of the number of rows or columns  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{V}\ \textbf{value} & \textbf{Difference strength} \\
\hline
V = 0 & \text{No difference} \\
0 < V < 0.1 & \text{Negligible difference} \\
0.1 \le V < 0.3 & \text{Weak difference} \\
0.3 \le V < 0.5 & \text{Moderate difference} \\
V \ge 0.5 & \text{Strong difference} \\
\end{array}
$$

As is seen, Cramér's V measures only the strength of difference and does not provide information about direction like positive or negative because of that categorical variables do not have the concept of a “+” or “–” direction.

It is Cramér's V coefficient of sample and to inference for population, hypothesis test must be used.

Here some confused points, chi-square test will be used because of that Cramér's V coefficient is based on chi-square and chi-square test is nonparametric while chi-square distribution is parametric.

**1. Hypotheses**

**Null hypothesis (H0):** The two categorical groups are **not different**.

**Alternative hypothesis (H1):** The two categorical groups are **different**.

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Chi-Square Homogeneity Test Stat**

To standardize Cramér's V coefficient $V$ from sample to inference for population via X-stat because of V coefficient based on chi-square.

The X-stat $\chi^2$ is:

$$
\chi^2 = \sum_{i=1}^{r} \sum_{j=1}^{c} \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
$$

**Where:**

- $O_{ij}$ : Observed frequency in cell $(i,j)$
- $E_{ij}$ : Expected frequency in cell $(i,j)$
- $r$ : Number of rows
- $c$ : Number of columns

Like chi-square distribution, every parametric distribution has a **degrees of freedom (df)** value, and for the X-stat, that is, the X-distribution, **df = (r - 1)(c - 1)** where r means number of rows & c means number of columns.

**3. X-Test Stat to Distribution via PDF to CDF**

Under H0, the X-stat follows X-distribution and the probability density function (PDF) is:

$$
f_{\chi^2}(X^2; df) =
\dfrac{1}{2^{df/2}\Gamma(df/2)} \, (X^2)^{\frac{df}{2}-1} e^{-X^2/2}, \quad X^2 > 0
$$

To integrate PDF as the cumulative distribution function (CDF) is:

$$
F_{\chi^2}(X^2; df) = \int_{0}^{X^2} f_{\chi^2}(t; df) \, dt
$$

**4. CDF to P-Value**

$$
p\text = P(\chi^2_{df} \ge X^2) = 1 - F_{\chi^2}(X^2; df)
$$

As is seen, the chi-square distribution is one-sided because of that X-stat is based on squared differences, so it cannot take negative values. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a relationship and the lower-tailed test logic is not meaningful for chi-square.

**5. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

Here, $\alpha$ is theoretically assumed as 0.05-0.01 generally.

## INTER-VARIABLE ANALYSIS

### Parametric Test For Continuous Numerical Inter-Variables

#### Pearson Correlation Test

To detect whether there is a relationship between two continuous numerical variables via Pearson correlation coefficient.

Pearson correlation coefficient is:  

$$
r = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum_{i=1}^{n} (x_i - \bar{x})^2} \sqrt{\sum_{i=1}^{n} (y_i - \bar{y})^2}}
$$

**Where:**

- $r$: Pearson correlation coefficient  
- $n$: Number of paired observations  
- $x_i$: Value of variable $X$ at observation $i$  
- $y_i$: Value of variable $Y$ at observation $i$  
- $\bar{x}$: Mean of variable $X$  
- $\bar{y}$: Mean of variable $Y$  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{r}\ \textbf{value} & \textbf{Relationship} \\
\hline
r = 1 & \text{Perfect positive relationship} \\
0.7 \le r < 1 & \text{Strong positive relationship} \\
0.3 \le r < 0.7 & \text{Moderate positive relationship} \\
0 < r < 0.3 & \text{Weak positive relationship} \\
r = 0 & \text{No relationship} \\
-0.3 < r < 0 & \text{Weak negative relationship} \\
-0.7 < r \le -0.3 & \text{Moderate negative relationship} \\
-1 < r \le -0.7 & \text{Strong negative relationship} \\
r = -1 & \text{Perfect negative relationship} \\
\end{array}
$$

It is Pearson correlation of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population correlation coefficient **is not** significantly different from zero.

**Alternative hypothesis (H1):** The population correlation coefficient **is** significantly different from zero.

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Pearson Correlation Coefficient to Test Stat**

To standardize Pearson correlation coefficient $r$ from sample to inference for population via t-stat.

The t-stat derived from Pearson correlation coefficient $r$ is:

$$
t = \frac{r \sqrt{df}}{\sqrt{1-r^2}}
$$

Like t-distribution, every parametric distribution has a **degrees of freedom (df)** value, and for the t-stat, that is, the t-distribution, **df = n − 2**.

**3. Test Stat to Distribution via PDF to CDF**

Under H0, the t-stat follows t-distribution and the probability density function (PDF) is:

$$
f(t) = \frac{\Gamma\left(\frac{df+1}{2}\right)}{\sqrt{df \pi}\, \Gamma\left(\frac{df}{2}\right)} \left(1 + \frac{t^2}{df}\right)^{-\frac{df+1}{2}}
$$

To integrate PDF to t as the cumulative distribution function (CDF) is:

$$
F(t) = \int_{-\infty}^{t} f(u)\,du
$$

**4. CDF to P-Value**

$$
F(t) = P(T \le t)
$$

It means the probability of values less than or equal to t.

- **One-Tailed:**  
  - Used when H0: parameter ≤ value, H1: parameter > value as **upper-tailed test** and the “extreme values” of interest are greater than t. Therefore, the p-value is:

$$
p = 1 - F(t)
$$

  - Used when H0: parameter ≥ value, H1: parameter < value as **lower-tailed test** and therefore, the p-value is directly:

$$
p = F(t)
$$

- **Two-Tailed:**  

  - Used when H0: parameter = value, H1: parameter ≠ value (i.e., "different") and to cover extreme values in both the upper and lower tails by using absolute value of t and formula multiplication by 2. Therefore, the p-value is:

$$
p = 2 \cdot (1 - F(|t|))
$$

**5. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

Here, $\alpha$ is theoretically assumed as 0.05-0.01 generally.

### Non-Parametric Test For Numerical & Ordinal Categorical Inter-Variables

#### Spearman Rank Correlation Test

To detect whether there is a relationship between two numerical & ordinal categorical variables via Spearman rank correlation coefficient.

Spearman rank correlation coefficient is:

$$
\rho_s = 1 - \frac{6 \sum_{i=1}^{n} d_i^2}{n(n^2 - 1)}
$$

**Where:**
- $\rho_s$ : Spearman rank correlation coefficient
- $n$ : Number of paired observations
- $d_i$ : Difference between the ranks of $x_i$ and $y_i$
- $x_i, y_i$ : Values of variables $X$ and $Y$ at observation $i$ (converted to ranks)

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{\rho_s}\ \textbf{value} & \textbf{Relationship} \\
\hline
\rho_s = 1 & \text{Perfect positive relationship} \\
0.7 \le \rho_s < 1 & \text{Strong positive relationship} \\
0.3 \le \rho_s < 0.7 & \text{Moderate positive relationship} \\
0 < \rho_s < 0.3 & \text{Weak positive relationship} \\
\rho_s = 0 & \text{No relationship} \\
-0.3 < \rho_s < 0 & \text{Weak negative relationship} \\
-0.7 < \rho_s \le -0.3 & \text{Moderate negative relationship} \\
-1 < \rho_s \le -0.7 & \text{Strong negative relationship} \\
\rho_s = -1 & \text{Perfect negative relationship} \\
\end{array}
$$

It is Spearman correlation of sample and to inference for population, hypothesis test must be used.

**1. Hypotheses**

**Null hypothesis (H0):** The population Spearman correlation coefficient **is not** significantly different from zero.

**Alternative hypothesis (H1):** The population Spearman correlation coefficient **is** significantly different from zero.

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Spearman Rank Correlation Coefficient via Resampling**

Resampling simulations, such as permutation & bootstrap can be used to recalculate Spearman rank correlation coefficient to get empirical probability distributions, not theoretical distributions like t-distribution.

Randomly shuffle the Y variable to break any existing relation between X and Y. This simulates the null hypothesis H0, where no relationship exists.

For each permutation j, to compute a new Spearman rank correlation coefficient:

$$
\rho_{\text{perm}}^{(j)} = \text{SpearmanRankCorr}(X, Y_{\text{shuffled}}^{(j)})
$$

Repeat this process N times (e.g., 10,000) to generate the null distribution of correlation coefficients under H0.

**3. Spearman Rank Correlation Coefficients to P-Value**

- **One-Tailed:**  
  - Used when H0: parameter ≤ value, H1: parameter > value as **upper-tailed test** and considered only extreme values greater than the observed correlation. Therefore, the p-value is:

$$
p = \frac{\text{number of permutations where } \rho_{\text{perm}}^{(j)} \ge \rho_{\text{obs}}}{N}
$$

  - Used when H0: parameter ≥ value, H1: parameter < value as **lower-tailed test** and considered only extreme values smaller than the observed correlation. Therefore, the p-value is:

$$
p = \frac{\text{number of permutations where } \rho_{\text{perm}}^{(j)} \le \rho_{\text{obs}}}{N}
$$

- **Two-Tailed:**  

  - Used when H0: parameter = value, H1: parameter ≠ value (i.e., "different") and compared the absolute values to account for extreme values in both directions. Therefore, the p-value is:

$$
p = \frac{\text{number of permutations where } |\rho_{\text{perm}}^{(j)}| \ge |\rho_{\text{obs}}|}{N}
$$

**4. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

Here, $\alpha$ is theoretically assumed as 0.05-0.01 generally.

### Non-Parametric Test For Nominal Categorical Inter-Variables

#### Cramer’s V With Chi-Square Independence Test

To detect whether there is a relationship between two nominal categorical variables via Cramer’s V coefficient.

Cramer’s V coefficient is:

$$
V = \sqrt{\frac{\chi^2}{n \cdot (k-1)}}
$$

**Where:**

- $V$: Cramér's V coefficient
- $\chi^2$: Chi-square independence test stat
- $n$: Total number of observations  
- $r$: Number of rows in the contingency table  
- $c$: Number of columns in the contingency table  
- $k = \min(r, c)$: The smaller of the number of rows or columns  

And its interpretation is:

$$
\begin{array}{c|l}
\mathbf{V}\ \textbf{value} & \textbf{Relationship strength} \\
\hline
V = 0 & \text{No relationship} \\
0 < V < 0.1 & \text{Negligible relationship} \\
0.1 \le V < 0.3 & \text{Weak relationship} \\
0.3 \le V < 0.5 & \text{Moderate relationship} \\
V \ge 0.5 & \text{Strong relationship} \\
\end{array}
$$

As is seen, Cramér's V measures only the strength of relationship and does not provide information about direction like positive or negative because of that categorical variables do not have the concept of a “+” or “–” direction.

It is Cramér's V coefficient of sample and to inference for population, hypothesis test must be used.

Here some confused points, chi-square test will be used because of that Cramér's V coefficient is based on chi-square and chi-square test is nonparametric while chi-square distribution is parametric.

**1. Hypotheses**

**Null hypothesis (H0):** The two categorical variables are **not dependent**.

**Alternative hypothesis (H1):** The two categorical variables are **dependent**.

**To reject H0** (that is, to accept H1), applying hypothesis test.

**2. Chi-Square Independence Test Stat**

To standardize Cramér's V coefficient $V$ from sample to inference for population via X-stat because of V coefficient based on chi-square.

The X-stat $\chi^2$ is:

$$
\chi^2 = \sum_{i=1}^{r} \sum_{j=1}^{c} \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
$$

**Where:**

- $O_{ij}$ : Observed frequency in cell $(i,j)$
- $E_{ij}$ : Expected frequency in cell $(i,j)$
- $r$ : Number of rows
- $c$ : Number of columns

Like chi-square distribution, every parametric distribution has a **degrees of freedom (df)** value, and for the X-stat, that is, the X-distribution, **df = (r - 1)(c - 1)** where r means number of rows & c means number of columns.

**3. X-Test Stat to Distribution via PDF to CDF**

Under H0, the X-stat follows X-distribution and the probability density function (PDF) is:

$$
f_{\chi^2}(X^2; df) =
\dfrac{1}{2^{df/2}\Gamma(df/2)} \, (X^2)^{\frac{df}{2}-1} e^{-X^2/2}, \quad X^2 > 0
$$

To integrate PDF as the cumulative distribution function (CDF) is:

$$
F_{\chi^2}(X^2; df) = \int_{0}^{X^2} f_{\chi^2}(t; df) \, dt
$$

**4. CDF to P-Value**

$$
p\text = P(\chi^2_{df} \ge X^2) = 1 - F_{\chi^2}(X^2; df)
$$

As is seen, the chi-square distribution is one-sided because of that X-stat is based on squared differences, so it cannot take negative values. Therefore, the upper-tailed test logic is used: the larger the observed value, the higher the likelihood of a relationship and the lower-tailed test logic is not meaningful for chi-square.

**5. P-Value vs $\alpha$**

To reject H0 if:

$$
p < \alpha
$$

Otherwise, fail to reject H0.

Here, $\alpha$ is theoretically assumed as 0.05-0.01 generally.
