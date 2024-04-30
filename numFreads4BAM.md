### Number of reads in bam file
__How to count the number of mapped reads in a BAM or SAM file?__
get the total number of reads of a BAM file (may include unmapped and duplicated multi-aligned reads)

```
samtools view -c SAMPLE.bam
```
  76382345

_options_<br>
  ```-c```  count reads and print the total number<br>
  ```-f bitcode```  output reads that fulfill the checked 'bitcode' criteria, see SAM bitcode fields<br>
  ```-F bitcode```  exclude reads that match one or more checked 'bitcode' criteria, see SAM bitcode fields<br>
  ```-F 260```  output primary aligned mapped reads<br>
                       read unmapped & not primary alignment criteria 3 & 9 are selected for exclusion<br>
                       bit 3 + bit 9 = 4 + 256 = 260<br>
http://samtools.sourceforge.net/samtools.shtml

read more
decode SAM bitcode flag number (meaning of flag bits)
http://broadinstitute.github.io/picard/explain-flags.html
