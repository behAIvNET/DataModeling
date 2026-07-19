# DATA PRE-PROCESSING

**Data**: There are five basic types of data:

-   **Numerical:** Data that are expressed via numbers.
    -   **Continuous:** Numbers that can take on any value in an
        interval, such as decimal numbers.
    -   **Discrete:** Numbers that can take on only integer values, such
        as counts.
-   **Categorical:** Data that are expressed via words.
    -   **Binary:** Words that can take just two categories of values,
        such as true/false.
    -   **Ordinal:** Words that can take an explicit ordering, such as
        low/medium/high.
    -   **Nominal:** Words that can take a non-ordering, such as nouns.

**Structured Data:** One of the commonest forms of structured data is a
table with rows and columns.

-   **Data frame:** A table is the basic data structure with rows and
    columns.
    -   **Feature:** A column within a table is commonly referred to as
        a feature.
    -   **Records:** A row within a table is commonly referred to as a
        record.
    -   **Index:** A table have one or more columns with a row number.

There are also other data structures besides data frame, such as time
series data, spatial data, graph/network data etc.

**Data Pre-Processing:** It means processing the structured data before
the analysis (EDA or CDA) and can be levelized hierarchically into 4
levels as **viewing, filtering, cleaning & encoding**.

# EXPLORATORY DATA ANALYSIS

EDA means analysis via **DESCRIPTIVE STATS & PLOTS**.

And the analysis via descriptive stats & plots can be categorized in 3
types hierarchically as **univariate, bivariate & multivariate
analysis**.

## UNIVARIATE ANALYSIS

Firstly, there are 3 basic levels in univariate analysis: **tendency,
dispersion & distribution** with 3 basic aspects as **parametricity,
trimed parametricity & non-parametricity**.

First level is the estimation of where most of the data is located as
**central tendency** and there is no also non-central tendency
naturally.

Central tendency covers mean vs median & mode.

The key difference between mean vs median & mode is that mean is
sensitive to outlier data but median & mode are robust.

Being sensitive to outliers called parametric, while being robust to
outliers called non-parametric but trimming (removing the lowest &
highest 5-20% of data) can be used to be robust for parametrics as
trimmed parametric.

In continuous & discrete numerical data; if mean is very different from
median & mode, trimmed mean can be applied to be robust the mean by
closing from parametric value to non-parametric value.

If the outliers are important in the analysis, trimming cannot be used
and the non-parametric value can be used directly.

**Parametric Central Tendency**

**Mean:** The sum of all values divided by the number of values in the
continuous & discrete numerical data.

$$
\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}
$$

Where:

-   $\bar{x}$ : Mean (average value)
-   $x_i$ : The $i^{th}$ observation (data point)
-   $n$ : Total number of observations (sample size)
-   $\sum$ : Summation symbol (sum of all values from $i=1$ to $n$)

**Non-Parametric Central Tendency**

**Median:** The value such that one-half of the data lies above and
below in the ordinal categorical data in addtion to continuous &
discrete numerical data.

$$
\text{Median} =
\begin{cases}
x_{\left(\frac{n+1}{2}\right)}, & \text{if } n \text{ is odd} \\
\frac{x_{\left(\frac{n}{2}\right)} + x_{\left(\frac{n}{2}+1\right)}}{2}, & \text{if } n \text{ is even}
\end{cases}
$$

Where:

-   $\text{Median}$ : The middle value of the ordered data
-   $x_{(k)}$ : The $k^{th}$ smallest observation (data sorted in
    ascending order)
-   $n$ : Total number of observations

**Mode:** It is the value that appears most often in the binary &
nominal categorical data in addition to continuous & discrete numerical
data.

**Trimmed Parametric Central Tendency**

**Trimmed Mean:** It is the mean without outliers.

$$
\text{Trimmed Mean} = \frac{1}{n - 2k} \sum_{i=k+1}^{n-k} x_{(i)}
$$

