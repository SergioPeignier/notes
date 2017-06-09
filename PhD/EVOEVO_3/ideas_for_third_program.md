# Operations

## Horizontal Gene Transfert (HGT):
+ Comobilization of a genetic region required for common function (not only one gene but functional sets of genes)
+ Can recombine with similar portions in the genome 
	+ Gene conversion: Gene repairment by homologus recombination of HGT (corepair)
	+ Can lead to duplicate:  Almost random insertion in genomes and  large range of sequence similarity relative to the native homolog.
	+ Increase in protein family sizes are more related to HGT => May be we can consider that if genes are not present in clusters in the same proportions => they do not co-localize
	+ HGT share less protein-protein interactions and regulatory mechanisms: Very suitable for new clusters
+ Can integrate a new entire function 
+ Occurs at very high rate
+ Consequently we can make a probability to create a new core-point or try to repair and existing one, depending on the distance to existing core-points

## Amplification (A):

+ Tandem duplication can create side by side several gene copies.
+ Increase adaptative mutation rate. 
	+ Gene with weak function of set of genes => co-amplified => restore function. 
	+ Higher chance of reversion or acquisition of compensatory mutation
+ Rudimentary form of regulation: reversible change in dosage => enable adaptation to variable environments
+ Novel functions: 
	+ Duplication and divergence (subfunctionalization, neofunctionalization)
+ Deamplification often occurs quickly after:
	+ removal of selective pressure 
	+ Acquisition of compensatory mutation
+ Most amplicons are stable and amplify at low rate but amplification generates tandem repeats that recombine at high frequencies. 
	+ Tandems are very unstable => deletion or amplification.
	+ Recombination is more frequent between close genes and similar genes		
	+ Rate-limiting step => initial amplification

## Duplicates:

+ Evolutionnary reservoirs:
	+ Mutators => Increase mutation rate in stress times (deletion of reparing genes)
	+ multiple repeats => Increase homologus recombination => increase instability (number of duplicates generated and mutations)
	+ Frequent stresses => generate variability at reduced number of loci => maintenance of repeats (recombination)
	+ repeats undergo conversion which tend to keep them alike
+ Divergence:
	+ Reduce homologus recombination of repeats (repeats regions has less mutations)
	+ Reduce gene conversion which keep repeats alike and thus lead to more recombination
	+ Selection of duplicate genes (paralogs) that diverged and obtained a new function: 
		+ subfunctionalization: 
			+ The two copies specialize in subfunctions of the primitive gene 
			+ Alows to escape from adaptative conflict (2 functions cannot be optimized on the same gene). By splitting the two functions => independence of evolution.
		+ neofunctionalization: 
			+ One copy acquire a new function. 
			+ Close related to the function required. Novelty built on a conserved enzymatuc mechanism
	+ If selection for amplification is stable: Genes have more time to diverge and adress a new function (related to the first one) and be selected. This new function may be inefficient and need amplification ...
+ Deletion:
	+ Arise from recombination between repeats at high rates
+ Silencing by mutational inactivation
	+ Accumulation of point substitution => pseudo-gene (too diferent to be repeats and recombine)
		
## Genome size: 

+ Number and density of IS encrease rapidly with genome size (so more recombination and mutations)
+ Will not increase too much:
	+ Amplicons are stable
	+ Only when turned into tandems they become unstable
	+ Deletion => back again to limiting step
	

## HGT and A

+ HGT genes are typically maladapted for expression on the host => Through amplification => adapt more rapidly by the joint action of three effects.
	+ amplified regions offer a larger mutation target (more mutations accumulating in the amplified set of genes than in a single-gene locus).
	+ recombination between repeats may engage the action of an error-prone polymerase and thus become locally mutagenic.
	+ repeats will accumulate changes and allele reassortment may occur within chromosomes by recombination between the copies, accelerating the combination of favorable changes in one gene. 
+ HGT usually undergo A and usually lead to paralog retention
+ A gene inserted besides an existing through HGT is ready for amplification.
+ New functions acquired could undergo amplification.

# Ideas for program

## HGT

+ Given that an entire genetic region is co-mobilized we can insert several dimensions at once => how to choose dimensions
+ Given that HGT can be inserted in the genome according to similarity (conversion or insertion) => Probability to assign to a cluster as a function of its distance
+ Start amplification directly after?
+ Idea: Compute the probability to be assigned to each particular core-point, if an existing one is chosen, only take:
	+ the dimensions in the core-point
	+ more? 
	+ May be only the remaining dimensions => specially given that protein family increase is more related to HGT and random insertion in genome
+ Otherwise take random dimensions (how many?)

## Amplification

+ Should be low if only one gene exists
+ Amplification of N genes => Add N coordinates from the cluster (along the chosen dimension or several of them depending on the region that is going to be amplified) compute the mean and update the location and the weights
+ P(amplification) = f(W)
+ P(amplify all genes in cluster) = f(W/Nb_genes)

## Deamplification

+ If compensatory mutation or no more selective pressure => No change on fitness
+ We can assume that a compensatory mutation arises very quickly and then we can lose genes without degradation only updating W? 
+ We can update the W and the location by removing a random coordinate taken from the dataset? 

## Recombination, mutation hotspot

+ Take N new elements (the ones that will recombine) and update the mean without changing W

## Divergence of duplicates

+ Pseudogene:
	+ P(number of duplicates) => one gene becomes a pseudogene (impact on location? ... may be we can do the same as for Deamplificaiton)
+ Sub/neo-functionalization:
	+ Add a new dimension in the same cluster taking a coordinate in the cluster points along this dimension
	+ Start amplification?
	+ Remove one element in the previous gene (do the same as for deamplification)

## General ideas:

+ Maybe we can say that single duplications events (from W=1 to further), creation of new dimensions (ne-functionalization) and HGT lead to amplification.
+ Amplification can also arise in tandem genes
+ Deamplification has no impact on the location
+ Pseudogeneation has no impact on the location
+ Number of mutational events is a function of the the genome size
+ Can we use non-functional elements as another mark to see which regions will be more likely to undergo simple duplication and simple deletion? 
+ Using medians will be probably more complicate for aggregations.
+ Another nice idea was to keep points in clusters (as DBSCAN core-points) to generate various shapes => more complicate given our little amount of time
+ We can have an implicit population as in Kymero
+ Given that searching centroids is coherent with minimization of euclidian distance, we will probably need to move towards euclidian distance.
+ If we use centroids can we have a fast way to see if the modification is positive or not without computing all distances? 
+ We can use the variance as in PROCLUS to exclude dimensions that are too spread.
