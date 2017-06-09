# HPStream
+ Find a ($k+1$)-partition of the data (last partition are outliers)
+ Find a set of dimensions for each cluster s.t. the cardinality of the set is a parameter $l$.

## Fading cluster structure
+ Half life of a point $t_0$ of a point is defined as the time at which $f(t_0) = (1/2)f(0)$: rate of decay of the weight assigned to each data point.
+ Data point weight: $f(t) = 2^{-\lambda t}$
+ Fading cluster structure of a set of points $\mathcal{C} = \{ X_{i_1} , \dots, X_{i_n}\}$ with time stamps $T_{i_1} \dots T_{i_n}$: $\mathcal{FC}(\mathcal{C}) = (FC2^x(\mathcal{C},t) , FC1^x(\mathcal{C},t) , W(t)): 
	+ $FC2^x(\mathcal{C},t) = \sum_{k=1}^n f(t-T_{i_k}) (x^j_{i_k})^2$
	+ $FC1^x(\mathcal{C},t) = \sum_{k=1}^n f(t-T_{i_k}) x^j_{i_k}$ 
	+ $W(t) = \sum_{k=1}^n  f(t-T_{i_k})$
	+ $\mathcal{B}(\mathcal{C})$: bit vector of relevant dimensions.
+ Properties of fading structure:
	+ $\mathcal{FC}(\mathcal{C}_1 \cup \mathcal{C}_2 , t) = \mathcal{FC}(\mathcal{C}_1,t) + \mathcal{FC}(\mathcal{C}_2,t)$
	+ If no points are added in the time interval $(t,t+\delta t)$, then $\mathcal{FC}(\mathcal{C}, t + \delta t) = e^{-\lambda \delta t}\mathcal{FC}(\mathcal{C}, t)$

## HPStream
+Initialization:
	+ Receive $InitNumber$ Points
	+ Compute $k$ clusters using K-means
	+ Select only $l$ dimensions per cluster using the same method
	+ Recompute an assignment according to the subspaces
	+ Repeate until convergence
	
+ Normalization:
	+ Compute $\sigma_d$ std along each dimension for an initial sample of the datapoints
	+ Devide the coodrinate of each new point by the std.
	+ Recompute $\sigma_d$ at an interval of $N'$ points
	+ If $\sigma_d$ changes to $\sigma'_d$ update fading clusters:
		+ $FC2^x(\mathcal{C},t) \times =  \sigma_d^2 / \sigma'^{2}_d \$
		+ $FC1^x(\mathcal{C},t) \times =  \sigma_d / \sigma'_d \$
+ update the temporal decay function for each cluster:
	+ Let $t$ denote the current time and $t^{up}$ the last update time for a given cluster. Multiply each fading cluster by: $e^{-\lambda (t - t^{up})}$
+ Compute $l$ relevant dimensions(\mathcal{FCS}, $l$, $X$)
	+ Create $|\mathcal{FCS}|$ tentative fading clusters by ading $X$ to each existing Fading cluster (to avoid selecting only the dimensions of very small clusters)
	+ Compute the radius along each dimension
	+ Pick the $|\mathcal{FCS} \times l|$ dimensions with least radii
	+ Create the bit vector $\mathcal{B}(\mathcal{C}_r)$ for each fading cluster
+ Compute projected (segmental manhattan) distances to each fading cluster and find the closest center.
+ Compute the limiting radius (mean of the STD of the cluster measured along its subspace only multiplied by $\tau$). 
+ If the new point is within the radius add it, otherwise create a new fading cluster.
+ In order to keep constant the number of clusters, remove the  one to which the least recent updating was performed
+ Remove clusters with 0 dimensions assigned to them
