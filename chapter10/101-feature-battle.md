| Stage of ML preprocessing or       type of model | Algorithm /         trainer | Ignite ML 2.5-2.6 | Ignite ML 2.7 | Spark ML 2.3 | Analogue in       Spark |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Feature Extracting | TF-IDF | no | no | yes | related to NLP |
| Feature Extracting | Word2Vec | no | no | yes | related to NLP |
| Feature Extracting | CountVectorizer | no | no | yes |  |
| Feature Extracting | FeatureHasher | no | no | yes |  |
| Feature Transformation | Tokenizer | no | no | yes | related to NLP |
| Feature Transformation | StopWordsRemover | no | no | yes | related to NLP |
| Feature Transformation | nn-gram | no | no | yes | related to NLP |
| Feature Transformation | Binarizer | no | yes | yes |  |
| Feature Transformation | PCA | no | no | yes |  |
| Feature Transformation | PolynomialExpansion | no | no | yes |  |
| Feature Transformation | Discrete Cosine Transform \(DCT\) | no | no | yes |  |
| Feature Transformation | StringIndexer | no | yes | yes |  |
| Feature Transformation | OneHotEncoder | no | yes | yes |  |
| Feature Transformation | Normalizer | no | yes | yes |  |
| Feature Transformation | StandardScaler | no | no | yes |  |
| Feature Transformation | MinMaxScaler | no | yes | yes |  |
| Feature Transformation | MaxAbsScaler | no | no | yes |  |
| Feature Transformation | QuantileDiscretizer | no | no | yes |  |
| Feature Transformation | Imputer | no | yes | yes |  |
| Feature Transformation | Locality Sensitive Hashing \(LSH\) | no | no | yes |  |
| Feature Selection | Feature Extractor | yes | yes | yes\* | \*VectorAssembler/VectorSlicer and others Vector Transformers |
| Feature Selection | Chi-Squared test of independence | no | no | yes\* | \*ChiSqSelector |
| Classification | Binomial logistic regression | no | yes | yes |  |
| Classification | Decision tree classifier | yes | yes | yes |  |
| Classification | Linear SVM | yes | yes | yes |  |
| Classification | Random forest classifier | no | yes | yes |  |
| Classification | Gradient-boosted tree classifier | no | no | yes |  |
| Classification | Multilayer perceptron classifier | yes | yes | yes |  |
| Classification | KNN | yes | yes | no |  |
| Classification | Weigthed KNN | yes | yes | no |  |
| Classification | ANN \(Approximate Nearest Neighbour\) with ACD strategy | no | yes | no\* | \*Spark can use ANN methods via pre-built buckets with LSH but it doesn't support another method to build annoy index |
| Classification | Naive Bayes | no | no | yes |  |
| Regression | Generalized linear regression | no | no | yes\* | \*supports only 4096 features |
| Regression | Linear regression with LSQR | yes | yes | no |  |
| Regression | Linear regression with SGD | yes | yes | yes |  |
| Regression | Decision tree regression | yes | yes | yes |  |
| Regression | Random forest regression | no | yes | yes |  |
| Regression | Gradient-boosted tree regression | no | yes | yes |  |
| Regularization | L1, L2 .. Lp as parameter for trainer | yes | yes | yes |  |
| Model Composition / Model Ensembles | Ensemble as a Mean value of predictions | no | yes | no\* | \*supported for trees only |
| Model Composition / Model Ensembles | Majority-based Ensemble | no | yes | no\* | \*supported for trees only |
| Model Composition / Model Ensembles | Ensemble as a weighted sum of predictions | no | yes | no\* | \*supported for trees only |
| Clustering | K-means | yes | yes | yes |  |
| Clustering | Latent Dirichlet allocation \(LDA\) | no | no | yes |  |
| Clustering | Bisecting k-means | no | no | yes |  |
| Clustering | Gaussian Mixture Model \(GMM\) | no | no | yes |  |
| Collaborative Filtering | ALS | no | no | yes |  |
| Model selection | TrainTest Splitting | no | yes | yes |  |
| Model selection | Cross Validation | no | yes | yes |  |
| Model selection | Parameter Grid | no | yes | yes |  |
| Model selection | Binary Evaluator | no | yes | yes |  |
| Model selection | Multi-class Evaluator | no | no | yes |  |
| Metric | Accuracy | no | yes | yes |  |
| Metric | Fmeasure | no | yes | yes |  |
| Metric | Precision | no | yes | yes |  |
| Metric | Recall | no | yes | yes |  |
| Metric | ROC AUC | no | no | yes |  |
| Advanced Topics | Genetic Algorithms | yes | yes | no |  |
| Advanced Topics | Model Export/Import | yes | yes | yes\* | \* PMML is supported |
| Advanced Topics | TensorFlow Integration via tensorflow/tensorflow/contrib/ | no | yes | no\* | \* no projects which are parts of original TF |
| Advanced Topics | Parallel run of particular trainings | no | yes | no\* | \* It supports in a tiny number of algorithms like KMeans initialization |



