## SAM file format
The Sequence Alignment/Map (SAM) is a file format to save alignment information of short reads mapped against reference sequences. It usually starts with a header section followed by alignment information as tab-separated lines for each read.<br>

_Header section_<br>
|@HD|VN:1.3|O:coordinate|
|:----|:----|:----|
|@SQ|SN:conticA|LN:443|
|@SQ|SN:contigB|LN:1493|
|@SQ|SN:contigC|LN:328|

_Tab-delimited read alignment information lines_
|QNAME|FLAG|RNAME|POS|MAPQ|CIGAR|RNEXT|PNEXT|TLEN|SEQ|QUAL|TAGS|
|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|
|readID43GYAX15:7:1:1202:19894/1|256|contig43|613960|1|65M|*|0|0|CCAGCGCGAACGAAATCCGCATGCGTCTGGTCGTTGCACGGAACGGCGGCGGTGTGATGCACGGC|EDDEEDEE=EE?DE??DDDBADEBEFFFDBEFFEBCBC=?BEEEE@=:?::?7?:8-6?7?@??#|AS:i:0|XS:i:0  XN:i:0  XM:i:0  XO:i:0  XG:i:0  NM:i:0  MD:Z:65  YT:Z:UU|
|readID43GYAX15:7:1:1202:19894/1|272|contig32|21001|1|65M|*|0|0|GCCGGACGTCACACGGCCGCCGGGCCGGTCTACGACCAGACGCATGCGGATTTCGTTAGAGCCGG|#??@?7?6-8:?7?::?:=@EEEEB?=CBCBEFFEBDFFFEBEDABDDD??ED?EE=EEDEEDDE|AS:i:-5|XS:i:0   XN:i:0  XM:i:1   XO:i:0   XG:i:0   NM:i:1   MD:Z:42T22   YT:Z:UU|
|readID43GYAX15:7:1:1202:19894/1|256|contig87|540849|1|65M|*|0|0|CCTGCACGAACGAAATCCGCATGCGTCTGGTCGTTGTACGGAACGGCGGTTGTGTGACGAACGGC|EDDEEDEE=EE?DE??DDDBADEBEFFFDBEFFEBCBC=?BEEEE@=:?::?7?:8-6?7?@??# AS:i:0  XS:i:0 XN:i:0  XM:i:0 XO:i:0  XG:i:0  NM:i:0|MD:Z:65|YT:Z:UU|

__Meaning of columns__<br>
|1|2|3|4|5|6|7|8|9|10|11|12|
|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|:----|
|QNAME|FLAG|RNAME|POS|MAPQ|CIGAR|RNEXT|PNEXT|TLEN|SEQ|QUAL|TAGS|

$1. Read Name$<br>
$2. SAM flag --> decode$<br>
$3. contig name or * for unmapped$<br>
$4. mapped position of base 1 of a read on the reference sequence$<br>
$5. MAPQ mapping quality$<br>
$6. CIGAR string describing insertions and deletions$<br>
$7. Name of mate$<br>
$8. Position of mate$<br>
$9. Template length$<br>
$10. Read Sequence$<br>
$11. Read Quality$<br>
$12. Additional information in TAG:TYPE:VALUE format$<br>

__Reference__<br>
[SAM file format](https://www.metagenomics.wiki/tools/samtools/bam-sam-file-format)<br>

__Read also__ <br>
[SAM Format Specification (PDF)](http://samtools.github.io/hts-specs/SAMv1.pdf) <br>

→ [How to filter reads using the SAM flags? (How to count the number of reads?)](https://www.metagenomics.wiki/tools/samtools/number-of-reads-in-bam-file) <br>
