# Genome Rearrangement operations [Insights into structural variations and genome re-arrangements in prokaryotic genomes](http://bioinformatics.oxfordjournals.org/content/early/2014/09/03/bioinformatics.btu600.full.pdf+html)

+ illegitimate recombination events (homologous recombination)
+ imprecise non-homologous repair mechanism during aberrant DNA replication to repair broken replication forks
+ few kb to sometimes up-to millions of bp
+ Outcomes: 
	+ loss
	+ amplification (Andersson, et al., 1998)
	+ translocation (Block, et al., 2012)
	+ inversions (Johnson, 1991) 
	+ disruption of an existing gene (Jasin and Schimmel, 1984), 
	+ creation of a new gene (Nagarajan, et al., 2012) 
	+ chimeric gene product through gene fusions (Nogami, et al., 1985; Roth, et al., 1996). 
	+ altered gene copy number and thereby affecting its expression (Rebollo, et al., 1988): Deletions and duplications can potentially lead to altered doses of otherwise functionally intact elements
+ Types:
	+ Deletion
	+ Duplication	
	+ Inversion
	+ Translocation
	+ Insertion
+ Molecular predisposition:
	+ chromosomal contexts:
		+ sequence and structural motifs,
		+ repeat elements,
		+ insertion sequence (IS) elements
		+ transposon elements (TE) (Mahillon and Chandler, 1998; Treangen, et al., 2009). 
	+ Homologous repetitive segments within one chromosome or on different chromosomes can serve as sites for illegitimate crossing-over. 
	+ Extensive array of repetitive sequences, recombination hotspots (Aras, et al., 2003; Treangen, et al., 2009). 
	+ Generic repeats may arise by Horizontal Gene Transfert whereby the incoming DNA fragment contains the information already present in the host genome and integrates seamlessly into the host genome using site-specific recombination (Treangen, et al., 2009).

# Duplications

