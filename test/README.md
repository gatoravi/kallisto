# test data set

Here you will find a small test data set to ensure that kallisto is working properly. The contents are:

- `transcripts.fasta.gz`: a gzip compressed transcriptome
- `reads_X.fastq.gz`: gzip compressed "left" and "right" reads
- `Snakefile`: a sample [`snakemake`](https://bitbucket.org/johanneskoester/snakemake/wiki/Home) file (not required for running kallisto)

#To generate the BAM files from the FASTQ
java -jar ../../picard-tools-1.140/picard.jar FastqToSam F1=reads_1.fastq.gz F2=reads_2.fastq.gz O=reads.bam SAMPLE_NAME=test
samtools index reads.bam
samtools sort -n reads.bam reads.sorted
samtools index reads.sorted.bam
