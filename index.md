# Funtional Genomic Tools and Fundamentals
[Zhanglab @ Columbia](https://hanruizhang.github.io/zhanglab/) by **Jianting Shi** [2019-09-07]

## Genome Resources

### 1. Sequence, Gene & Protein Resources

- Public Resources

	1) [NCBI Main Site](http://www.ncbi.nlm.nih.gov)   
	2) [PubMed](http://www.ncbi.nlm.nih.gov/pubmed)   
	3) [NCBI RefSeq](http://www.ncbi.nlm.nih.gov/refseq/)   
	4) [NCBI Entrez](http://www.ncbi.nlm.nih.gov/)   
	5) [UniGene](http://www.ncbi.nlm.nih.gov/sites/entrez?db=unigene)   
	6) [NCBI GEO - Gene Expression Omnibus](http://www.ncbi.nlm.nih.gov/geo/)  
	7) [BioGPS - gene annotation portal](http://biogps.org/)  
	8) [UniProt](http://www.uniprot.org)  
	9) [PDB - Protein Data Bank](http://www.rcsb.org/pdb/home/home.do)  
	10) [ExPasy - Bioinformatics Resources Portal](http://www.expasy.org/)  
	11) [OMIM](http://omim.org)
- Examples  
	1) [Search for 'BAX' in all NCBI Databases](https://www.ncbi.nlm.nih.gov/search/all/?term=bax)  
	2) [Search for 'BAX' in NCBI nucleotides database](https://www.ncbi.nlm.nih.gov/nuccore/?term=bax)  
	3) ['BAX' information in OMIM](https://omim.org/entry/600040)  

	
### 2. UCSC genome browser
- Beginner's basics from the start

1) The main site https://genome.ucsc.edu/  
2) [Tutorial from UCSC](https://genome.ucsc.edu/training/)  
3) [Genome Browser User Guide](https://genome.ucsc.edu/goldenPath/help/hgTracksHelp.html)  
4) [Nature Scitable Guide to the UCSC Genome Browser](www.nature.com/scitable/ebooks/guide-to-the-ucsc-genome-browser-16569863)

- UCSC browser skills  
		a. Perform text searches (gene)  
		b. Perform blat searches (sequence, Fasta file)  
		c. Understand and customize tracks and displays (Annotation Tracks, Configuration of Track Displays, Get DNA sequences, Export Images)  
		d. Access links to additional resources  
		e. Create and share user sessions  
		f. Browse and download data (bulk retrieval through table browser)  
		g. Upload your own data tracks  
	
