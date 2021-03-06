   # Background
 ![DSC_0503-01_032b](https://user-images.githubusercontent.com/103780040/168170795-8615189a-3614-492e-82ea-93236a2da4dd.JPG)


 # Kiwiberry



Kiwiberry (Actinidia arguta) is an emerging berry crop within highly diverse Actinidia genus and has received the attention of horticulturalists and plant breeders due to adaptation to northern latitudes and the smooth edible skin. It is rich in vitamins (A, B8, C, E), carotenoids (lutein, beta-carotene), and minerals (potassium, calcium) (Latocha, 2017). They have also been shown to possess therapeutic value to anticancer (Yu et al., 2015), anti-fatigue, and anit-inflammatory properties.

# Objective
- To create a vcf file with all the possible SNPs for kiwiberry genome using GBS-SNP-CROP pipeline (perl script)
- To look into the differences in cluster frequencies when using 1 read vs 10 reads to develop the mock reference genome



# Methodology
- All the computational work is done through premise after an account was setup.(done)


#Data - Data of 10 different kiwiberry accession was collected from Hale lab. The provided data was trimmed and demultiplexed. 

## Building MOCK reference
1) Firstly, the data input for the script1.sh is a Fastq file and barcode text file.
2) Barcode text file was created using the accession id's
3) Mock reference genome was created using the script1.sh which  clusters the reads using vsearch package

## Map alignment
1) script2.sh was used for the alignment mapping using BWA-mem and was processed with sam tools.  
2) script3.sh is used in parsing the mpile up file and create variant discovery matrix.    
3) script4.sh is used for the variant calling and genotype calling .    
  

## Descriptor file
1) script5.sh is used for providing description of all variants in a cluster   

The descriptor file was used to make histograms for cluster length frequencies.

#### more details on the work flow and script for histogram in R is in whole_script path.txt


# Findings 


### script1.sh output - mock reference genome


### script2.sh output - mpileup files


### script3.sh output - variant/genotype matrix


### script4.sh output - vcf file


### script5.sh output - descriptor.txt file

### Differences in the cluster length frequency when using 1 read vs 10 reads for the reference genome
Cluster length frequency in the VCF file  represents the number of SNPs identified using the built mock reference genome. The cluster length frequency varied from 50 -160 in both the situation. The cluster frequency was highest for the cluster with length 160 bp in both the cases. The number of SNPs identified using the developed cluster (160bp) in mock reference genome with 1 read (>6000) was double incomparison to the cluster (160 bp) in mock reference with 10 reads (approx 3000). 

In plots/Wholecluster.png you can see that the number of SNPs in cluster length <160 bp is <1000 whereas the number of SNPs in cluster length <160bp in plots/cluster.png is around 1000-1500

Histogram Plots

https://github.com/reechaacharya/Kiwiberry/blob/63c3ae9a2c3f08e0cba73aa725876ed62353e525/plots/Wholecluster.png
https://github.com/reechaacharya/Kiwiberry/blob/b98fd83a9e13746b54fe41e362b899a9cff78445/plots/cluster.png


# Poster
 The poster on the project is in Poster_Genomics.pptx file
 https://github.com/reechaacharya/Kiwiberry/blob/6834507a54ce116fad8d0cf13104ba36bed85480/Poster_Genomics.pptx
 

# References 
Melo et al. GBS-SNP-CROP: A reference-optional pipeline for SNP discovery and plant germplasm characterization using genotyping-by-sequencing data. BMC Bioinformatics. 2016. 17:29. DOI 10.1186/s12859-016-0879-y.

Latocha, P. (2017). The Nutritional and Health Benefits of Kiwiberry (Actinidia arguta) ??? a Review. Plant Foods for Human Nutrition, 72(4), 325???334. https://doi.org/10.1007/s11130-017-0637-y


Yu, X., Liu, C., Liu, Y., Tan, C., & Liu, Y. (2015). Actinidia arguta polysaccharide induces apoptosis in Hep G2 cells. Advance Journal of Food Science and Technology, 7(11), 857???863. https://doi.org/10.19026/ajfst.7.2522
