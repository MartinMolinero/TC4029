# Ingeniería de características

## Contexto
- El aumento en la precisión de los modelos de aprendizaje automático siempre es una prioridad para los científicos de datos. Pero este proceso de perfeccionamiento y ajuste para producir resultados precisos, está asociado en primera instancia con disponer de un conjunto óptimo de variables. Es aquí donde interviene la ingeniería de características (o FE por sus siglas en inglés: Feature Engineering), para convertir observaciones sin procesar en características deseadas.
- Escalamiento (Scaling): Se estandariza el rango de las variables independientes o características. También se conoce como normalización.
    - Escalamiento Z-score / estandarización / transformación gaussiana
    - Escalamiento Min-Max
    - Escalamiento Robusto
- Discretización (Binning): Se transforman las variables continuas en discretas mediante la creación de un conjunto de intervalos contiguos que abarca el rango de valores de la variable.
    - Agrupación (bins) de igual tamaño
    - Agrupación (bins) de igual frecuencia
    - Agrupación por K-means: Se usa el algoritmo k-means para particionar valores en grupos.
    - Agrupación usando árboles de decisión: Se utiliza un árbol de decisión para identificar los puntos de división óptimos que determinarían los contenedores.
- Codificación (Encoding): Se transforman las variables categóricas en números para que los algoritmos puedan manejar esos valores.
    - Codificación Ordinal
    - Codificación One-hot
    - Codificación binaria
- Transformación: Se reemplazan los valores originales de las variables con una función matemática de esa variable. Las transformaciones intentan llevar la distribución de la variable a una forma más simétrica, es decir, gaussiana.
    - Transformación logarítmica
    - Transformación recíproca
    - Transformación raíz cuadrada
    - Transformación exponencial
    - Transformación Box-Cox
    - Transformación Yeo-Johnson
- Generación: Se crean nuevas características como una combinación de las existentes. Es una excelente manera de agregar conocimientos de dominio al conjunto de datos.
    - Funciones matemáticas
    - Estadísticas 

## Raschka, S. (2014, julio 11). About Feature Scaling and Normalization – and the effect of standardization for machine learning algorithms. sebastianraschka.

### standardization
- The result of standardization (or Z-score normalization) is that the features will be rescaled so that they’ll have the properties of a standard normal distribution with
- Standardizing the features so that they are centered around 0 with a standard deviation of 1 is not only important if we are comparing measurements that have different units, but it is also a general requirement for many machine learning algorithms.
- Algorithms that need it:
    - knn
    - kmeans
    - Log reg
    - Linear discriminant

### min max
- between 0-1 values

