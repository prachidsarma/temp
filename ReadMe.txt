
Steps used in the assignment
1. Wrote a python script NGS_readsimulator.py that generates given no of single end reads (100000) of given readlength(50bp) randomly from the human genome. The reads are then mutated with error rate of 0.01 and saved in FASTQ file using dummy quality values.
	The input fasta file of genome reference GRCh37 was downloaded from NCBI https://www.ncbi.nlm.nih.gov/genome/guide/human/
	The output file generated is Readdata.fasta

2. The resultant output file Readdata.fasta was used as input to run bwa and samtools. The bwa and samtools were run using following commands at commandline. 

	bwa index reference_genome.fasta
	bwa aln reference_genome.fasta Readdata.fasta >ALN_SA.sai
	bwa samse reference_genome.fasta ALN_SA.sai Readdata.fasta > ALN_SE.sam
	
	samtools view -S ALN_SE.sam > ALN_SE.bam
	
3.The error rate was calculated

An error rate of 0.01 was added to mutate the DNA
