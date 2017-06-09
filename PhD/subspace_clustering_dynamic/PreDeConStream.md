# PreDeConStream

## Microclusters

+ Exponential fading function: weight of points decrease $f(t) = 2^{-\lambda t}$, $0<\lambda <1 $
+ Core Microcluster CMC(w,c,r):
	+ $w$ sum of weights of the data points $w=\sum_{i=1}^n f(t-t_i)$
	+ $center = \frac{1}{w}\sum_^n{i=1} f(t-t_i) p_j$
	+ $radius = \frac{1}{w} \sum_^n{i=1} f(t-t_i) dist(p_i,center)$
	+ $w > \mu_N$
	+ $r < \epsilon_N$
+ Potential MicroClusters PMC(CF1,CF2,w,c,r): 
	+ $C={p_1,p2,\dots , p_n}$ set of d-dimensional points
	+ $mc(C,t) = (CF1(t), CF2(t), W(t), center, radius)$
	+ $CF1(t) = \langle CF1_1(t) \dots CF1_d(t)\rangle$ weighted linear sum of coordinates along each dimension: $CF1_1(t) = \sum_{i=1}^n f(t,t_i)p_{i_j}$
	+ $CF2(t) = \langle CF2_1(t) \dots CF2_d(t)\rangle$ weighted square sum of coordinates along each dimension: $CF1_1(t) = \sum_{i=1}^n f(t,t_i)p^2_{i_j}$
	+ $w$ sum of weights of the data points $w=\sum_{i=1}^n f(t-t_i)$
	+ $c = \frac{CF1}{w}$
	+ $r = \sqrt{\frac{CF2}{w} - (\frac{CF1}{w})^2}$
	+ $w > \beta \mu_N$
+ Outlier microcluster OMC(CF1, CF2, w,c,r,to)
	+ to : creation time to decide whether the outlier microcluster is being evolving or is fading out.
	+ $w < \beta \mu_N$
+ Microclusters maintenance:
	+ Additivity: new point $p$ added at time $t+1$: 
		+ $mc \rightarrow mc \times 2^{-\lambda \delta t}$
		+ $mc = (CF1(t)+p,CF2(t)+p^2, W(t) +1)$
	+ Temporal multiplicity: If no points are added to mc during (t, t+\delta t): $mc \rightarrow mc \times 2^{-\lambda \delta t}$
+ Maximum weight of a microcluster:
	+ $w_{max} = lim_{t\leftarrow \infty} w = lim_{t\leftarrow \infty} \frac{1-2^{-\lambda (t+1)}}{1-2^{-\lambda}} = \frac{1}{1-2^{-\lambda}}$
	+ Minimum timespan of new created microcluster to grow into a potential microcluster: $T_p = \frac{1}{\lambda} log2(\frac{1}{1-\beta\mu_N (1-2^{-\lambda})}) - 1$
	+ Minimum timespan of potential microcluster to fade into an outlier microcluster: $T_d = \frac{1}{\lambda} log2(\beta \mu_N)$
	+  Minimum validity interval of an offline clustering is the time within which PreDeConStream does not need to update the offline clustering since it ramains valid because no change of the status of any microcluster status happened $T_v = min\{ T_p , T_d\}$	
+ Prefered dimension (microcluster prefers a dimension, if the variance of the microclusters that are in the Euclidean $\epsilon -neighborhood$ $\mathcal{N}_{\epsilon_F}(c)$ is bellow a theshold $\delta$
	+ $\deta$: variance threshold
+ Dimension preference vector:
	+ $\Phi(mc) = \langle \phi_1,\phi_2,\dots \phi_d  \rangle$
	+ $\phi_j = \kappa$ if $j$ is prefered, and 1 otherwise
	+ $\kappa >> 1$ is a constant
	+ $PDim(mc)$ Nb of prefered dimensions.
+ Data Structure to manage Microcluster
	+ the algorithm does not need to check for all potential microclusters, at each timestamp, whether the potential microcluster remains potential or fades into a deleted microcluster
	+ Microclusters are grouped into multiple lists according to their weights
	+ All microclusters that where not hit in the previous timestamp will fade to the lower-weighted list
	+ Borders: $W_d = 1$,$W_{min} = \beta \mu_N$, $W_{max} = \frac{1}{1-2^{-\lambda}}$ 
	+ Two types of lists:
		+ outlier lists $l_j^o$ : Inner border $w_i^p = \frac{w_{i-1}^p}{2^{-\lambda}}$
		+ potential lists: $l_i^p$: Inner border $w^o_i = 2^{-\lambda} w^o_{i-1}$ 
	+ Only the lists around $W_min$ from both outliers and potentials lists need to be checked each $T_v$ to see if the current offline clustering is still valid

## PreDeConStream Algorithm
+ Compute  $T_v$, $T_d$ and $T_v$
+ Initialize:
	+ Take initial data points
	+ If a point $p$ contains at least $\beta \mu_N$ points in their $\epsilon$-neighborhood. Add new potential microcluter and remove p and all its neighbors for initial points
	+ Repeat until no more potential microclusters are inserted into the lists
	+ The initial clustering is computed with an adapted version of PreDeCon
+ Get new point with the current time stamp $tc$
+ process the point:
	+ Search nearest potential microcluster $c_p$ in the list $l^p$
	+ merge p into $c_p$ if $radius_p \leq \epsilon_N$
	+ Otherwise: Search nearest outlier microcluster $c_o$ in $l^o$
	+ merge p into $c_o$ if $radius_o \leq \epsilon_N$ 
	+ If $w_o \geq \beta \mu_N$ insert $c_o$ into $l^p_min$ and remove it from $l^o_{max}$.
	+ otherwise create a new outliser microcluster with p
+ Maintain the microclusters in the data structure:
	+ For each newly created potential microcluster $c_p$:
		+ compute its subspace preference vector 
		+ For all potential microcluster $c_q$ in the $\epsilon_F$-neighborhood of $c_p$:
			+ update the subspace preference vector of $c_q$
			+ If the core proprerty of $c_q$ has changed add $c_q$ to $UPSEED_i$
	+ For each microcluster $c_d$ that fades out:
		+ For all potential microcluster $c_q$ in the $\epsilon_F$-neighborhood of $c_d$:
			+ update the subspace preference vector of $c_q$
			+ If the core proprerty of $c_q$ has changed add $c_q$ to $UPSEED_d$
	+ $UPSEED = UPSEED_i \cup UPSEED_d$
	+ Re-insert all the clusters in $UPSEED$ by calling the expandCluster function of PreDeCon considdering the old structure.
+ If ($t_c mod T_v = 0$) Update the macro cluster


