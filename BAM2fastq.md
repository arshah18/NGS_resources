### SAMtools
https://www.metagenomics.wiki/tools/samtools/converting-bam-to-fastq#h.cym40tk1lm75<br>
http://www.htslib.org/doc/samtools-fasta.html<br>
### sort paired read alignment .bam file (sort by name -n)
```
samtools sort -n SAMPLE.bam -o SAMPLE_sorted.bam
```
### save fastq reads in separate R1 and R2 files
```
samtools fastq -@ 8 SAMPLE_sorted.bam \
    -1 SAMPLE_R1.fastq.gz \
    -2 SAMPLE_R2.fastq.gz \
    -0 /dev/null -s /dev/null -n
```
### Using bam2fq
```samtools bam2fq SAMPLE.bam > SAMPLE.fastq```
### paired-end reads:   '/1' or '/2' is added to the end of read names
### http://www.htslib.org/doc/samtools.html

### How to split a single .fastq file of paired-end reads into two separated files?
### extracting reads ending with '/1' or '/2'
cat SAMPLE.fastq | grep '^@.*/1$' -A 3 --no-group-separator > SAMPLE_r1.fastq
cat SAMPLE.fastq | grep '^@.*/2$' -A 3 --no-group-separator > SAMPLE_r2.fastq

### Picard
### converting a SAMPLE.bam file into paired end SAMPLE_r1.fastq and SAMPLE_r2.fastq files
java -Xmx2g -jar Picard/SamToFastq.jar I=SAMPLE.bam F=SAMPLE_r1.fastq F2=SAMPLE_r2.fastq
 F2   to get two files for paired-end reads (R1 and R2)
### -Xmx2g   allows a maximum use of 2GB memory for the JVM
### http://broadinstitute.github.io/picard/command-line-overview.html#SamToFastq

### bam2fastx
### http://manpages.ubuntu.com/manpages/quantal/man1/bam2fastx.1.html

### Bedtools
bedtools bamtofastq -i input.bam -fq output.fastq
paired-end reads:
samtools sort -n input.bam -o input_sorted.bam   # sort reads by identifier-name (-n)
bedtools bamtofastq -i input_sorted.bam -fq output_r1.fastq -fq2 output_r2.fastq
### http://bedtools.readthedocs.org/en/latest/content/tools/bamtofastq.html

### Bamtools
### http://github.com/pezmaster31/bamtools
