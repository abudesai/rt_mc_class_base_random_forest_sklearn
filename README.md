Random Forest Classifier in SciKitLearn with Shapley explanations for Multi-class Classification - Base problem category as per Ready Tensor specifications.

- random forest
- ensemble
- multi-class classification
- XAI
- sklearn
- python
- pandas
- numpy
- scikit-optimize
- flask
- nginx
- uvicorn
- docker

This is a Multi-class Classifier that uses a Random Forest implementation through SciKitLearn. Feature impacts are provided with Shapley values for model interpretability.

The classifier starts by creating an ensemble of decision trees and assigns the sample to the class that is predicted by the majority of the decision trees.

The data preprocessing step includes missing data imputation, standardization, one-hot encoding for categorical variables, datatype casting, etc. The missing categorical values are imputed using the most frequent value if they are rare. Otherwise if the missing value is frequent, they are give a "missing" label instead. Missing numerical values are imputed using the mean and a binary column is added to show a 'missing' indicator for the missing values. Numerical values are also scaled using a Yeo-Johnson transformation in order to get the data close to a Gaussian distribution.

Hyperparameter Tuning (HPT) is conducted by finding the optimal number of decision trees to use in the forest, number of samples required to split an internal node, and number of samples required to be at a leaf node.

During the model development process, the algorithm was trained and evaluated on a variety of publicly available datasets such as email primary-tumor, splice, stalog, steel plate fault, wine, and car.

This Multi-class Classifier is written using Python as its programming language. Scikitlearn is used to implement the main algorithm, create the data preprocessing pipeline, and evaluate the model. Numpy, pandas, and feature_engine are used for the data preprocessing steps. SciKit-Optimize was used to handle the HPT. Flask + Nginx + gunicorn are used to provide web service which includes three endpoints- /ping for health check, /infer for predictions in real time and /explain to generate local explanations.
