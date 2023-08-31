# Roary
Roary calculates the pan-genome from annotated assemblies using the .gff files obtained from prokka. The .gff file describes all the genomic features of all the genes in a genome. Roary outputs a gene_presence_absence.csv document, which contains each genome's genes. This master document can be analyzed in various ways; however, for the citrus canker project, the focus was to find core genes that were highly specific to _X. citri_ pv. _citri_ and _X. fuscans_ pv. _aurantifolii_ and whether these genes could be good targets in detection assays.
The gene_presence_absence.csv document attached here provides the pan-genome for the 43 Xanthomonads. The pan-genome contained 7644 genes, of which 3036 were core genes. The gene pool was manually scrutinized for genes that were not suitable primer candidates, such as transposons. Core genes of interest were selected for the next part of this pipeline.  

Move each genome's .gff files obtained from prokka into a new folder. Make a directory called FILES_gff and create a loop to move all the .gff files into that folder.   
   ````
mkdir gff_files
for x in 'cat FILE_NAME'
do
mv*/*.gff gff_files/
````

Run roary

```
module purge
ml roary
roary -e --mafft -p 4 -o roary_results -cd 100 gff_files/*.gff
```
Combine the gene_presence_absence.csv and gene_presence_absence.Rtab output files into a master Excel document. Using sort/filer, navigate through the genomes: 1 = presence and 0 = absence.

# Acknowledgements
The `roary` package used here is "version 3.11.2" (https://sanger-pathogens.github.io/Roary/)

