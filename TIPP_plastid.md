## simulation data for Selaginella tamariscina

```
perl ~/script/circle.reopen.pl Selaginella_tamariscina.fasta > Selaginella_tamariscina.reopen.fasta
cat Selaginella_tamariscina.fasta Selaginella_tamariscina.reopen.fasta > Selaginella_tamariscina.merged.fasta
./pbsim --strategy wgs --method qshmm --qshmm ../data/QSHMM-RSII.model --difference-ratio 22:45:33 --length-mean 15000 --depth 2000 --genome Selaginella_tamariscina.merged.fasta --pass-num 10
samtools view -@8 -bS sd_0001.sam > sd_0001.bam
samtools view -@8 -bS sd_0002.sam > sd_0002.bam
rm sd_0001.sam sd_0001.maf
rm sd_0002.sam sd_0002.maf
samtools index -@8 sd_0001.bam
samtools index -@8 sd_0002.bam
ccs -j 48 sd_0001.bam sd_0001.bam.fastq
ccs -j 48 sd_0002.bam sd_0002.bam.fastq
cat sd_0001.bam.fastq sd_0002.bam.fastq > sd.bam.fastq
perl /tmp/global2/wxian/te/TIPP/src/TIPP_plastid.pl -d /tmp/global2/wxian/software/TIPP/Plastid_db_4452_genera.fasta.gz -f sd.bam.fastq -t 64
```
