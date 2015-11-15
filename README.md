A basic scikit-learn application of text classification for the Kaggle ["What's cooking ?"](https://www.kaggle.com/c/whats-cooking) knowledge competition. 

## Environment

- Ipython notebook running in an anaconda environment, with scikit-learn / nltk3 / matplotlib / pandas / xgboost installed
- cooking.ipynb is a python notebook that build a scikit-learn model and outputs a csv submission file
- stats.ipynb provides some data exploration
- xgboost.ipynb provides the same logic than cooking.ipynb, this time with xgboost

## Principles

A few classic scikit-learn models have been applied : 
- scikit-learn's RandomForest, ExtraTrees and GradientBoostedTrees have been tested for model building
- xgboost has been tested as well too
- CountVectorizer and TfIdfVectorizer have been tried to build text features
- additionally, some extra text manipulations have been explored : english stop words, numbers removal, ascii folding, stemming, usage of bigrams, token merging for long words with edit distance of 1 (to allow better handling of orthographic variations, such as amaretti / amaretto), custom stopwords list   

## Results

On a text manipulation point of view, basic english stemming with standard stopwords, numbers removed and ascii folding seems to be the most efficient solution (long tokens merging have surprisingly not improved the result).

On an model point of view, the ExtraTreesClassifier (with 500 estimators) has outclassed RandomForestClassifier among scikit-learns methods.
GradientBoostingTrees is taking way too much time to build its model, so we'll skip. 
Xgboost has slightly outperformed all these methods (it really _does_ look to avoid overfitting)

The best solution only leads to a so-so 0.78902 accuracy (vs 0.82 for the top solution).

## TODO

- Provide a better representation of confusion matrix
- Provide some matplotlib visualizations of ingredients
- Explore grid search for hyper-parameters