### STD VS MINMAX
- For example, in clustering analyses, standardization may be especially crucial in order to compare similarities between features based on certain distance measures. Another prominent example is the Principal Component Analysis, where we usually prefer standardization over Min-Max scaling, since we are interested in the components that maximize the variance (depending on the question and if the PCA computes the components via the correlation matrix instead of the covariance matrix;
- however, this doesn’t mean that Min-Max scaling is not useful at all! A popular application is image processing, where pixel intensities have to be normalized to fit within a certain range


### The effect of standardization on PCA in a pattern classification task
- Principal Component Analysis (PCA) as an example where standardization is crucial, since it is “analyzing” the variances of the different features.
Now, let us see how the standardization affects PCA and a following supervised classification on the whole wine dataset.
    - Reading in the dataset
    - Dividing the dataset into a separate training and test dataset
    - Standardization of the features
    - Principal Component Analysis (PCA) to reduce the dimensionality
    - Training a naive Bayes classifier
    - Evaluating the classification accuracy with and without standardization

### Dimensionality reduction via Principal Component Analysis (PCA)
- Now, we perform a PCA on the standardized and the non-standardized datasets to transform the dataset onto a 2-dimensional feature subspace.
- In a real application, a procedure like cross-validation would be done in order to find out what choice of features would yield a optimal balance between “preserving information” and “overfitting” for different classifiers. However, we will omit this step since we don’t want to train a perfect classifier here, but merely compare the effects of standardization.

### Training a naive Bayes classifier
- We will use a naive Bayes classifier for the classification task. If you are not familiar with it, the term “naive” comes from the assumption that all features are “independent”.
- All in all, it is a simple but robust classifier based on Bayes’ rule


## Brownlee, J. (2020, mayo 27). How to Scale Data With Outliers for Machine Learning. Machine Learning Mastery.
### Context
- Many machine learning algorithms perform better when numerical input variables are scaled to a standard range.
- This includes algorithms that use a weighted sum of the input, like linear regression, and algorithms that use distance measures, like k-nearest neighbors.
- Standardizing is a popular scaling technique that subtracts the mean from values and divides by the standard deviation, transforming the probability distribution for an input variable to a standard Gaussian (zero mean and unit variance). Standardization can become skewed or biased if the input variable contains outlier values.
### Robust Scaling Data
- This is because data often consists of many different input variables or features (columns) and each may have a different range of values or units of measure, such as feet, miles, kilograms, dollars, etc.
- If there are input variables that have very large values relative to the other input variables, these large values can dominate or skew some machine learning algorithms. The result is that the algorithms pay most of their attention to the large values and ignore the variables with smaller values.
- Algorithms:
    - Linear reg
    - Log reg
    - ANN
    - KNN
    - SVM
- It is normal to scale input variables to a common range as a data preparation technique prior to fitting a model.
- One approach to data scaling involves calculating the mean and standard deviation of each variable and using these values to scale the values to have a mean of zero and a standard deviation of one, a so-called “standard normal” probability distribution. This process is called standardization and is most useful when input variables have a Gaussian probability distribution.
- value = (value – mean) / stdev
- Sometimes an input variable may have outlier values. These are values on the edge of the distribution that may have a low probability of occurrence, yet are overrepresented for some reason. Outliers can skew a probability distribution and make data scaling using standardization difficult as the calculated mean and standard deviation will be skewed by the presence of the outliers
- One approach to standardizing input variables in the presence of outliers is to ignore the outliers from the calculation of the mean and standard deviation, then use the calculated values to scale the variable.
#### robust standardization or robust data scaling.
- This can be achieved by calculating the median (50th percentile) and the 25th and 75th percentiles. The values of each variable then have their median subtracted and are divided by the interquartile range (IQR) which is the difference between the 75th and 25th percentiles.
- value = (value – median) / (p75 – p25)
- The resulting variable has a zero mean and median and a standard deviation of 1, although not skewed by outliers and the outliers are still present with the same relative relationships to other values.

## McKinney, W. (2022). Python for Data Analysis (3rd ed.). O´Reilly Media.

### Discretization and Binning
- Continuous data is often discretized or otherwise separated into “bins” for analysis. Suppose you have data about a group of people in a study, and you want to group them into discrete age buckets:
- If you pass an integer number of bins to pandas.cut instead of explicit bin edges, it will compute equal-length bins based on the minimum and maximum values in the data. Consider the case of some uniformly distributed data chopped into fourths
- The precision=2 option limits the decimal precision to two digits. A closely related function, pandas.qcut, bins the data based on sample quantiles. Depending on the distribution of the data, using pandas.cut will not usually result in each bin having the same number of data points. Since pandas.qcut uses sample quantiles instead, you will obtain roughly equally sized bins

## Brownlee, J. (2020, junio 12). Ordinal and One-Hot Encodings for Categorical Data. Machine Learning

### Context
- Machine learning models require all input and output variables to be numeric.
- This means that if your data contains categorical data, you must encode it to numbers before you can fit and evaluate a model.

### Nominal and ordinal variables
- Numerical data, as its name suggests, involves features that are only composed of numbers, such as integers or floating-point values
- Categorical data are variables that contain label values rather than numeric values.
- Categorical variables are often called nominal.
-  a numerical variable between 1 and 10 can be divided into an ordinal variable with 5 labels with an ordinal relationship: 1-2, 3-4, 5-6, 7-8, 9-10. This is called discretization.
- Nominal Variable (Categorical). Variable comprises a finite set of discrete values with no relationship between values.
- Ordinal Variable. Variable comprises a finite set of discrete values with a ranked ordering between values.

- Algorithms that use categorical data:
    - Decision trees

- Some implementations of machine learning algorithms require all data to be numerical. For example, scikit-learn has this requirement.

#### Ordinal encoding
- In ordinal encoding, each unique category value is assigned an integer value.
- It is a natural encoding for ordinal variables. For categorical variables, it imposes an ordinal relationship where no such relationship may exist. This can cause problems and a one-hot encoding may be used instead.
- By default, it will assign integers to labels in the order that is observed in the data. If a specific order is desired, it can be specified via the “categories” argument as a list with the rank order of all expected labels.
- f a categorical target variable needs to be encoded for a classification predictive modeling problem, then the LabelEncoder class can be used. Same as ordinal encoder in a one dimensional input.

#### One hot encoding
- Categorical variables in which the integer encoding is not enough.
- Each bit represents a possible category. If the variable cant belong to multiple categories at once, only one bit in the group can be on.

#### Dummy variable encoding.
- ONE HOT creates one binary variable for each category.
- This representation includes redundancy
- Dummy variable encoding represents C categories with C-1 binary values.


## Galli, S. (2022). Python Feature Engineering Cookbook. Packt Publishing.

- Variable transformation consists of replacing the original variable values with a function of that variable. More generally, transforming variables with mathematical functions helps reduce variable skewness, improve the value spread, and sometimes unmask linear and additive relationships between predictors and the target.
- Commonly used mathematical transformations include the logarithm, reciprocal, power, square, and cube root transformations, as well as the Box-Cox and Yeo-Johnson transformations.
- This set of transformations is commonly referred to as variance stabilizing transformations.
- Variance stabilizing transformations intend to bring the distribution of the variable to a more symmetric – that is, Gaussian – shape.

### Transforming variables with the logarithm function
- The logarithm function is a powerful transformation for dealing with positive data with a right-skewed distribution (observations accumulate at lower values of the variable).
- To evaluate the variable distribution and understand whether a transformation improves value spread and stabilizes the variance, we can visually inspect the data with histograms and Quantile-Quantile (Q-Q) plots. 
- A Q-Q plot helps us determine whether two variables show a similar distribution.
- In a Q-Q plot, we plot the quantiles of one variable against the quantiles of the second variable. 
- If we plot the quantiles of the variable of interest against the expected quantiles of the normal distribution, then we can determine whether our variable is also normally distributed. 
- If the variable is normally distributed, the points in the Q-Q plot will fall along a 45-degree diagonal. 

### Transforming variables with the reciprocal function
- The reciprocal function is defined as 1/x. The reciprocal transformation is often useful when we have ratios – that is, values resulting from the division of two variables. 

### Using the square root to transform variables
- The square root transformation, √x, as well as its variations, the Anscombe transformation, √(x+3/8), and the Freeman-Tukey transformation, √x + √(x+1), are variance stabilizing transformations that transform a variable with a Poisson distribution into one with an approximately standard Gaussian distribution.
- The Poisson distribution is a probability distribution that indicates the number of times an event is likely to occur. In other words, it is a count distribution. It is right-skewed and its variance equals its mean

### Using power transformations
- The square and cube root transformations are special cases of power transformations where lambda is 1/2 or 1/3, respectively. The challenge resides in finding the value for the lambda parameter. The Box-Cox transformation, which is a generalization of the power transformations, finds the optimal lambda via maximum likelihood.

### Performing Box-Cox transformation
- The Box-Cox transformation is a generalization of the power family of transformations and is defined as follows:
- Here, y is the variable and λ is the transformation parameter. It includes important special cases of transformations, including untransformed (λ = 1), the logarithm (λ = 0), the reciprocal (λ = - 1), the square root (when λ = 0.5, it applies a scaled and shifted version of the square root function) and the cube root.
- In the Box-Cox transformation, several values of λ are evaluated using the maximum likelihood, and the λ parameter that returns the best transformation is selected.
- The Box-Cox transformation can only be used on positive variables. If your variables have negative values, try the Yeo-Johnson transformation, which is described in the next recipe, Performing Yeo-Johnson transformation. Alternatively, you can shift the variable distribution by adding a constant before the transformation.

### Performing Yeo-Johnson transformation
- The Yeo-Johnson transformation is an extension of the Box-Cox transformation that is no longer constrained to positive values. In other words, the Yeo-Johnson transformation can be used on variables with zero and negative values, as well as positive values. These transformations are defined as follows:
- When the variable has only positive values, then the Yeo-Johnson transformation is like the Box-Cox transformation of the variable plus one.
- If the variable has only negative values, then the Yeo-Johnson transformation is like the BoxCox transformation of the negative of the variable plus one at the power of 2.
- If the variable has a mix of positive and negative values, the Yeo-Johnson transformation applies different powers to the positive and negative values.