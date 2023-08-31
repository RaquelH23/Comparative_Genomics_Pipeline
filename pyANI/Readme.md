# Pyani
Pyani is a Python-based software package that classifies the genomes and calculates the genomes' average nucleotide identity and relatedness.

The Xanthomonas comparative genomics study evaluated 43 genomes, which comprised the 5 strains of citrus canker. The pathogens clustered into two distinct groups. Group 1 contained the Asiatic strains, while Group B contained the South American strains. The documents ANIm_percentage_identity.pdf and ANIm_alignment_coverage.pdf illustrate clearly the two groups and their relatedness. The ANIm_percentage_identity.xlsx document reveals the pathogens' relatedness numerically, which was highly similar (>96%). 

Module load pyani

`ml pyani` 

Calculate the average nucleotide identity of the genomes in the specified folder (FILE_NAME) and save the output as results_ani

`average_nucleotide_identity.py -o results_ani -i FILE_NAME -g --write_excel`

# Acknowledgments
The `pyani` package used here was "v0.2.12" (https://github.com/widdowquinn/pyani).
