# Outliers detection or Anomaly detection
+ novelty detection:
	+ The training data is not polluted by outliers, and we are interested in detecting anomalies in new observations.
+ outlier detection:
 	+ The training data contains outliers, and we need to fit the central mode of the training data, ignoring the deviant observations.
+ [global outlier approaches](http://scikit-learn.org/stable/modules/outlier_detection.html). Evaluate differences of properties compared over the complete data set. Outlierness correspond then to a binary property: for each object it is decided whether it is an outlier or not.
+ [Density-based techniques (K-nearest neighbors)](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm). If a point has its KNN too far away, it means that is probably an outlier
+ [Replicator Neural Networks](autoencodeur)](http://togaware.com/papers/dawak02.pdf). The idea is to train a NN to take data inputs, compress them and output the same input decompressing it. Then authors define a measure of outliersness based on the distance between the input and the reconstruction (bad in case of outliers) 
+ [Outliers detection in subspaces](http://www.dbs.ifi.lmu.de/Publikationen/Papers/pakdd09_SOD.pdf). Detect the subspace where the point is an outlier. For this they find a set of reference points for the analyzed point, compute the variance along the different dimensions for this points, detect important subspaces, compute a distance measure (like in K-nearest neighbors) but only in those dimensions