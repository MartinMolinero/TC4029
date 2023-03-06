# Modelos de análisis de datos

- La principal diferencia es que el primero (el aprendizaje supervisado) usa datos etiquetados para ayudar a predecir los resultados, o en otras palabras, tenemos un conocimiento previo de cuáles deberían ser los valores de salida para nuestras muestras. Por lo tanto, el objetivo del aprendizaje supervisado es aprender una función que, dada una muestra de datos y resultados deseados, se aproxime mejor a la relación entre entrada y salida observable en los datos.

- El aprendizaje no supervisado, por otro lado, no tiene salidas etiquetadas, por lo que su objetivo es inferir la estructura natural presente dentro de un conjunto de puntos de datos.

- Después de construir los modelos, es necesario verificar que los resultados sean válidos y correctos, lo que nos guiará a la fase de evaluación. En caso de que los resultados sean erróneos, la metodología permite volver al primer paso para tener una comprensión de lo que está ocurriendo. Por lo general, en un proyecto de ciencia de datos, el científico de datos divide los datos en entrenamiento y prueba. En este paso se utilizan los datos de prueba y es importante especificar alguna métrica de desempeño.


## Aprendizaje no supervisado
- Los modelos de aprendizaje no supervisados, por el contrario, funcionan por sí solos para descubrir la estructura inherente de los datos no etiquetados (aunque todavía requieren cierta intervención humana para validar las salidas). Por ejemplo, los modelos de análisis de cesta de compra tienen como objetivo encontrar asociaciones en los productos que permitan predecir con qué probabilidad se comprará un producto B si se compra un producto A. Sin embargo, un analista de datos tendría que validar que tiene sentido que un modelo agrupe los martillos con la pintura (se ha demostrado que los hombres que van a comprar martillos compran también pintura un 60% de las veces).

- La agrupación en clústers es una técnica para agrupar datos no etiquetados en función de sus similitudes o diferencias. Es útil para la segmentación del mercado, la compresión de imágenes, etc.

- La asociación utiliza diferentes reglas para encontrar relaciones entre variables en un conjunto de datos determinado. Estos métodos se utilizan con frecuencia para el análisis de la cesta de la compra y los motores de recomendación.

- La reducción de la dimensionalidad se utiliza cuando el número de características (o dimensiones) en un conjunto de datos dado es demasiado alto. Reduce la cantidad de entradas de datos a un tamaño manejable al mismo tiempo que preserva la integridad de los datos. A menudo, esta técnica se utiliza en la etapa de preprocesamiento de datos.

- . Es recomendable reducir la cantidad de dimensiones (variables) en los datos de entrenamiento antes de enviarlos a otro algoritmo de aprendizaje automático, pues se reducen los tiempos de procesamiento, los datos ocupan menos espacio en disco y memoria y, en algunos casos, también se logran mejores resultados. La reducción de dimensionalidad es considerada entonces parte de la ingeniería de características para modelos de aprendizaje supervisado.

### IBM (2022). What is unsupervised learning?
- uses machine learning algorithms to analyze and cluster unlabeled datasets. These algorithms discover hidden patterns or data groupings without the need for human intervention. Its ability to discover similarities and differences in information make it the ideal solution for exploratory data analysis, cross-selling strategies, customer segmentation, and image recognition.


#### Clustering
-  data mining technique which groups unlabeled data based on their similarities or differences. Clustering algorithms are used to process raw, unclassified data objects into groups represented by structures or patterns in the information. Clustering algorithms can be categorized into a few types, specifically exclusive, overlapping, hierarchical, and probabilistic.

##### Exclusive and Overlapping Clustering
- Exclusive clustering is a form of grouping that stipulates a data point can exist only in one cluster. This can also be referred to as “hard” clustering. The K-means clustering algorithm is an example of exclusive clustering.

- K-means clustering is a common example of an exclusive clustering method where data points are assigned into K groups, where K represents the number of clusters based on the distance from each group’s centroid. The data points closest to a given centroid will be clustered under the same category.

##### Hierarchical clustering
-  Its data points are isolated as separate groupings initially, and then they are merged together iteratively on the basis of similarity until one cluster has been achieved. Four different methods are commonly used to measure similarity:
- Ward’s linkage: This method states that the distance between two clusters is defined by the increase in the sum of squared after the clusters are merged.
- Average linkage: This method is defined by the mean distance between two points in each cluster
- Complete (or maximum) linkage: This method is defined by the maximum distance between two points in each cluster
- Single (or minimum) linkage: This method is defined by the minimum distance between two points in each cluster

