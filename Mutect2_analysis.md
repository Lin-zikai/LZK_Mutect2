``` bash 
gatk Mutect2 \
-R ~/hmk/sandbox/ref/Homo_sapiens_assembly38.fasta \
-I ~/hmk/sandbox/bams/normal.bam \
-L ~/hmk/sandbox/resources/chr17plus.interval_list \
--germline-resource ~/hmk/sandbox/resources/chr17_af-only-gnomad_grch38.vcf.gz \
-O ~/hmk/sandbox/unfiltered_normal.vcf.gz
```
-R：参考基因组（Homo_sapiens_assembly38.fasta）。  这部分可以直接用/mnt/project/下的Homo_sapiens_assembly38.fasta

-I：输入 BAM 文件。  这部分考虑使用/Bulk/Exome sequences/Exome OQFE CRAM files/下的cran文件

--germline-resource：用来过滤常见的种系变异资源库（gnomAD）。

考虑采用gnomAD的数据，需要下载每个Exomes的数据文件，考虑能不能直接gs下载（记得下载TBI）

gs://gcp-public-data--gnomad/release/4.1/ht/exomes/gnomad.exomes.v4.1.sites.ht

https://gnomad.broadinstitute.org/downloads#v4-variants

-L：限制检测的基因区域。 暂时没搞懂这个是什么格式
-O：输出未经过滤的 VCF 文件。 每个人都有一个也？
