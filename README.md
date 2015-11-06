A basic scikit-learn application of text classification for the Kagggle ["What's cooking ?"](https://www.kaggle.com/c/whats-cooking) knowledge competition. 

## Environment

- Ipython notebook running in an anaconda environment, with scikit-learn / nltk3 / matplotlib / pandas installed
- cooking.ipynb is a python notebook that build a model and outputs a csv submission file
- stats.ipynb provides some data exploration

## Principles

A few classic scikit-learn models have been applied : 
- RandomForest, ExtraTrees and GradientBoostedTrees have been tested for model building
- CountVectorizer and TfIdfVectorizer have been tried to build text features
- additionally, some extra text manipulations have been explored : english stop words, numbers removal, ascii folding, stemming, usage of bigrams, token merging for long words with edit distance of 1 (to allow better handling of orthographic variations, such as amaretti / amaretto)   

## Results

On a text manipulation point of view, basic english stemming with stop words, numbers removed and ascii folding seems to be the most efficient solution (long tokens merging have surprisingly not improved the result).

On an model point of view, the ExtraTreesClassifier (with 500 estimators) has outclassed RandomForestClassifier.
GradientBoostingTrees is taking way too much time to build its model, so we'll skip. 

The best solution only leads to a very weak 0.773 accuracy (vs 0.82 for the top solution).

## TODO

- Provide a better representation of confusion matrix
- Provide some matplotlib visualizations of ingredients
- Explore grid search for hyper-parameters
- Try xgboost