# zymo-data release 2019-02
Oxford Nanopore Technologies Zymo Mock Community data on R9.4.1

We are happy to announce the release of Zymo mock community dataset for R9.4.1. This dataset has recently been used internally as a method of measuring platform and algorithm improvements.
Data Generation Conditions: 
This data was generated on five MinION Flow Cells (FLO-MIN106). 
The first 20 hours from each flow cell has been used, totalling 59.6 Gb of data (median 12 Gb per flow cell).

Version Management: 
Device: GridION 
Flow Cell: FLO-MIN106 (R9.4.1, RevC) 
MinKNOW Version: 18.12.4 Basecalling: 
Flip-Flop Model in Guppy 2.3.5


## Files ##
| Type | URL |
|----------------|--------------------------------------------------------------------|
| Sizes          | https://s3.amazonaws.com/ont-zymo/2019-02+R9.4.1/fastq.listing.txt |
| MD5 checksums  | https://s3.amazonaws.com/ont-zymo/2019-02+R9.4.1/fastq.md5sums.txt |

## Download script ##
```
#!/bin/bash
curl -o fastq.listing.txt https://s3.amazonaws.com/ont-zymo/2019-02+R9.4.1/fastq.listing.txt
for i in $(awk '{print $NF}' < fastq.listing.txt); do
  dir=$(dirname $i);
  fn=$(basename $i);
  mkdir -p $dir;
  echo $dir/$fn;
  curl -o $dir/$fn https://s3.amazonaws.com/ont-zymo/2019-02+R9.4.1/$i;
done
```
