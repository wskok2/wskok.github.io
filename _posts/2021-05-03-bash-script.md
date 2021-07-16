---
layout: post
title: "Handy Bash Script Reference"
---

### Handy Shell script for text manipulation

1. remove the first columns of , delimetered files

awk '{sub(/[^,]*/,"");sub(/,/,"")} 1'

2. Remove the last column of a file

awk -F',' 'BEGIN { OFS = FS }; NF { NF -= 1 }; 1' < $input > $out

OFS = output file delimeter
FS =  file delimeter

3.  Delete BOM char from the file

sed $'1s/\xef\xbb\xbf//' < orig.txt > new.txt

