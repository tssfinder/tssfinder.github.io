# TSSFinder

TSSFinder is a software for TSS prediction that is faster and with higher accuracy than previously published applications. TSSFinder can also be customized to novel organisms using as few as 125 full transcripts and their corresponding genomic locations.

# TSSFinder web service

For the web service version, TSSFinder can be accessed [here](http://sucest-fun.org/wsapp/tssfinder/)


## Requirements

- C++14
- Python 3.6

## Install

### Ubuntu

- Download the pre-compiled package for Linux [here](https://github.com/tssfinder/tssfinder.github.io/releases/download/v1.0.0/tssfinder-linux.zip)

- Install python's requirements:

```
pip install -r requirements.txt
```

- Add `tssfinder` and `tssfinder/bin/cli` folders to the `PATH`

### Docker

Install docker and add `tssfinder/docker-bin` folder to the `PATH`

## Training

```
tssfinder-train --model <OUTPUT-DIR> \
                --start <START-CODON-BED> \
                --tata <TATA-BOX-BED> \
                --tss <TSS-BED> \
                --genome <GENOME-FASTA> 
```

## Prediction

```
tssfinder --model <MODEL-DIR> \
          --start <START-CODON-BED> \
          --genome <GENOME-FASTA> \
          --output <OUTPUT-DIR>
```
## File Examples

The input for TSSFinder must be in two formats: FASTA and BED (tab).

For example the FASTA format which may look like:
```
>genome_fasta
CTGATTTTCGTTGGCCCTAGATTTCATCAATCTCTAATTTCATTTTGTATTTTTATCGTTTTGA
AATTTAAATGTCAAGTCCCAACGGTCCTCTGATCTCGGCAGTTTTTGTGTTATGTAAATGACTA
```
The FASTA format must be a multi-fasta file, generally the organism's genome. For more information for [FASTA file](https://en.wikipedia.org/wiki/FASTA_format).

For example the BED (tab) format which may look like:
```
xxx.bed 
Chr	Coord_a	Coord_b	Name_locus	1º_tss	strand
1	1597842	1597843	EXEM1G05440_1	1	-
1	1766149	1766150	EXEM1G05840_1	1	-
1	1775654	1775655	EXEM1G05880_1	1	+
1	1823346	1823347	EXEM1G06010_1	1	+
1	1855962	1855963	EXEM1G06120_1	1	+

```
The BED (tab) format is used for files for start, tss and tata-box. For more information for [BED file](https://m.ensembl.org/info/website/upload/bed.html).
