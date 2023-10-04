# Prokka
Prokka is a Python-based software that rapidly annotate genes and identify coding sequences in prokaryotic genomes. It was used here for annotating 43 Xanthomonas bacterial genomes. 

Create a list of the genomes fasta file and save it as FILE_NAME

`ls *.fasta | sed 's/.fasta//g' > FILE_NAME`

Create a loop so that each fasta file can be annotated
`````
ml prokka
for x in 'cat FILE_NAME'
do
prokka --outdir "prokka__results_"$x --locustag $x"_gene" --cpus 4 --prefix $x $x".fasta"
done
`````
A folder named prokka_results_FILE_NAME will be created for each genome. Various file format documents will be obtained. The .gff file is required for the next step of the pipeline


# Acknowledgments
The `prokka` package used here is "v1.14.5" (https://github.com/tseemann/prokka)