**Where:** - $x_{(i)}$ are the data sorted in ascending order
- $n$ is the total number of observations
- $k$ is the number of values trimmed from each end

Second level is the measurement whether the data are tightly clustered
or spread out as **central dispersion** and there is also non-central
dispersion.

Central dipersion covers mean absolute deviation and its derrivatives as
variance & standard deviation vs mean absolute deviation from median and
there is also no central dispersion measurement for mode naturally.

The key difference between mean absolute deviation and its derrivatives
as variance & standard deviation vs mean absolute deviation from median
is that mean absolute deviation and its derrivatives as variance &
standard deviation is sensitive to outlier data but median & mean
absolute deviation from median is robust.

Being sensitive to outliers called parametric, while being robust to
outliers called non-parametric but trimming (removing the lowest &
highest 5-20% of data) can be used to be robust for parametrics as
trimmed parametric.

In continuous & discrete numerical data; if mean absolute deviation is
very different from mean absolute deviation from median, trimmed
variance & standart deviation can be apllied to be robust the variance &
standart deviation by closing from parametric value to non-parametric
value.

If the outliers are important in the analysis, trimming cannot be used
and the non-parametric value can be used directly.

Non-central dispersion is also non-parametric naturally.

**Parametric Central Dispersion**

**Mean Absolute Deviation (MnAD):** It is the sum of the absolute
deviations from the mean divided by n, where n is the number of data.

$$
\text{MnAD} = \frac{1}{n} \sum_{i=1}^{n} \left| x_i - \bar{x} \right|
$$

**Where:** - $x_i$ are the individual data points
- $\bar{x}$ is the mean of the data
- $n$ is the total number of observations

To overcome the differentiability limitation of MnAD because of
absolution, taking square can be used as variance.

**Variance:** It is the sum of squared deviations from the mean divided
by n -- 1 where n is the number of data and is used to show how much the
data in a dataset vary from each other.

$$
s^{2} = \frac{\sum_{i=1}^{n} \left(x_i - \bar{x}\right)^{2}}{n - 1}
$$

Where:

-   $s^{2}$ : Sample variance
-   $x_i$ : The $i^{th}$ observation (data point)
-   $\bar{x}$ : Sample mean (average of the observations)
-   $n$ : Total number of observations
-   $\sum$ : Summation symbol (adds up all squared deviations)
-   $n - 1$ : Adjusted sample size

To overcome the square of unit limitation of variance because of taking
square, taking square root of variance can be used as standard
deviation.

**Standard Deviation:** It is the square root of the variance and is
used to show how far apart the data in a dataset are from the mean.

$$
s = \sqrt{\frac{\sum_{i=1}^{n} \left(x_i - \bar{x}\right)^{2}}{n - 1}}
$$

Where:

-   $s$ : Sample standard deviation
-   $x_i$ : The $i^{th}$ observation (data point)
-   $\bar{x}$ : Sample mean
-   $n$ : Total number of observations
-   $\sum$ : Summation symbol (adds up all squared deviations)
-   $n - 1$ : Adjusted sample size

**Non-Parametric Central Dispersion**

**Median Absolute Deviation (MdAD):** It is the median of the absolute
deviations from the median.

$$
\text{MdAD} = \frac{1}{n} \sum_{i=1}^{n} \Big| X_i - \text{median}(X) \Big|
$$

Where:
- $X_i$ : The $i^{th}$ observation (data point)
- $\text{median}(X)$ : The median of the data set $X$
- $n$ : Total number of observations
- $\sum$ : Summation symbol (adds up all absolute deviations)

**Trimmed Parametric Central Tendency**

**Trimmed Variance**

$$
s_t^{2} = \frac{\sum_{i=1}^{n_t} \left(x_i - \bar{x}_t\right)^{2}}{n_t - 1}
$$

Where:

-   $s_t^{2}$ : Trimmed sample variance
-   $x_i$ : The $i^{th}$ observation after trimming
-   $\bar{x}_t$ : Trimmed mean (mean of the remaining data after
    removing extremes)
