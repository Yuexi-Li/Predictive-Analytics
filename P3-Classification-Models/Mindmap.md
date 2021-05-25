

# Binary
## Logistic 
- refine: Stepwise model 
- Evulation: AIC &#8593; and BIC (penalty) &#8595; 
## Decision Trees
- Easy to overfit model (the Accuracy gap between train and test data)


# NonBinary

## Decision Trees 
- Pros: Easy to overfitting 
- Cons: computationally Intensive
## Random Forest Models
- Ensemble of decision trees randomly
- overfitting averages out by all trees
### Validation 
- OOB rate: *i.e.Out of the bag error rate (Similar as R-squared value)*
- Confusion matrix 
### [Gini](https://dinsdalelab.sdsu.edu/metag.stats/code/randomforest.html)
- Gini coefficient: quadrant divide, right top are more important, left bottom little to no importance 

## Boosted Models 
### overview:
- makes one tree 
- detect error and changes the tree to reduce the error and repeat this step 
### Validation 
- variable importance plot 
- number of iterations assessment plot