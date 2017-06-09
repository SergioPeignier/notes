# HDDStream

## Microclusters

+ Exponential fading function: weight of points decrease $f(t) = 2^{-\lambda t}$, $0<\lambda <1 $
+ MicroClusters: 
	+ $C={p_1,p2,\dots , p_n}$ set of d-dimensional points
	+ $mc(C,t) = (CF1(t), CF2(t), W(t))$
	+ $CF1(t) = \langle CF1_1(t) \dots CF1_d(t)\rangle$ weighted linear sum of coordinates along each dimension: $CF1_1(t) = \sum_{i=1}^n f(t,t_i)p_{i_j}$
	+ $CF2(t) = \langle CF2_1(t) \dots CF2_d(t)\rangle$ weighted square sum of coordinates along each dimension: $CF1_1(t) = \sum_{i=1}^n f(t,t_i)p^2_{i_j}$
	+ $W(t)$ sum of weights of the data points $W(t)=\sum_{i=1}^n f(t-t_i)$
+ Online maintenance:
	+ Additivity: new point $p$ added $mc = (CF1(t)+p,CF2(t)+p^2, W(t) +1)$
	+ Temporal multiplicity: If no points are added to mc during (t, t+\delta t): $mc \rightarrow mc \times 2^{-\lambda \delta t}$
+ Prefered dimension (microcluster prefers a dimension, if the members of the microcluster are densely packed along this dimension)
	+ A microcluster $mc$ preferes the j-th dimension if: $Var_j(mc) \leq \delta$
	+ $Var_j(mc) = \sqrt(\frac{CF2_j(t)}{W(t)} - (\frac{CF1_j(t)}{W(t)})^2)
	+ $\deta$: variance threshold
+ Dimension preference vector:
	+ $\Phi(mc) = \langle \phi_1,\phi_2,\dots \phi_d  \rangle$
	+ $\phi_j = \kappa$ if $j$ is prefered, and 1 otherwise
	+ $\kappa >> 1$ is a constant
	+ $PDim(mc)$ Nb of prefered dimensions.
+ Projected radius: 
	+ $radius^{\phi}(mc) = \sqrt{ \frac{1}{\phi_j} \sum_^d{j=1} Var_j(mc)}$
+ Projected micro-cluster: microcluster + dimension preference vector
+ Core-pMC: Core projected microcluster if it 'compresses' more than $\mu$ points within a limited radius $\epsilon$, in a projected subspace of maximal dimensionality $\pi$
	+ $radius^{\phi}(mc) \leq \epsilon$
	+ $W(t) \geq \mu$
	+ $PDim(mc)\leq \pi$
+ pCore-pMC: potential core projected microcluster
	+ $radius^{\phi}(mc) \leq \epsilon$
	+ $W(t) \geq \mu\beta$
	+ $PDim(mc)\leq \pi$
	+ $\beta \in [0,1]$
+ o-MC: outiler microcluster
	+ $radius^{\phi}(mc) \leq \epsilon$
	+ $W(t) < \mu\beta$ or 
	+ $PDim(mc) > \pi$

## HDDStream Algorithm

+ Initialization
	+ Arrival of $initPoints$ points
	+ Build initial set of microclusters
+ Online microcluster maintenance
	+ As new points arrive arrive and old points expire due to ageing
	+ New point may be inserted to existing microcluster or start its own microcluster
+ Offline clustering
	+ Extrated on demand based on maintained microclusters

### Initialization
+ Receive $initPoints$ points
+ Apply PreDeCon to extract first microclusters
+ For each point $p$ Compute the d-dimensional neighborhood $\mathcal{N}_{\epsilon} (p)$ : all points within a distance $\epsilon$ from $p$.
+ Compute the dimension preference vector $\Phi(p)$ based on the variance along each dimension in $\mathcal{N}_{\epsilon} (p)$.
+ If $PDim(mc) \leq \pi$ and $W(t) \geq \mu\beta$ Build a potential core projected microcluster (pCore-pMicroCluster): $mc = \{ p \cup \mathcal{N}_{\epsilon} (p) \}$ 

### Online microcluster maintenance
+ Two lists maintained: 
	+ pCore-pMicroClusters
	+ o-microClusters
+ New point $p$ arrives at time $t$
	+ Distance between a point $p$ and a microcluster $mc$: $dist^{\phi}(p,mc) = \sqrt{\sum{j=1}^d \frac{1}{\\phi_j} (p_j - center_j)^2}$
	+ Try to add $p$ to the closest pCore-pMicroCluster $m$ s.t. the dimension preferences of $m$ remains smaller than $\pi$, and the radius, remains smaller than $\epsilon$.
	+ Otherwise try to add $p$ to its closest o-MicroCluster $m$ only looking if the restriction on the radius is not violated.
	+ Otherwise create a new o-MicroCluster

### Offline clustering
+ pCore-pMicroClusters are used as seeds for extracting projected clusters.
+ For mc $\in$ pCore-pMicroClusters we check if it is a core projected microcluster. If so, the micro-cluster and its neighbors are collapsed into one cluster and further expansions are applied from this neighbors. When all points are proceed, we are done. 

### Evaluation:
+ Use Purity
+ Covertype and Intrusions
+ Evaluation Horizon $H = 1$ (same size as the window size)
+ Intrusion parameters:
	+ $initPoints = 2000$, $H = 1$, $\lambda = 0.5$, $\mu = 10$, $\beta = 0.5$, $\epsilon = 0.2$, $\pi = 30$, $\delta = 0.001$, $w = 1000$ per time. 
+ Covertype parameters:
	+ $initPoints = 2000$, $H = 1$, $\lambda = 0.5$, $\mu = 10$, $\beta = 0.5$, $\epsilon = 0.2$, $\pi = 8$, $\delta = 0.01$, $w = 200$ per time. 