-   $n_t$ : Number of observations after trimming
-   $\sum$ : Summation symbol (adds up all squared deviations)
-   $n_t - 1$ : Adjusted sample size after trimming

**Trimmed Standard Deviation**

$$
s_t = \sqrt{\frac{\sum_{i=1}^{n_t} \left(x_i - \bar{x}_t\right)^{2}}{n_t - 1}}
$$

Where:

-   $s_t$ : Trimmed sample standard deviation
-   $x_i$ : The $i^{th}$ observation after trimming
-   $\bar{x}_t$ : Trimmed mean (mean of remaining data after removing
    extremes)
-   $n_t$ : Number of observations after trimming
-   $\sum$ : Summation symbol (adds up all squared deviations)
-   $n_t - 1$ : Adjusted sample size after trimming

**Non-Central Dispersion**

**Range:** The difference between the largest and the smallest value in
a data set.

$$
\text{Range} = \max(x_i) - \min(x_i)
$$

Where:

-   $\text{Range}$ : The spread of the data
-   $\max(x_i)$ : The largest value in the dataset
-   $\min(x_i)$ : The smallest value in the dataset
-   $x_i$ : The $i^{th}$ observation (data point)

**Percentile:** The value such that P percent of the values take on this
value or less and (100--P) percent take on this value or more.

$$
P_{p} = x_{\left( \lceil \tfrac{p}{100} \cdot n \rceil \right)}
$$

Where:

-   $P_{p}$ : The $p^{th}$ percentile
-   $p$ : Desired percentile (e.g., $p=25$ for 25th percentile)
-   $x_{(k)}$ : The $k^{th}$ smallest observation (data sorted in
    ascending order)
-   $n$ : Total number of observations
-   $\lceil \cdot \rceil$ : Ceiling function (rounds up to the nearest
    integer)

**Interquartile Range:** The difference between the 75th percentile and
the 25th percentile.

$$
\text{IQR} = Q_{3} - Q_{1}
$$

Where:

-   $\text{IQR}$ : Interquartile Range
-   $Q_{1}$ : First quartile (25th percentile)
-   $Q_{3}$ : Third quartile (75th percentile)

Third level is the estimation of shape of all data as **distribution**.

Distribution covers skewness & kurtosis vs Bowley's skewness & Moors
kurtosis.

The key difference between skewness & kurtosis vs Bowley's skewness &
Moors kurtosis is that skewness & kurtosis are sensitive to outlier data
but Bowley's skewness & Moors kurtosis are robust.

Being sensitive to outliers called parametric, while being robust to
outliers called non-parametric but trimming (removing the lowest &
highest 5-20% of data) can be used to be robust for parametrics as
trimmed parametric.

In continuous & discrete numerical data; if skewness & kurtosis is very
different from Bowley's skewness & Moors kurtosis, trimmed skewness &
kurtosis can be apllied to be robust the skewness & kurtosis by closing
from parametric value to non-parametric value.

If the outliers are important in the analysis, trimming cannot be used
and the non-parametric value can be used directly.

**Parametric Distribution**

**Parametric Skewness**

$$
g_1 = \frac{\frac{1}{n}\sum_{i=1}^n (x_i - \bar{x})^3}{\left(\frac{1}{n}\sum_{i=1}^n (x_i - \bar{x})^2\right)^{3/2}}
$$

Where:
- $g_1$ : Parametric skewness
- $x_i$ : $i^{th}$ observation
- $\bar{x}$ : Sample mean
- $n$ : Sample size

**Parametric Kurtosis**

$$
g_2 = \frac{\frac{1}{n}\sum_{i=1}^n (x_i - \bar{x})^4}{\left(\frac{1}{n}\sum_{i=1}^n (x_i - \bar{x})^2\right)^{2}}
$$

Where:
- $g_2$ : Parametric kurtosis
- $x_i$ : $i^{th}$ observation
- $\bar{x}$ : Sample mean
- $n$ : Sample size

**Non-Parametric Distribution**

