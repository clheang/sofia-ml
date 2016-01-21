# sofia-ml
Automatically exported from code.google.com/p/sofia-ml

The suite of fast incremental algorithms for machine learning (sofia-ml) can be used for training models for classification, regression, ranking, or combined regression and ranking. Several different techniques are available. This release is intended to aid researchers and practitioners who require fast methods for classification and ranking on large, sparse data sets.

Supported classification, regression, and ranking learners include:

* Pegasos SVM
* Stochastic Gradient Descent (SGD) SVM
* Passive-Aggressive Perceptron
* Perceptron with Margins
* ROMMA
* Logistic Regression (with Pegasos Projection)

These learners can be configured for binary classification, ranking, and optimizing ROC area, through the use of several available sampling methods for stochastic gradient descent.

This implementation is very fast. For example, 100,000 Pegasos SVM training iterations can be performed on data from the CCAT task from the RCV1 benchmark data set (with roughly 780,000 examples) in 0.1 CPU seconds on an ordinary 2.4GHz laptop, with no loss in classification performance compared with other SVM methods. On LETOR learning to rank benchmark tasks, training time with 100,000 Pegasos SVM rank steps complete 0.2 CPU seconds on an ordinary laptop.

The primary computational bottleneck is actually reading the data off of disk; sofia-ml reads and parses data from disk substantially faster than other SVM packages we tested. For example, sofia-ml can read and parse data nearly 10 times faster than the reference Pegasos implementation by Shalev-Shwartz, and nearly 3 times faster than svm_perf by Joachims.

This package provides a commandline utility for training models and using them to predict on new data, and also exposes an API for model training and prediction that can be used in new applications. The underlying libraries for data sets, weight vectors, and example vectors are also provided for researchers wishing to use these classes to implement other algorithms.
