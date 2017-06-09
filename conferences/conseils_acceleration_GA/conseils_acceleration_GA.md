# Optimizations
+ Do not recompute the phenotype/fitness of a perfect-clone
+ Avoid modulo operation when it is not needed (modulo is recursive)
+ Power is also recursive (math.pow)
+ calcule scalaire (classique, 1 operation = 1 resultat) vs calcule SIMD avec SSE (Streaming SIMD extensions)/ SSE3 (1 operation = n resultats)
+ Utiliser des doubles et non pas des float entraine un coup de calcul plus fort pour les GPU et la compilation SSE

# Paralelization
+ If no problem of memory: OpenMP (simple)
+ If problem of memory: MPI (tres complique)
+ Execo a toolkit to automatise your experimentation campaign (Parameter sweep) ... Utile si sur machine partagee ... Sinon plus facile de le faire en bash

# Qund faire du GPU
+ Massivelly parallel part of program
+ Is the program omogenous in task or not
+ rewrite in cuda
+ Standford NVIDIA MOOC sur internet
+ OpenACC ou OpenMP: pragma and task based (garde code C en rajoutant quelques lignes)

????? bash schedular

