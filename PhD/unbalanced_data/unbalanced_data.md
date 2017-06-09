# [Dealing with unbalanced data](http://machinelearningmastery.com/tactics-to-combat-imbalanced-classes-in-your-machine-learning-dataset/)
+ Collect More Data
+ [Change Your Performance Metric](http://machinelearningmastery.com/classification-accuracy-is-not-enough-more-performance-measures-you-can-use/):
	+ Confusion Matrix
	+ Precision: A measure of a classifiers exactness (True Positives divided by the number of True Positives and False Positives)
	+ Recall: A measure of a classifiers completeness (True Positives divided by the number of True Positives and the number of False Negatives)
	+ F1 Score (or F-score): A weighted average of precision and recall.
	+ Kappa (or Cohen’s kappa): Classification accuracy normalized by the imbalance of the classes in the data.
	+ ROC Curves: Like precision and recall, accuracy is divided into sensitivity and specificity and models can be chosen based on the balance thresholds of these values.
		+ Sensitivity: TP/(TP + FN) = TP/P
		+ Specificity: TN/(TN + FP) = TN/N
+ Resampling Your Dataset:
	+ Under-sample over represented data (if a lot of data)
	+ Add copies or surrogates (SMOTE technique) of instances from the under-represented (otherwise)
+ Try Different Algorithms (random forest are good)
+ Try Penalized Models (modify objective function)
