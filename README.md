# Tree-based ensemble methods

The purpose of this project is to examine the performance of published tree-based ensemble methods.


## Boosting-Based pruning (BB)
We implemented from scratch an algorithm from the scientific paper "Using boosting to prune bagging ensembles". This method intends to use ensemble pruning to reduce storage and running time. Numerous experimental studies show that pooling the decisions of classifiers in an ensemble generally improves the generalization performance of weak learners. A vital shortcoming of ensemble methods is the loss of classification speed and the growth in storage needs with increasing numbers of inducers. Ensemble pruning reduces the storage needs, speeds up the classification process and has the potential of improving the classification accuracy of the original ensembles.

**Reference**:
Martínez-Muñoz, G., & Suárez, A. (2007). Using boosting to prune bagging ensembles. Pattern Recognition Letters, 28(1), 156-165

![Figure 1: The Boosting-Based pruning illustration](https://github.com/TamarDD/Final_Project_ML/blob/master/BB.png)
Figure 1: The Boosting-Based pruning illustration


## Experiments

We examine the performance of BB and XGBoost on 150 classification datasets. We used 10-Fold Cross-Validation to calculate the external metric, including accuracy, TPR, FPR, precision, AUC-ROC, AUC precision-recall, training time, and inference time. 
We used micro-average to achieve the performance overall across the data. Then, we used Bayesian Optimization for hyperparameters tuning with 3-Fold Cross-Validation for choosing the best parameters.

## Meta-learning model 

We build a meta-learning model which aims to predict the best algorithm (XGBoost or BB) according to Meta-Features features. The target was the winner between the algorithm according to the mean AUC each algorithm achieved on the classification databases. The evaluation performance of the model was done by Leave-One-Out cross-validation.
The meta-learning model does not adequately learn which model is better, although it receives better accuracy than random guesses. So in practice, the observations indicated that selecting a subset of classifiers from the original ensemble may improve the classification performance.

**Notes**
You can find the full report and more advanced analysis at [link](https://github.com/TamarDD/Final_Project_ML/blob/master/project_report.pdf)

## Instructions
For running this code, please follow the instructions:
1. Clone the repository 
2. Unzip classification folder to 'classification_datasets' folder
3. Turn on the GPU
4. Run "project_code.ipynb"


## Installation 

To run this code, you'll need Python 3.5 installed. To install the necessary python packages, you may also need Anaconda.

Once you have Anaconda, type this to make a new virtual environment with all the packages you need: conda create --name final_project --file requirements.txt

