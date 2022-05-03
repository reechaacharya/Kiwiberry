   **Background** 
 
 
 **Kiwiberry**



Kiwiberry (Actinidia arguta) is an emerging berry crop within highly diverse Actinidia genus and has received the attention of horticulturalists and plant breeders due to adaptation to northern latitudes and the smooth edible skin. It is rich in vitamins (A, B8, C, E), carotenoids (lutein, beta-carotene), and minerals (potassium, calcium) (Latocha, 2017). They have also been shown to possess therapeutic value to anticancer (Yu et al., 2015), anti-fatigue, and anit-inflammatory properties.

**Objective**
- To create a vcf file with all the possible SNPs for kiwiberry genome using GBS-SNP-CROP pipeline (perl script)
- To create linkage map from the genotypic data (but using rose data just for the sample)



**Methodology**
- All the computational work is done through premise after an account was setup.(done)


#Data - Data of 10 different kiwiberry accession was collected from Hale lab. The provided data was trimmed and demultiplexed. 

**Building MOCK reference**
1) Firstly, the data input for the script1.sh is a Fastq file and barcode text file.
2) Barcode text file was created using the accession id's
3) Mock reference genome was created using the script1.sh which  clusters the reads using vsearch package

**Map alignment**
1) script2.sh was used for the alignment mapping using BWA-mem and was processed with sam tools.  **##output** - mpileup
2) script3.sh is used in parsing the mpile up file and create variant discovery matrix.     **##output** - variant/genotype matrix
3) script4.sh is used for the variant calling and genotype calling .    **##output** - vcf file
4) script5.sh is used for providing description of all variants in a cluster   **## output** - descriptor.txt file






**Findings**








**References**
Melo et al. GBS-SNP-CROP: A reference-optional pipeline for SNP discovery and plant germplasm characterization using genotyping-by-sequencing data. BMC Bioinformatics. 2016. 17:29. DOI 10.1186/s12859-016-0879-y.