### 3. Ensembl Genome browser
[Ensembl](https://useast.ensembl.org/index.html) genome browser main site is organized by organism genome,  featuring eukaryotic genomes. [Pre!Ensembl](http://pre.ensembl.org/index.html) features in-process genomes, while other genomes of other organisms, such as fungi, bacteria, etc. can be found on [EnsemblGenomes](http://ensemblgenomes.org/).   

- Ensembl identifiers

	** human:  
	ENSG########### GENE   
	ENST########### TRANSCRIPT  
	ENSP########### PROTEIN  
	ENSE########### EXON  
	ENSR########### REGULATORY FEATURE ID  
	** mouse  
	ENSMUSG########### mouse gene (Mus musculus)  
	
- Data download using BioMart 

	Worked Example:  
   a. Identify all genes in a region known to be linked to a disease/phenotype, Chr1: 50M - 60M  
   b. Database - dataset - Filter - count genes - attributes (Ensembl ID, Chromosome Name, EntrezGene ID, HGNC symbol) - Dataset (compare mouse & human gene variation)

### 4. Model organism
- Major mode organism database:  
		a. Mouse genome informatics: MGI  
		b. Zebrafish information network (ZFIN)  
- Gene Ontology  
  1. Uses terms to describe gene products: biological process, molecular function, cellular component.
  2. Given terms may have multiple parent nodes
  3. GO evidence codes: Experimental Evidence; Automatically assigned evidence; curatorial statement codes; computational evidence
  4. AMIGO(http://geneontology.org/):
  5. GO terms and annotations search
  6. Relationships among GO terms 
	      
	      
## DNA Sequence Analysis


### 1. [Galaxy](https://usegalaxy.org/) (SNP calling)
- General workflow:  
	Sequencing data - mapping genome - alignment data (BAM-SAM) - [viewable in UCSC genome browser] - initial results - explore results - more analysis
- Galaxy:  
	Key steps:  
	Upload files - choose data type and genome - bowtie2 for alignment - (mapping statistics are generated from the BAM file, assess to check the quality of our alignment) - viewable in UCSC genome browser.   
	FreeBayes (bayesian genetic variant detector) - vcf (variant calling format)
	Summary statistics - Filter and sort - viewable in IGV
- Detailed reference:
	https://www.melbournebioinformatics.org.au/tutorials/tutorials/variant_calling_galaxy_1/variant_calling_galaxy_1/
	
### 2. Sequence polymorphisms
	
- [HapMap project](https://www.genome.gov/10001688/international-hapmap-project)  
	* A haplotype is a group of genes within an organism that was inherited together from a single parent. The word "haplotype" is derived from the word "haploid," which describes cells with only one set of chromosomes, and from the word "genotype," which refers to the genetic makeup of an organism.
	* SNP identification; 'tag' SNPs identification; screen 'tag' SNP in multiple populations
	* Data reduction by haplotype recognition 
	* Genotype imputation by haplotype recognition

- 1000 genome (whole genome sequencing)  
	* Low-coverage whole-genome and exome sequencing  
	* SNP, short insertion and deletion, larger deletion
	
- GWAS  
	* 99% of the human genome does not code for protein  
	* Genetic variants lie in non-coding regions  
	* Limits
	
- Data Access tools  
	* Entrez (variation):   
		a. dbSNP: short genetic variation  
		b. dbVar: structural variation  
		c. dbGAP: genotypes and phenotypes  
	* Anciliary databases
	  a. DGB(database of genomic variants)
	
- Large-scale annotation of sequence variation
   * General Workflow:
	Alignment - Variant predication - Variant annotation - Filtering and Prioritizing variants
	a. Alignment: BWA -- Samtools/GATK
	• Variant prediction: Mpileup/Unified genotyper(haplotype caller)
	• (high throughput) Variant annotation: Seattleseq, SNP effect, Variant Annotator, Variant Effect Predictor (Ensembl)
	• Filtering and prioritizing variants: 
		1- Presence\Absence in affected\unaffected
		2- Consequence to Protein - strongest impact
		3- Conservation (PHAST, GERP) - most highly conserved
		4- Allele frequency in ESV - low minor allele frequency (NHLBI Exome Sequencing Project)
		
- Worked Example:
	Ensembl - Information about Variants of Gene - 
	• Variation table
	• View SNP in dbSNP ** validation status
	• Structural variation ** impact on genes and regulation
	
		
### 3. Functional genomics elements and ENCODE
- Goal of encyclopedia of DNA elements: to identify all functional elements in the human genome sequence
- Download raw data and alignment data
- How to use ENCODE data
	• View and search for tracks in the UCSC browser
	• Understand and customize tracks and displays
	• Access links to additional resources
	• Browse and download data
- Worked Example:
	• ATAC-Seq Data (download from GEO)
	• Upload custom tracks
Turn on ENCODE tracks/super tracks/track hub

## RNA Sequence Analysis

Outline: Experimental Design - QC - Read alignment - Quantify isoform and gene expression

- Experimental Design  
	* Ask a few questions:  
	1. How many reads? Sequencing depth [or library size refers to the number of sequenced reads for a given sample]  
	2. Single-End or Paired-end sequencing?
	3. What is the Read length? [>100bp]
	4. How many samples? [> 2 replicates]  
	* Adjust to different goals
	Differential expression of highly expressed and well annotated genes?  
	A. Smaller sample depth; more biological replicates  
	B. No need for paired end reads; shorter reads (50bp) may be sufficient;  
	C. Better to have 20 million 50bp reads than 10 million 100bp reads  
	Looking for novel genes/splicing/isoforms?  
	D. More read depth, paired-end reads from longer fragments.  
	* Multiplexing, Replication, Randomization
- Quality Control  
	FASTX-Toolkit  
	FastQC
- Alignment
	Multi-mapping reads
	Alignment to genome or transcriptome: genome(can align novel isoforms)
	Visualization of alignment data (BAM/SAM) : IGV and UCSC
	Aligned reads to gene abundance:
- Galaxy (fastqsanger - bowtie - SAMtoBAM convertor - cufflinks - cuffdiff
- R environment
- Gene Set Enrichment Analysis and Pathway Analysis

**Materials here are licensed as [CC BY-NC-SA 4.0 Creative Commons License](https://creativecommons.org/licenses/by-nc-sa/4.0/).**
