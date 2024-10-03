# Week3

# Question 1

```bash
find /home/alboeis/ncbi_dataset/data -type f -
name "*.fna" -exec sh -c 'echo "$(tail -n +2 "$1" | wc -c) $(basename "$1
")"' _ {} \; | sort -n | tail -n 1 | awk '{print "The largest genome is i
n \"" $2 "\": " $1}'
```
> OUTPUT: The largest genome is in "GCF_000006745.1_ASM674v1_genomic.fna": 4083974

# Question 2


``` bash
find /home/alboeis/ncbi_dataset/data -type f -name "*.fna" -exec sh -c 'echo "$(tail -n +2 "$1" | wc -c) $(basename "$1")"' _ {} \; | sort -n | head -n 1 | awk '{print "The smallest genome is in \"" $2 "\": " $1}'
```
> OUTPUT: The smallest genome is in "GCA_000008725.1_ASM872v1_genomic.fna": 1055551


# Question 3

``` bash
grep -E 'GCA' /home/alboeis/ncbi_dataset/data/data_summary.tsv | grep -E 'c.*c' | wc -l
```
> OUTPUT: 7

# Question 4

``` bash
grep -E 'GCA' /home/alboeis/ncbi_dataset/data/data_summary.tsv | grep -E 'c.*c' | grep -v 'coccus' | wc -l
```
> OUTPUT: 5

# Question 5

``` bash
find /home/alboeis/ncbi_dataset/data -type f -name "*GCA*.fna" -size +3M | wc -l

```
> OUTPUT: 3
