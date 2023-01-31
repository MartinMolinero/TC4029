

## Kumar Mukhiya, S., y Ahmed, U. (2020). Hands-On Exploratory Data Analysis with Python

### The significance of EDA
- Different fields of science, economics, engineering, and marketing accumulate and store data primarily in electronic databases. Appropriate and well-established decisions should be made using the data collected
- Exploratory data analysis is key, and usually the first exercise in data mining. It allows us to visualize data to understand it as well as to create hypotheses for further analysis. The exploratory analysis centers around creating a synopsis of data or insights for the next steps in a data mining project.
- EDA actually reveals ground truth about the content without making any underlying assumptions. This is the fact that data scientists use this process to actually understand what type of modeling and hypotheses can be created. Key components of exploratory data analysis include summarizing data, statistical analysis, and visualization of data.

### Making sense of data
- A dataset contains many observations about a particular object. For instance, a dataset about patients in a hospital can contain many observations. 

### Measures of central tendency
- The measure of central tendency tends to describe the average or mean value of datasets that is supposed to provide an optimal summarization of the entire set of measurements

### Measures of dispersion
- The second type of descriptive statistics is the measure of dispersion, also known as a measure of variability. It is used to describe the variability in a dataset, which can be a sample or population. It is usually used in conjunction with a measure of central tendency, to provide an overall description of a set of data.

- In simple language, the standard deviation is the average/mean of the difference between each value in the dataset with its average/mean; that is, how data is spread out from the mean

- Variance is the square of the average/mean of the difference between each value in the dataset with its average/mean; that is, it is the square of standard deviation.

- In probability theory and statistics, skewness is a measure of the asymmetry of the variable in the dataset about its mean.
- The graph on the right-hand side has a tail that is longer than the tail on the right-hand side. This indicates that the distribution of the data is skewed to the left. If you select any point in the left-hand longer tail, the mean is less than the mode. This condition is referred to as negative skewness.
- The graph on the left-hand side has a tail that is longer on the right-hand side. If you select any point on the right-hand tail, the mean value is greater than the mode. This condition is referred to as positive skewness.
- The graph in the middle has a right-hand tail that is the same as the left-hand tail. This condition is referred to as a symmetrical condition.

- Basically, kurtosis is a statistical measure that illustrates how heavily the tails of distribution differ from those of a normal distribution.
- Kurtosis, unlike skewness, is not about the peakedness or flatness. It is the measure of outlier presence in a given distribution. Both high and low kurtosis are an indicator that data needs further investigation. The higher the kurtosis, the higher the outliers.

- Mesokurtic: If any dataset follows a normal distribution, it follows a mesokurtic distribution. It has kurtosis around 0.
- Leptokurtic: In this case, the distribution has kurtosis greater than 3 and the fat tails indicate that the distribution produces more outliers.
- Platykurtic: In this case, the distribution has negative kurtosis and the tails are very thin compared to the normal distribution


- Percentiles measure the percentage of values in any dataset that lie below a certain value. In order to calculate percentiles, we need to make sure our list is sorted

- Given a dataset sorted in ascending order, quartiles are the values that split the given dataset into quarters. Quartiles refer to the three data points that divide the given dataset into four equal parts, such that each split makes 25% of the dataset. In terms of percentiles, the 25th percentile is referred to as the first quartile (Q1), the 50th percentile is referred to as the second quartile (Q2), and the 75th percentile is referred to as the third quartile (Q3).


## McKinney, W. (2022). Python for Data Analysis (3rd ed.). O´Reilly Media

### Introducing correlation
- The columns of a dataset are, most probably, related to one another because they are collected from the same event. One field of record may or may not affect the value of another field.
- The strength of such a relationship between two fields of a dataset is called correlation, which is represented by a numerical value between -1 and 1.
- Correlation tells us how variables change together, both in the same or opposite directions and in the magnitude (that is, strength) of the relationship. To find the correlation, we calculate the Pearson correlation coefficient, symbolized by ρ (the Greek letter rho). This is obtained by dividing the covariance by the product of the standard deviations of the variables:
- In terms of the strength of the relationship, the value of the correlation between two variables, A and B, varies between +1 and -1. If the correlation is +1, then it is said to be a perfect positive/linear correlation (that is, variable A is directly proportional to variable B), while a correlation of -1 is a perfect negative correlation (that is, variable A is inversely proportional to variable B).

### Understanding bivariate analysis
-  When we create a scatter plot by plotting one variable against another on a Cartesian plane (think of the x and y axes), it gives us a picture of what the data is trying to tell us. If the data points seem to fit the line or curve, then there is a relationship or correlation between the two variables. Generally, bivariate analysis helps us to predict a value for one variable (that is, a dependent variable) if we are aware of the value of the independent variable.


### Understanding multivariate analysis

### Discussing multivariate analysis using the Titanic dataset