##### Probabilistic clustering
- The Gaussian Mixture Model (GMM) is the one of the most commonly used probabilistic clustering methods.
- Gaussian Mixture Models are classified as mixture models, which means that they are made up of an unspecified number of probability distribution functions. GMMs are primarily leveraged to determine which Gaussian, or normal, probability distribution a given data point belongs to. If the mean or variance are known, then we can determine which distribution a given data point belongs to. However, in GMMs, these variables are not known, so we assume that a latent, or hidden, variable exists to cluster data points appropriately. While it is not required to use the Expectation-Maximization (EM) algorithm, it is a commonly used to estimate the assignment probabilities for a given data point to a particular data cluster.   

#### Association Rules
- An association rule is a rule-based method for finding relationships between variables in a given dataset. These methods are frequently used for market basket analysis, allowing companies to better understand relationships between different products.

##### Apriori algorithms
- Apriori algorithms have been popularized through market basket analyses, leading to different recommendation engines for music platforms and online retailers. They are used within transactional datasets to identify frequent itemsets, or collections of items, to identify the likelihood of consuming a product given the consumption of another product

#### Dimensionality reduction
-  Dimensionality reduction is a technique used when the number of features, or dimensions, in a given dataset is too high. It reduces the number of data inputs to a manageable size while also preserving the integrity of the dataset as much as possible

##### Principal component analysis
- Principal component analysis (PCA) is a type of dimensionality reduction algorithm which is used to reduce redundancies and to compress datasets through feature extraction. This method uses a linear transformation to create a new data representation, yielding a set of "principal components." The first principal component is the direction which maximizes the variance of the dataset. While the second principal component also finds the maximum variance in the data, it is completely uncorrelated to the first principal component, yielding a direction that is perpendicular, or orthogonal, to the first component.

##### Singular value decomposition
- Singular value decomposition (SVD) is another dimensionality reduction approach which factorizes a matrix, A, into three, low-rank matrices. SVD is denoted by the formula, A = USVT, where U and V are orthogonal matrices. S is a diagonal matrix, and S values are considered singular values of matrix A. Similar to PCA, it is commonly used to reduce noise and compress data, such as image files.

##### Autoencoders
- Autoencoders leverage neural networks to compress data and then recreate a new representation of the original data’s input

## Parte, K. (2020, noviembre 3). Dimensionality Reduction: Principal Component Analysis. Analytics Vidhya.
-  If we keep on increasing the number of features, after a certain point, the performance of our machine learning algorithm tends to decrease.
- According to Hughes phenomenon, If the number of training samples is fixed and we keep on increasing the number of dimensions then the predictive power of our machine learning model first increases, but after a certain point it tends to decrease.
- typically as the dimensions increase the number of samples needed for good prediction increases logarithmically. In the real world, datasets have 1000s of features, so the amount of data we need to keep up with the increasing dimensions becomes enormous (2¹⁰⁰⁰ ) which increases the training time drastically, on the other hand, if we keep on increasing the dimensions and don’t increase the number of samples then our machine learning algorithms tend to overfit and their performance decreases.
- After a certain point, the data becomes so sparse that an accurate estimation of the classifier parameters becomes more difficult. In fact, data around the origin is much sparser than data in the corners
- As the dimensions increase, all the points become equidistant from each other such that the difference between the minimum and maximum distance between two points tends to zero.
- PCA is a linear dimensionality reduction technique which converts a set of correlated features in the high dimensional space into a series of uncorrelated features in the low dimensional space. These uncorrelated features are also called principal components. PCA is an orthogonal linear transformation which means that all the principal components are perpendicular to each other. It transforms the data in such a way that the first component tries to explain maximum variance from the original data.
- To find these new features, all PCA does is, rotate the original axes in such a way that we get maximum spread (variance) on the new axes after projecting the data points on them. These new axes are a linear combination of the original axes and they are always perpendicular to each other.

- PCA is the simplest dimensionality reduction algorithm, but it has its own limitations. There are other variations of PCA such as kernel PCA which can be used for non-linear data. PCA doesn't take into consideration the local structure present in the data as it tries to preserve the global structure. There are other highly advanced dimensionality reduction techniques such as TSNE, which do not make any linear assumptions about the data and preserves the local structure present in the data. Overall we can use PCA when the variables are strongly correlated, but if the relationship between the variables is weak, PCA does not work.