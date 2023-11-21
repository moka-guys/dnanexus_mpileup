# DNAnexus mpileup_v1.0.0
## What does this app do?
This app applies samtools mpileup and creates an mpileup based on the provided BAM and BED.

## What are typical use cases for this app?
The mpileup file lists the bases observed at each position that meet the criteria provided.

## What inputs are required for this app to run?
This app requires the following data:
-   skip - default True. the app will only run if skip is set to false.
-   Compressed reference genome including `*.fa` and `*.fa.fai` (`*.tar.gz`)
-   BAM file(s) (`*.bam`). If multiple BAM files are given a seperate analysis will be performed on each BAM file.
-   BED file of regions of interest, for filtering output vcf (`*.bed`) 

The following samtools mpileup can be specified. if not given the app defaults are applied (stated in square brackets):
-	min-MQ: Minimum mapping quality for an alignment to be used (-q) [20]
-   extra arguments (string)
-	min-BQ: Minimum base quality for a base to be considered (-Q) [15]

## How does this app work?
This app uses samtools v1.13.

- `samtools mpileup` creates an mpileup file.

## What does this app output?
This app will output:
- samtools mpileup file. This lists the base calls made at each position in the BED that meet the given criteria.
For further information on the mpileup format please see the [Documentation](http://www.htslib.org/doc/samtools-mpileup.html)


the mpileup file is output to `/coverage/mpileup`
