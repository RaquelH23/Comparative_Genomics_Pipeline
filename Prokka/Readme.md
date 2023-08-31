# Prokka
Prokka is a Python-based software that is used for annotating whole genomes of bacteria, viruses, or archaea. In this pipeline, it is used for annotating 43 Xanthomonas bacterial genomes.
![image](https://github.com/RaquelH23/cankerproject/assets/139277746/74e0f92d-b900-4a52-80b3-35b197add339)

#Create a list of the genomes fasta file and save it as FILE_NAME
### ls *.fasta | sed 's/.fasta//g' > FILE_NAME

#Create a loop so that each fasta file can be annotated
ml prokka
for x in 'cat FILE_NAME'
do
prokka --outdir "prokka__results_"$x --locustag $x"_gene" --cpus 4 --prefix $x $x".fasta"
done
#A folder named prokka_results_FILE_NAME will be created for each genome. Various file format documents will be obtained. The .gff file is required for the next step of the pipeline

# Acknowledgments
The [prokka] package used here is "v1.14.5" (https://github.com/tseemann/prokka)