+ [Caractérisation et analyse évolutive des répétitions intragéniques : une étude au niveau des gènes, des séquences protéiques et des structures tridimensionnelles](https://tel.archives-ouvertes.fr/tel-00482373/file/these.pdf)
+ [all about mutations](http://web.stanford.edu/group/hopes/cgi-bin/hopes_test/all-about-mutations/#the-unequal-crossing-over-model)
+ [Adaptative amplification](http://www.tandfonline.com.sci-hub.cc/doi/full/10.1080/10409230701507757)

### Polymerase slippage model:

+ Polymerase slips from the template strand during replication. 
+ It causes the new strand to unpair (release) from the template strand.
+ The new strand tries to reattach to the template strand, it will have many identical copies of the codon to choose from.
+ With so many identical codon copies to reattach to, the new strand may reattach to the template at the wrong copy.
+ Repair mechanisms may lead to deletion or duplication 
+ Small duplications require little energy (for slippage to occure) and are easily accounted for by the slippage model. 
+ However, many of the expansions that researchers see are quite large, sometimes in the hundreds of repeats. Slippage as the cause of these large expansions would be energetically unfavorable.
+ Can be enhanced by harpin loops (larger duplications and deletions can appear)

### Homologous recombination:

+ Appears thanks to structure called Amplicon:
	+ DNA sequence surounded by primers (repeted sequences)
+ 3 mechanisms:
	+ Unequal crossing over => tandem repetitions of variable sizes (or deletions)
	+ Excision of replicon and then insertion in the genome (same chromosome or distincct one)
	+ Circular replicon =>
		+ double strand break + single gap in one strand
		+ annealing between the portion around the double break and the compelmentary strand in the gap
		+ circle closed by ligation
		+ replication fork stablished in the circle
		+ elongation of sequence in the circle (several duplications)
		+ Circle breaks and strands are linked (at double strand break point)

### Transposable elements:

+ 2 sort of TE (creates separated duplications):
	+ class 1 (RNA dependent):
		+ Gene is transcribed
		+ Reverse transcription
		+ 2 sort of insertions into the genome:
			+ LTR (Long Terminal Repeat), if the TE has repeated sequences siding the sequence, insertion by recombination in zones containing repeated sequences
			+ no-LTR, in this case the TE gets inserted in double strand break points
	+ class 2 (DNA dependent):
		+ The element is cut from the genome => double strand break 
		+ Paste somewhere else
		+ If another copy is around it can get pasted there (double strand break point)
		+ If there cell under replication the segment can be inserted and transcribed, and clipped, so finally a new free element will exist see this [link](https://es.wikipedia.org/wiki/Transposón#/media/File:Transposición_no_conservativa.png)


### Gene convertion
+ Homologus recombination with replacement of one sequence by another => correction of a mutated sequece.

# [Genesis, effects and fates of repeats in prokaryotic genomes](http://femsre.oxfordjournals.org/content/33/3/539.abstract)

+ Cause creation:
	+ Intrachromosomal recombination
	+ horizontal transfer
+ recombination operations: 
	+ amplifications, 
	+ deletions
	+ rearrangements 
+ Types: immense diversity of repeats in genomes
	+ created by selfish elements 
	+ protection against selfish elements
	+ transient gene amplifications 
	+ stable duplications. 
	+ some repeats do not carry any adaptive value
	+ Allow functional diversification and increased expression. 
	+ Number and types of repeats are also quite diverse and in line with ecological variables, such as host-dependent associations or population sizes, and with genetic variables, such as the recombination machinery
+ Role:
	+ play extremely important roles in genome stability and plasticity.
	+ Through recombination, repeats increase the rates of rearrangement, amplification and deletion of genetic material
	+ Deletions and amplifications of short tandem repeats are particularly frequent
	+ nonreciprocal recombination (gene conversion), repeats can also lead to new combinations of pre-existing alleles.
	+ Finally, closely spaced inverted repeats (IRs) result in structured DNA or RNA molecules. Repeated elements have the potential to increase genome plasticity and have been recruited to produce localizing sequence diversification by recombination processes.

###What is a DNA repeat? Multiple perspectives on repeats

+ Repeats:
	+ Source of functional overlapping:
		+ Establish an association between genetic elements 
		+ Redundancy:  two proteins with a similar protein domain, duplicated genes or operons
		+ similar copies of a repeat in their regulatory regions: associations between genes in genetic networks.
	+ Source of sequence recombination: 
		+ mechanisms require some level of sequence similarity between the sequences.
		+ RecA promotes strand exchange between homologous or homeologous sequences
		+ RecA dependent recombination steps:
			+ efficiency decreases exponentially with sequence divergence: 
		+ Slipped-strand mispairing
			+ Decreases exponentially with the distance between the copies of the repeat (Che ́din et al., 1994; Lovett et al., 1994) 
			+ increases with the length of the repeated elements (Peeters et al., 1988; Pierce et al., 1991).

### The origin of repeats

#### Generic repeats

+ Cause:
	+ horizontal gene transfer:
		+ creation of repeats whenever the incoming DNA contains elements similar to information already present in the genome.
		+ integration into genome by:
			+ site-specific recombination (e.g., phage integrase)
			+ Homologus recombination:
				+ if  incoming DNA contains homology with the chromosome at both extremities => double cross-over leads to genetic replacement (Niaudet et al., 1985).
				+ if incoming DNA is circular => then one single region of similarity with the chromosome allows integration of the genetic element by homologous recombination in a Campbell-like manner (Duncan et al., 1978). =>  repeats are created close together as they are spaced by the sequence of the incoming element.
	+ homologous recombination between smaller or more degenerate repeats:
		+ Leads to gene conversion:
			+ increase the region of similarity between the elements
			+ Creates larger repeats (Santoyo & Romero, 2005)
			+ Maintains the sequence similarity between repetitive elements (Harvey & Hill, 1990) (Hughes, 2000).
		+ Some sequences escape from gene conversion:
			+ The sequence may diverges after a given threshold, it may become free from the homogenizing effect of gene conversion because recombination frequency drops exponentially 
	+ Illegitimate recombination between potentially very small and close repeats:
		+ Illegitimate recombination between small degenerate closely spaced 
			+ Cause dislocation mutagenesis => production of a strict repeat from a degenerate one (Schaaper, 1988).
			+ Given slipped-strand mispairing properties => repeats must be nearby in the genome but they may only be a few nucleotides long. Such repeats can be so small that they are easily found in genetic texts (Karlin & Cardon, 1994). 
		+ amplicon model of repeat generation (Romero & Palacios, 1997)
			+ First, illegitimate recombination leads to the creation of short close repeats (slippage events  (Edlund & Normark, 1981) ). 
			+ Second, these repeats are low-frequency amplicons that may amplify in tandem.
			+ Third, resulting amplifications are large and can expand and contract by homologous recombination (Levinson & Gutman, 1987)

#### Selfish elements

+ Transposable Elements (TE): 
	+ retrotransposons or class I elements:
		+ RNA intermediate
	+ DNA transposons or class II elements:
		+ DNA intermediate. 
		+ Most frequent and repetitive in prokariots
		+ IS are the most aboundant members
			+ Carry one or two ORFs encoding the transposase
			+ generally (but not always) flanked by short IRs  (Mahillon & Chandler, 1998).
			+ Composite transposons are elements flanked by IS elements
			+ noncomposite transposons are flanked only by IRs
			+  Transposons may carry unrelated genes such depending on their mechanism of transposition (for a review, see Mahillon & Chandler, 1998).
		+ TEs move in genome by a process that is independent of DNA homology:
			+ cut-and-paste
			+ copy-and-paste : if transposition takes place at the moment of replication from a newly replicated region to a nonreplicated region
	+ 3 prokaryotic types:
		+ Group II introns (Ferat & Michel, 1993; Simon et al., 2008):
			+ distributed among all three domains of life
			+ self-splicing. Muliply via reverse transcription 	
		+ retrons (Temin, 1989; Lampson et al., 2005) 
			+ multicopy single-stranded DNA covalently linked to RNA 
			+ reverse transcibed
		+ diversity-generating retroelements (Medhekar & Miller, 2007).
			+ selective advantage by introducing vast amounts of sequence diversity into target genes (Doulatov et al., 2004).

### The functional consequences of repeats

#### Gene genesis by duplication and divergence

+ most evolutionary novelty is thought to arise from the duplication and divergence of pre-existing elements (Ohno, 1970; Taylor & Raes, 2004).
+ Gene duplication creates redundancy, thus freeing the copies from some functional constraints. If the copies are effectively redundant, then one of them is likely to be lost by lack of selection against inactivating mutations
+ However, in rare cases, the accumulation of mutations may lead either to:
	+ neofunctionalization, one of the copies acquires a new function
	+ subfunctionalization, the two copies specialize in subfunctions of the primitive gene (Fig. 6) (Lynch & Katju, 2004)
	+ Both rely heavily on the accumulation of point mutations. 
+ If there is strong selection for both copies at the time of amplification, then the amplification will be stable and mutational processes could have much more time to diversify the function of the genes (Francino, 2005; Bergthorsson et al., 2007):
	+ e.g.,A gene confers a secondary function with weak efficiency 
	+ Need for that function increases,
	+ Amplification of the gene is selected
	+ amplified gene accumulates mutations in the different copies. 
	+ Mutations in one of the copies of the gene allowing an increase in efficiency of the secondary function become highly adaptive. 
	+ Other copies could be deleted or be used for the primary or other function 
	+ Leads to subfunctionalization (Francino, 2005). 
	+ Might be a frequent event (Patrick et al., 2007).
	+ Bias of deletion over amplification in prokaryotic genomes (Lawrence et al., 2001; Mira et al., 2001). Once repeats are created by recombination, typically in tandem, they are then deleted at high rates 
	+ gene conversion homogenize the two copies of the gene => reduce sequence divergence and slow subfunctionalization and neofunctionalization (Santoyo & Romero, 2005).
	+ large rearrangements tend to be highly deleterious (Rocha, 2008). Repeats can be stabilized if, after creation in tandem, they are physically separated by chromosome rearrangements (Achaz et al., 2000).
	+ CONCLUSION: ample evidence for gene amplifications in genomes, demonstrated by the abundance of repeated elements and some large families of paralogues (Snel et al., 2002; Gevers et al., 2004; Alm et al., 2006; Cho et al., 2007). It is unclear whether gene amplifications last long enough to be responsible for the creation of these large gene families (Lerat et al., 2005), but it is not clear...

+ Horizontal Transfert:
	+ quick avenue for acquiring functions that have already endured selection in other contexts
	+ ample evidence that it brings new genes into most genomes at very high rates (Hao & Golding, 2006)

### Intragenic repeats and the evolution of protein function

+ Repeats exist inside genes and cause intragenic amplifications of genetic material.
+ Intragenic amplification => direct influence of DNA sequences on protein sequences: consequences at the three levels (DNA seq, protein seq, struccture) often deleterious consequences.
+ Many proteins contain repeated zones. 
+ Several proteins contain the same domains
+ Domain duplication is one of the main sources of new domains (Vogel et al., 2004).
+ Tandem repeats can lead to misfolding and are typically avoided by proteins.
+ Some proteins evolve by amplifying domains (quite rare however).
+ When repeats are found in tandem, some residues named structural gatekeepers may prevent the proteins from misfolding.

## The evolutionary impact of repeats

### Repeats, recombination and adaptation

+ Schematically, environmental challenges can be classified according to
	+ frequency with which they arise
	+ possibility of building appropriate physiological responses to tackle them.
	+ The evolutionary patterns associated with adaptation depends on both 
+ Stresses
	+ tackled by a physiological response based on the regulated expression of a set of proteins
	+ Usually stresses are too complex, too elusive or too quickly lethal to be handled by a well-regulated stress response.
	+ selection will purge the elements in the population that are unable to find a qualified solution to the standing challenge.
+ Mutators
	+ Point mutations => slow generation of genetic novelty
	+ Needs for increasing the mutation rates in times of stress (Bjedov et al., 2003) 
	+ substantial burden of deleterious mutations (Sniegowski et al., 2000)
	+ when stresses are frequent and can be tackled by the generation of variability at a reduced number of loci: there is often selection for the maintenance of repeats engaging in recombination at those loci. In this case, repeats are under second-order selection because they generate at high rates the adaptive changes with which they hitchhike to fixation (Tenaillon et al., 2001). This does not suppose any sort of directionality; repeats will recombine randomly, resulting in sequence reassortment or gene conversion. When such events have a high probability of leading to adaptive changes, then the associated repeats will propagate in the population. On the other hand, repeats generating deleterious changes with a high frequency will in general be purged by the action of natural selection.
+ Programmed hotspots of variation by recombination 
	+ associated with functions managing antagonistic social interactions (e.g., during arms races both partners are continuously changing to keep the other in check (Van Valen, 1973).)	
	+ Usually associated to negative frequency-dependent selection, i.e. a given variant is highly adaptive only when rare.
+ Many forms of diversifying selection share the peculiarity that they hardly select for higher efficiency, but instead for sequences that are different while performing an equivalent function.

### Repeats as evolutionary reservoirs

+ Homologous recombination between one (or a few) master gene and copies of it allows sequence variation without loss of function.
+ Repeats leading to recombination events with better results (i.e., diverse but functional variants), will be selected for.
+ This creates evolutionary reservoirs in the form of repeats scattered in the chromosome (Palmer & Brayton, 2007). 
	+ e.g. Borrelia: 
		+ large number of plasmids containing the vast majority of repeated elements of the genome (Casjens, 1999).
		+ Antigenic variation is under strong selection and proceeds by recombination processes within the repeats present in the plasmids (Norris, 2006). 
		+ antigenic variation results from replacement of internal segments of varied lengths of the master gene by gene conversion resulting from its recombination with the repeated elements (Zhang et al., 1997). 
		+ Replacements occur at high frequencies during infection, thereby allowing continuous escape from the immune system (McDowell et al., 2002).

### Transient gene inactivation

Gene deletions may be highly adaptive in contexts of host–pathogen associations or for the adoption of new ecological niches (Sokurenko et al., 1999), even though they are expected to lower the cell fitness in the original habitat. 

+ Gene deletions may arise from recombination between repeats (Gaudriault et al., 2008) 
+ Occurs at high rates among mismatch repair genes in enterobacteria (Bjedov et al., 2003) rich in close repeats (Rocha et al., 2002),
+ The loss of these genes increases mutations rates 100- to 1000-fold. 
+ High load of deleterious changes, but in maladapted populations, the rate of adaptive mutations may be enough to allow mutators to increase in frequency (Taddei et al., 1997). 
+ Adaptive for the new variant to revert to the nonmutator phenotype
	+ This occurs at high frequencies because the loss of mismatch repair renders homologous recombination more permissive
	+ Which facilitates the recovery of the intact genes by horizontal transfer.
+ Losing a mismatch gene increases the likelihood of receiving one by horizontal transfer because recombination barriers are diminished. Most genes have no such feedback effect.
+ Strategy is limited to prokaryotes with high rates of horizontal gene transfer
+ Sexual isolation => gene deletion is irreversible. In this case, the larger the number of repeats in a gene, the more likely its irreversible deletion from the genome. 

### Transient gene silencing

+ Reversible way of function gain and loss: gene expression regulation (turned on or off under specific conditions). 
+ Contingency loci are elements that are stochastically turned on and off resulting in random variation, phase variation, of the expression of the proteins under diversifying selection (Moxon et al., 1994) => Quasi species like: The population is now a distribution
+ Involve homologous recombination between one master gene and repeats in the chromosomes. In this case, recombination leads to gene inactivation or silencing. (Swanson et al., 1986).
+ Site-specific recombination systems are activated stochastically to produce chromosomal rearrangements leading to phase variation (Komano, 1999). 
+ SSR (short repeated sequences in tandems) are less frequent than expected in prokaryotic genomes, especially inside genes (hence typically purged from genomes) (Field & Wills, 1998; Ackermann & Chao, 2006)
+ When present, they are often associated with genes under diversifying selection.
+ Important property of SSR is that changes in copy number are heritable and reversible. By subsequent contraction and expansions, it is possible for a gene to oscillate between expression and silencing. This is unattainable for deletions between spaced repeats, which require hazardous recovery of the missing sequence by horizontal transfer.
+ Gene deletion in mutS amplifies mutation rates in general, but more intensely so in SSR. This shows the tight associations that can be created within the different ways of generating variability in times of stress by means of recombination between repeats. While recombination between repeats may inactivate genes associated with mismatch repair, the loss of the latter leads to higher and more permissive recombina- tion processes that result in further generation of genetic diversity.

### The impact of selfish-DNA
Upon insertion, TEs may affect the expression of nearby genes, either by interrupting/silencing them or by enhancing their expression.

+ TE elements also provide a structural basis to
	+ duplications, 
	+ deletions, 
	+ rearrangements
	+ incorporation of foreign DNA either by active transposition or by homologous recombination between the multiple copies present in a genome (Naas et al., 1995; Alokam et al., 2002; Kothapalli et al., 2005; Redder & Garrett, 2006).
	+ mediate the transfer of genetic information between genomes or between replicons of the same genome. 
	+ TE are believed to undergo frequent horizontal transfer and cycles of expansion and extinction within a given species, most likely as a consequence of transfer between genomes and plasmids (Wagner, 2006). 
	+ Important source of genomic diversity and plasticity (Schneider et al., 2002; Brugger et al., 2004; Nascimento et al., 2004; Yang et al., 2005). 
	+ genome size is to date the only statistically significant determinant of IS abundance (Touchon & Rocha, 2007). Indeed, the numbers and density of IS increase rapidly with genome size, which is the exact inverse trend found for the density of genes under strong selection such as essential genes, suggesting that ISs are as strongly counter-selected as the average gene is under strong selection.

### Transient amplifications and amplicons

+ two repeats separated by a spacer have the capacity to serve as amplicons, i.e., units that may amplify in tandem.
+ If the flanking repeats are long and distant, the amplification will engage homologous recombination.
+ If the repeats are close they will engage slipped-strand mispairing.
+ If they are both long and close they will engage both. 
+ Doubts surrounding the relevance of such structures for the creation of stable paralogues
+ many results show that these structures accelerate adaptation by transient amplifications of genetic material (Anderson & Roth, 1977). 
+ In some rare cases, amplicons are extremely deleterious because they duplicate genetic elements that are needed in strictly single copies, but in the majority of cases they are neutral, i.e. without effect on fitness, beneficial or only mildly deleterious.
+ frequency of recombination depends on the repeat size and similarity, their relative distance, the natural selection of the ensuing amplification and the probability of recombination between such chromosomal locations.
+ Most amplicons are very stable and amplify at low rates. Yet, amplification produces large tandem repeats that recombine at high frequencies. The very large repeats resulting from amplifications are remarkably unstable, and homologous recombination quickly leads to either deletion or further amplification (Romero & Palacios, 1997).
+ the rate-limiting step of the process corresponds to the initial amplification. 
+ Tandem copied genes can occupy significant fractions of the chromosome (Jannie`re et al., 1985) (Smith et al., 1988). 
+ Some amplicons may attain particularly high amplification numbers => rolling-circle replication (Petit et al., 1992). 
+ It has even been proposed that clusters of functional neighboring genes, such as operons, are maintained to allow their coamplification (Reams & Neidle, 2004).
+ plasmids may insert in the chromosome by duplication insertion, involving the production by homologous recombination of two copies of a repeat at the edges of the integrated element => structure of an amplicon. Elements integrated in this way are immediately ready to be further amplified (Haldenwang et al., 1980; Smith et al., 1988). 
+ Laterally transferred genes are typically maladapted for expression on the host because their regulatory genes do not allow optimized expression. If they are amplified in the chromosome in high copy number, they may then adapt more rapidly by the joint action of three effects.
	+ amplified regions offer a larger mutation target (more mutations accumulating in the amplified set of genes than in a single-gene locus).
	+ recombination between repeats may engage the action of an error-prone polymerase and thus become locally mutagenic.
	+ repeats will accumulate changes and allele reassortment may occur within chromosomes by recombination between the copies, accelerating the combination of favorable changes in one gene. 

## The fate of repeats

+ It is the fate of repeats to disappear. 
+ This can take very diverse time frames depending on the repeats. 
+ Genes under prolonged selection for gene dosage effects will last in genomes until such selection ceases.
+ Some repeats will fade away because they accumulate point mutations. Even if they may remain in genomes, they will end up by losing the ability to recombine and therefore cease to be considered as repeats. 
+ Repeats carrying no significant lasting advantage will disappear quickly either by deletion or by counter-selection
+ Hence, while genomic rearrangement rates are close to genomic mutation rates, rearrangements are much more rarely fixed in populations than point substitutions because of their deleterious effects. Because the stability of genomes is largely a result of the rearrangements between repeats and ensuing natural selection, this means that:
	+ selection for organization is extremely strong and the vast majority of rearrangements are purged (Rocha, 2006); 
	+ genomes with many repeats exhibit high rearrangement rates and are less fit regarding chromosome organization and gene repertoire stability (Rocha, 2003b)
+ The size of genomes is largely the result of the balance of forces increasing genetic information, horizontal transfer and amplifications, and forces removing genetic information, selection and genetic deletions. 
+ The genome will not increase too much since:
	+ The limiting step in the formation of the amplicon is the creation of the flanking repeats. A deletion of these repeats will result in a sequence that will lead to a new amplicon at very low rates
	+ large tandems of amplicons are expected to cause genetic instability and they create a severe imbalance in the gene dosage. 
	+ These will result in a deletion bias (Koch, 1979).
+ Structure of repeats have different consequences (For the same number of repeats):
	+ certain chromosomal distributions of the copies are less disruptive upon deletion: 
		+ close repeats will affect smaller fractions of the genome. 
		+ repeats tend to be distributed nonrandomly in genomes in such a way as to exert less negative effects on the chromosome upon recombination than expected by chance (Achaz et al., 2003).

#[turning a hobby into a job](http://www.nature.com/nrg/journal/v9/n12/abs/nrg2482.html)

##which genes undergo duplications:

+ Pattern that seems to hold only for small-scale duplications (SSDs), not for WGD16 (see below)
	+ less densely clustered parts of the protein-interaction network => fewer pleiotropic constraints
	+ Fewer pleiotropic constraints(14)
	+ with smaller fitness defects when knocked out(15)
+ indirect association between lower rates of evolution and essentiality (17)
+ Explantation:
	+ Certain types of genes have biochemical features that allow them to be adapted easily to novel functions (substrate promiscuity)
	+ Other types of genes might be particularly unlikely to undergo functional innovation via duplication, because the duplication has an immediate detrimental effect (so-called duplication-resistant genes(18)). => MOST SUPPORTED HYPOTHESIS
		+ i.e., highly constrained cellular systems => selectively unfavourable is termed the dosage-balance hypothesis(1)

##Single-gene duplications versus whole-genome duplications

+ Anticorrelation between genes fixed in duplicate after SGD and those surviving from WGD: Genes in a functional category are duplicated by SSD and not by WGD or  vice versa. (25, 20)
+ WGD tend to diverge in expression more quickly (26)
+ Duplicates produced by WGD also seem to share more protein interactions after duplication than do genes duplicated by SSD (26, 27)
+ Enzymes retained in duplicate after WGD seem to have fitness defects at least as large as those for the genes that are not retained(16)
+ Dosage is not affected by WGD => WGD events might allow certain evolutionary novelties to appear and be selected for that would have been unlikely to arise otherwise.  
+ WGD might also allow innovation through changes in relative gene dosage. 
	+ WGD may allow all the genes in a pathway to increase their relative dosages simultaneously, simply by remaining in duplicate as the rest of the genome shrinks
+ WGD duplicate genes retain substantial degrees of functional overlap for long periods (31,32)
+ Many WGD loci that are fixed in duplicate in one yeast species are single-copy in others(33) => point to a high frequency of neofunctionalization.

### The nature of co-option

+ Co-option often occurs using some evolved feature of the gene in question, although perhaps in a surprising way (29, 34, 35)
+ Co-option can also result in proteins being used for functions that are seemingly unrelated to their evolved role (37, 38, 39)

### Natural selection and co-option

+ In the absence of other factors, gene duplications are expected to be either selectively neutral(43) or detrimental(44, 46)
+ Three life stages of a duplicate gene pair: 
	+ creation (mutation in a single individual)
	+ fixation–preservation (in the whole population by selection or drift)
		+ Neofunctionalization:
			+ New function on one member of a duplicate gene pair occurs after the duplication(51)
			+ Gene appropriated for adaptation after duplication has a function that is closely related to the function required => novelty is built on a conserved enzymatic mechanism.
		+ Subfunctionalization:
			+ Functions of an ancestrally multifunctional gene have become divided up neutrally among the daughter copies (degeneration, complementation model) (9, 37, 50)
			+ escape from adaptive conflict (EAC) model (59–61): The two functions of the ancestral gene cannot simultaneously be optimized by natural selection. After gene duplication, the two daughter genes can escape from the conflict.
			+ Several studies have suggested that the extant features of networks, such as those of protein–protein interactions and transcriptional regulation, are compatible with a node (gene) duplication model (64–66)
		+ Dosage
			+ Duplicate gene pairs  preserved by selection for increased gene dosage (70) => selectively advantageous at birth
			+ Selection for higher gene dosage might increase the likelihood of a later neofunctionalization event by prolonging the half-life of a duplicate gene pair.
		+ Building new functions by dosage selection
			+ A gene does not address only one function it also encode minor activities (78) (promiscuous protein activities)
			+ These minor activities can also evolve into new functions: reservoir of functional novelty
			+ Combine Selection for gene dosage and Neofunctionalization of minor activities : adaptive amplification (88,89) adaptive radiation(90) or IAD(45, 90) model
				+ Duplications are selected in certain genes with weak but beneficial activities.
				+ The tandem arrays of duplicates that this selection maintains have an increased rate of beneficial, activity-enhancing mutations owing to the large number of mutational targets.
				+ Once such muta- tions have been fixed, selection to maintain the duplicated array is reduced and the extra copies are lost
				+ leaving only the ancestral gene and the new duplicate with a novel function
	+ optimization
	+ (loss of a duplication is by far the most common fate)


# Ideas for program:

+ Repeated elements mark the position for futur insertion of elements => higher probability to receive new TE or Horizontal Transfert sequences  
+ Repeated elements are received through Horizontal gene transfert
+ It is possible to measure the essentiality of a gene (decrease of SAE it permits). So a possibility could be to have more chances to undergo duplications for non essential genes (at constant number of genes associated)
+ In order to respect the dosage effect hypothesis, the effect of duplication should be relative to the relative difference of number of genes in the same pathway (cluster). If only one gene of a cluster is duplicated => its position changes and not the other ones (e.g., twice further). I all genes are duplicated, the position of the core-points does not change.
+ Gene conversion => That is way we do not keep track of the sequence . . .  usually it will be homogenized by gene conversion, until it escapes and tackles a new function
+ If the gene becomes too different (e.g., works for another centroid) we can consider that it becomes free to moove => less likelly to copy 2 genes of unrelated functions together.
+ Gene conversion from Horizontal gene transfert => We replace the location along a given dimension only considering points belonging to the core-point (and not very far away).
+ Amplification: various copies of same gene => weight matrix (less likelly to be at the origin of novelty)
+ Acquisition of new gene: Horizontal Gene Transfert => taking elements from the dataset (very likelly to be at the origin of novelty)
+ Another possibility to describe the mutation of existing genes (with various copies is the Homologous recombination between one (or a few) master gene and copies of it allows sequence variation without loss of function.)
+ To which function contribute Horizontal Gene transfert in probability?
+ Transient gene inactivation => It should be possible to give recently deleted genes/corepoints in Horizontal Gene Transfert from time to time. Simulaitng though that the gene is still in the population => Larger memory
+ Muators lead specially to more mutations on repeated parts
+ Genome size is positivelly correlated with the number of IS => More recombination => Bigger genomes  will undergo more mutations. Small genomes rich on vital genes have few IS => less recombination
+ Amplicons are quite stables but the amplified sequences are very variable => have a weight of 1 <=> genome of amplicons and they are specially unstable when they have more copies. Rate limiting step in amplification are the initial steps. There are mechanisms that allow more rapid duplication (circular)
+ Laterally tranfered genes are usually maladapted and amplification can help them to be more adapted:
	 
