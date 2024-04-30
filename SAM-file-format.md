$$**SAM file format**$$
The Sequence Alignment/Map (SAM) is a file format to save alignment information of short reads mapped against reference sequences. It usually starts with a header section followed by alignment information as tab separated lines for each read.
Header section
@HD    VN:1.3    SO:coordinate
@SQ    SN:conticA    LN:443
@SQ    SN:contigB    LN:1493
@SQ    SN:contigC    LN:328
Tab-delimited read alignment information lines
readID43GYAX15:7:1:1202:19894/1    256    contig43    613960    1    65M    *    0    0    CCAGCGCGAACGAAATCCGCATGCGTCTGGTCGTTGCACGGAACGGCGGCGGTGTGATGCACGGC    EDDEEDEE=EE?DE??DDDBADEBEFFFDBEFFEBCBC=?BEEEE@=:?::?7?:8-6?7?@??#    AS:i:0    XS:i:0  XN:i:0  XM:i:0  XO:i:0  XG:i:0  NM:i:0  MD:Z:65  YT:Z:UU
readID43GYAX15:7:1:1202:19894/1    272    contig32    21001    1    65M    *    0    0    GCCGGACGTCACACGGCCGCCGGGCCGGTCTACGACCAGACGCATGCGGATTTCGTTAGAGCCGG    #??@?7?6-8:?7?::?:=@EEEEB?=CBCBEFFEBDFFFEBEDABDDD??ED?EE=EEDEEDDE    AS:i:-5    XS:i:0   XN:i:0  XM:i:1   XO:i:0   XG:i:0   NM:i:1   MD:Z:42T22   YT:Z:UU
readID43GYAX15:7:1:1202:19894/1    256    contig87    540849    1    65M    *    0    0    CCTGCACGAACGAAATCCGCATGCGTCTGGTCGTTGTACGGAACGGCGGTTGTGTGACGAACGGC    EDDEEDEE=EE?DE??DDDBADEBEFFFDBEFFEBCBC=?BEEEE@=:?::?7?:8-6?7?@??# AS:i:0  XS:i:0 XN:i:0  XM:i:0 XO:i:0  XG:i:0  NM:i:0    MD:Z:65    YT:Z:UU
Meaning of columns
QNAME    FLAG    RNAME    POS    MAPQ    CIGAR    RNEXT    PNEXT    TLEN    SEQ    QUAL    TAGS
Read Name
SAM flag --> decode
contig name or * for unmapped
mapped position of base 1 of a read on the reference sequence
MAPQ mapping quality
CIGAR string describing insertions and deletions
Name of mate
Position of mate
Template length
Read Sequence
Read Quality
Additional information in TAG:TYPE:VALUE format
Read also
SAM Format Specification (PDF)
→ How to filter reads using the SAM flags? (How to count the number of reads?)
