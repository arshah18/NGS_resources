### Number of reads in bam file
__How to count the number of mapped reads in a BAM or SAM file?__
get the total number of reads of a BAM file (may include unmapped and duplicated multi-aligned reads)

```
samtools view -c SAMPLE.bam
```
  76382345

_options_<br>
  &nbsp```-c```  count reads and print the total number;<br>
  ```-f bitcode```  output reads that fulfill the checked _'bitcode'_ criteria, see SAM bitcode fields<br>
  ```-F bitcode```  exclude reads that match one or more checked _'bitcode'_ criteria, see SAM bitcode fields<br>
  ```-F 260```  output primary aligned mapped reads<br>
                       _read unmapped & not primary alignment criteria_ 3 & 9 are selected for exclusion<br>
                       bit 3 + bit 9 = 4 + 256 = 260<br>
http://samtools.sourceforge.net/samtools.shtml<br>

__read more__
decode SAM bitcode flag number (meaning of flag bits)<br>
http://broadinstitute.github.io/picard/explain-flags.html<br>
