# Fasta2primer3
Fasta2primer3 is a python package for designing and developing primers. It was used at the end of the comparative genomics pipeline for developing RPA universal primers to detect all strains of the pathogens causing citrus canker disease. The input file for `fasta2primer3` is the file path of a `.fasta` file.

### Gene file preparation
After analyzing the genes of interest from the combined excel file outputs from roary, create a list of the genes of interest from one of the genomes and save as Gene_List.
Extract the fasta file for the selected genes in the Gene_List and save as Target_List.fasta


`ml seqtk`

`seqtk subseq /FILE_PATH/prokka_results_GeneName.ffn Gene_List > Target_List.fasta`

Provide the file path leading to the .ffn file for the selected genome. The .ffn file is found from step 3 - prokka output

Here you can BLASTn the selected genes OR proceed to primer design then BLASTn the primers.

### Changing primer design parameters
Change default settings to reflect parameters for RPA or PCR design. RPA primer parameters used for the Xanthomonas comparative genomics study were: min size -30, max size -35, opt size -32, product size range -100 to 200bp, min TM -10, Max TM -100, opt TM -60 (TM is not a factor for RPA primers therefore this wide range in the melting temperature is required in order for the software to produce primers). The file [Pipeline_primer_orig.xlsx] contains the RPA primers obtained from this study using `fasta2primer3.

```
ml python/2.7.18
ml primer3
python fasta2primer3.py /FILE_PATH_TO Gene_List.fasta
```

# Acknowledgements
The `fasta2primer3` package used here is (https://github.com/frba/fasta2primer3)
