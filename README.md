# zymo-data
Oxford Nanopore Technologies Zymo Mock Community data



## Files ##
File listing including sizes: https://s3.amazonaws.com/ont-zymo/2019-02+R9.4.1/fastq.listing.txt
File listing including checksums: https://s3.amazonaws.com/ont-zymo/2019-02+R9.4.1/fastq.md5sums.txt

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
