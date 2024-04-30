### SAMtools
_https://www.metagenomics.wiki/tools/samtools/converting-bam-to-fastq#h.cym40tk1lm75<br>_
_http://www.htslib.org/doc/samtools-fasta.html<br>_

__Sort paired read alignment .bam file (sort by name -n)__
```
samtools sort -n SAMPLE.bam -o SAMPLE_sorted.bam
```
__Save fastq reads in separate R1 and R2 files__
```
samtools fastq -@ 8 SAMPLE_sorted.bam \
    -1 SAMPLE_R1.fastq.gz \
    -2 SAMPLE_R2.fastq.gz \
    -0 /dev/null -s /dev/null -n
```
__Using bam2fq__
```
samtools bam2fq SAMPLE.bam > SAMPLE.fastq
```
Paired-end reads:   '/1' or '/2' is added to the end of read names<br>
_http://www.htslib.org/doc/samtools.html_

__How to split a single .fastq file of paired-end reads into two separated files?__
Extracting reads ending with '/1' or '/2'
```
cat SAMPLE.fastq | grep '^@.*/1$' -A 3 --no-group-separator > SAMPLE_r1.fastq
cat SAMPLE.fastq | grep '^@.*/2$' -A 3 --no-group-separator > SAMPLE_r2.fastq
```

### Picard
Converting a SAMPLE.bam file into paired end SAMPLE_r1.fastq and SAMPLE_r2.fastq files
```
java -Xmx2g -jar Picard/SamToFastq.jar I=SAMPLE.bam F=SAMPLE_r1.fastq F2=SAMPLE_r2.fastq
```
F2 to get two files for paired-end reads (R1 and R2)
-Xmx2g   allows a maximum use of 2GB memory for the JVM
_http://broadinstitute.github.io/picard/command-line-overview.html#SamToFastq_

### bam2fastx
_http://manpages.ubuntu.com/manpages/quantal/man1/bam2fastx.1.html_

### Bedtools
```
bedtools bamtofastq -i input.bam -fq output.fastq
```
paired-end reads:
```
samtools sort -n input.bam -o input_sorted.bam   # sort reads by identifier-name (-n)
bedtools bamtofastq -i input_sorted.bam -fq output_r1.fastq -fq2 output_r2.fastq
```
_http://bedtools.readthedocs.org/en/latest/content/tools/bamtofastq.html_

### Bamtools
_http://github.com/pezmaster31/bamtools_

Reference<br>
_https://www.metagenomics.wiki/tools/samtools/converting-bam-to-fastq_
