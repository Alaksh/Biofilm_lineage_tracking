# Biofilm_lineage_tracking
Code for publication High-resolution lineage tracking maps the multi-phase evolution and adaptive potential of biofilms 

#File description and dependencies
Processing of sequencing data:
We processed the raw sequencing data using Usearch (https://www.drive5.com/usearch/, https://doi.org/10.1093/bioinformatics/btq461, Edgar 2010). We used the usearch fastq_mergepairs command to merge the forward and reverse reads. Susequently, we performed alignment to a template reference sequence. Finally, we used the shepherd algorithm (Tavakolian 2022, https://doi.org/10.1093/bioinformatics/btac395) to cluster the barcodes. The clustering algorithm clustered the barcodes and generated files with counts for barcodes in each sample.  

This code combines all the samples with counts for each barcode across conditions.We then used rarefaction analysis to find the minimum number of reads required to represent all samples. We remove all barcodes which have reads = 0 after the normalisation across all samples. We then normalize all samples to this minimum number of reads. We calculate the enrichment for each barcode comapred to the inoculum in each sample. Finally, we saved the data as the file ""Biofilm_filtered.csv". This ""Biofilm_filtered.csv" is the master file used for all analyses.

A. Biofilms binding dynamics.ipynb (Figure 1)
Code to determine the binding dynamics, measure the Shannon indiced, the Bray-Curtis distance from the inoculum and characterize the expansion of variants in different subsections of the biofilms on dics. 

B. Binding simulation.ipynb (Figure 2)
Code implementing the simple bottleneck model and binding growth model for initial biofilm formation. The code also compared simulated data to experimental data.

C. Binding Simulation Temporal dynamics.ipynb (Figure 3)
Code with the temporal simulation introducing the migration parameter

D. Temporal dynamics Shannon and Bray.ipynb (Figure 3)
Code to look and the temporal diversity and distance parameters, to quantify how the biofilm population evolves over time.

E. Temporal dynamics fitness.ipynb (Figure 4)
Code to calculate fitness using two algorithms. For one of the algorithms, you will need to download popDMS. The popDMS implementation code and the output are in the popDMS folder.

F. Mutations and variants.ipynb (Figure 4)
Code to count mutations and determine the targeted genes. The code for the competition data can be found in the folder F. Competition upload. This folder contains the count files and the processing code to determine the competition coefficient of each variant in different contexts deccribed in figure 4.

G. Temporal dynamics with antibiotics.ipynb
Code to determine the temporal diversity and distance parameters for the experiment with antibiotic treatment.

H. Fitness estimates antibiotics.ipynb
Code to determine fitness for experiment with antibiotic treatment.

The ""Biofilm_filtered.csv" and all raw data used to process the files is availaible on Zenodo. The link to the Zenodo repository is: https://doi.org/10.5281/zenodo.22301322. To work with the files, please save the files in a subfolder called the "Figurewise raw data". This will allow access to all files.

