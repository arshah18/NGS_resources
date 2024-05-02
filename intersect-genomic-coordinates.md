### R function for intersection of genomic coordinates from one file and check if the coordinates are within a specific range
```
library(GenomicRanges)
library(rtracklayer)

f1 <- import("file1.bed")
f2 <- import("file2.bed")

# subset f1 features that overlap with f2
result <- f1[countOverlaps(f1, f2, maxgap=150) > 0]

# save as bed
export(result, "f1_f2_overlap.bed")

# or as a dataframe
df <- as.data.frame(result)
write.table(df, file="f1_f2_overlap.txt", sep="\", col.names=NA)
```