**Non-Parametric Skewness**

(Bowley's Quartile Skewness)

$$
Q_s = \frac{(Q_3 + Q_1 - 2Q_2)}{Q_3 - Q_1}
$$

Where:
- $Q_s$ : Bowley's non-parametric skewness
- $Q_1$ : First quartile
- $Q_2$ : Median (second quartile)
- $Q_3$ : Third quartile

**Non-Parametric Kurtosis**

(Moors Kurtosis)

$$
K_M = \frac{(P_{87.5} - P_{62.5}) + (P_{37.5} - P_{12.5})}{P_{75} - P_{25}}
$$

Where:
- $K_M$ : Moors non-parametric kurtosis
- $P_{p}$ : $p^{th}$ percentile (e.g. $P_{87.5}$ is 87.5th percentile)

**Trimmed Parametric Distribution**

**Trimmed Parametric Skewness**

$$
g_{1t} = \frac{\frac{1}{n-2k}\sum_{i=k+1}^{n-k}(x_{(i)} - \bar{x}_t)^3}{\left(\frac{1}{n-2k}\sum_{i=k+1}^{n-k}(x_{(i)} - \bar{x}_t)^2\right)^{3/2}}
$$

Where:
- $g_{1t}$ : Trimmed skewness
- $x_{(i)}$ : Ordered observation
- $\bar{x}_t$ : Trimmed mean
- $n$ : Sample size
- $k$ : Trimmed observations per tail

**Trimmed Parametric Kurtosis**

$$
g_{2t} = \frac{\frac{1}{n-2k}\sum_{i=k+1}^{n-k}(x_{(i)} - \bar{x}_t)^4}{\left(\frac{1}{n-2k}\sum_{i=k+1}^{n-k}(x_{(i)} - \bar{x}_t)^2\right)^{2}}
$$

Where:
- $g_{2t}$ : Trimmed kurtosis
- $x_{(i)}$ : Ordered observation
- $\bar{x}_t$ : Trimmed mean
- $n$ : Sample size
- $k$ : Trimmed observations per tail

Until now, **descriptive stats** can be covered and since now **plots**
will be covered in EDA.

Distribution represents as these plots hierarchically:

**Frequency Table:** A table of the count of values that fall into a set
of numeric scale or categories.

**Bar Chart:** It is based on frequency (as y-axis) and the x-axis
represents different categories of a factor variable.

**Histogram:** It is based on frequency (as y-axis) and the x-axis
represents different numeric scales of a factor variable.

Note that a bar chart resembles a histogram; in a histogram, the bars
are typically shown touching each other, with gaps indicating values
that did not occur in the data. In a bar chart, the bars are shown
separate from one another. Bar charts should not be confused with
histograms.

**Distribution Plot:** It is based on histogram with 2 different
distributions; such as real & test distributions.

**Real distributions** based on real data points when **test
distributions** lied on (hypothesis) tests' data points.

**Real distributions** can be seperated as **single** to **multiple**
trial distributions hierarchically based on five basic outcome types
respectively; **single, two, multiple, unlimited (for discretes) &
infinite (for continuouses)** outcomes and all real distributions are
**parametric distribution**.

| **Trial Type** | **Outcome Type** | **Distribution** |
|----------------|------------------|------------------|
| Single trial | Single outcome | Certainty |
| Single trial | Two outcomes | Bernoulli |
| Single trial | Multiple outcomes | Categorical |
| Single trial | Unlimited outcomes | Poisson |
| Single trial | Infinite outcomes | Normal |
| Multiple trials | Single outcome | Uniform |
| Multiple trials | Two outcomes | Binomial |
| Multiple trials | Multiple outcomes | Multinomial |
| Multiple trials | Unlimited outcomes | Poisson |
| Multiple trials | Infinite outcomes | Normal |

As is seen, **normal distribution** as main parametric distribution in
data science that based on central limit theorem that said that the
tendency of the sampling distribution to take on a normal shape as
sample size rises.

**Normal & Standard Normal Distribution:** Standart distribution
represents 68% of the data lies within one standard deviation of the
mean, and 95% lies within two standard deviations.

To transform normal distribution to a standard normal distribution, you
subtract the mean and then divide by the standard deviation; this is
also called standardization and the transformed value of n-th original
data point is termed a **z-score** of n-th original data point.

$$
Z_n = \frac{X_n - \mu}{\sigma}
$$

**Where:** - $Z_n$ : z-score of the n-th data point
- $X_n$ : n-th original data point
- $\mu$ : mean of the distribution
- $\sigma$ : standard deviation of the distribution

**Density Plot:** A smoothed version of the histogram of the normal
distribution, based on a kernel density estimate.

**QQ-Plots:** They can be used to detect **normal-like vs normal
distributions**.

A QQ-Plot is used to visually determine how close a sample is to the
normal distribution.

The QQ-Plot orders the z-scores from low to high and plots each value's
z-score on the y-axis; the x-axis is the corresponding theoretical
quantile of a normal distribution for that value's rank.

Since the data is normalized, the units correspond to the number of
standard deviations away from the mean.

If the points roughly fall on the diagonal line, then the sample
distribution can be considered close to normal.

There are also **anti-normal parametric distributions** (never to close
the normal) such as Cauchy, log-normal, exponential & Pareto
distributions hierarchically familiar to unfamiliar to Normal
distribution.

Moreover, **test distributions** such as t-distribution, F-distribution,
chi-square distribution & their trimmed derivatives can be covered in
confirmatory data analysis (CDA) as **parametric & trimmed parametric
distributions** and Wilcoxon, Mann-Whitney U, Kruskal-Wallis H &
Friedman distributions can also be covered in confirmatory data analysis
(CDA) as **non-parametric distributions**, not here (exploratory data
analysis (EDA)).

## BIVARIATE ANALYSIS

Bivariate analysis can be groupped into 3 groups by combination of
numerical vs categorical as **numerical vs numerical**, **categorical vs
categorical** & **categorical vs numerical**.

**NUMERICAL VS NUMERICAL**

**Scatterplot** is a plot in which the x-axis is the value of one
variable, and the y-axis the value of another.

Scatterplots are fine when there is a relatively small number of data
values but for data sets with hundreds of thousands or millions of
records, a scatterplot will be too dense, so we need a different ways to
visualize the relationship such as hexagonal binning & contour plot.

**Hexagonal Binning:** A plot of two numeric variables with the records
binned into hexagons.

**Heatmap:** A plot showing the density of two numeric variables with
different colors red to blue as lower density.

**Contour Plot:** A plot showing the density of two numeric variables
with 3-D lines like a topographical map.

**CATEGORICAL VS CATEGORICAL**

A useful way to summarize two categorical variables is a **contingency
table** that is a table of counts by category.

**CATEGORICAL VS NUMERICAL**

**Boxplot** is also a simple way to visually compare the distributions
of a numeric variable grouped according to a categorical variable, that
is the plot that based on percentiles to compare more than one
distribution side by side:

-   The top and bottom of the box are the 75th and 25th percentiles,
    respectively.

-   The median is shown by the horizontal line in the box.

-   The dashed lines, referred to as whiskers, extend from the top and
    bottom of the box to indicate the range for the bulk of the data.

-   Any data outside of the whiskers is plotted as single points or
    circles (often considered outliers).

Moreover, a **violin plot** is an enhancement to the boxplot and plots
the density estimate with the density on the y-axis. The density is
mirrored and flipped over, and the resulting shape is filled in,
creating an image resembling a violin.

The advantage of a violin plot is that it can show nuances in the
distribution that aren't perceptible in a boxplot. On the other hand,
the boxplot more clearly shows the outliers in the data.

## MULTIVARIATE ANALYSIS

**Faceting** is the concept of splitting the data into subplots based
more variables. In other words, by creating multiple small plots within
a single figure; each small plot represents a specific category or
combination of variables.
