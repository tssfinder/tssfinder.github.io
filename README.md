# TSSFinder

TSSFinder is a software for TSS prediction that is faster and with higher accuracy than previously published applications. TSSFinder can also be customized to novel organisms using as few as 500 full transcripts and their corresponding genomic locations.

## Requirements

- C++14
- Python 3.6

## Install

### Ubuntu

- Download the pre-compiled package for Linux [here](https://github.com/tssfinder/tssfinder.github.io/releases/download/v1.0.0/tssfinder-linux.zip)

- Install python's requirements:

```
pip install -r requirements.txtx
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
