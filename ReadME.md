# Data preparation
Arabidopsis thaliana Col-0_XJTU
```
wget https://download.cncb.ac.cn/gsa/CRA004538/CRR302670/CRR302670_f1.fastq.gz
wget https://download.cncb.ac.cn/gsa/CRA004538/CRR302670/CRR302670_r2.fastq.gz
/tmp/global2/wxian/software/fxTools/target/release/fxTools -s 7g CRR302668.fastq.gz | /tmp/global2/wxian/software/pigz-master/pigz > Col-0_XJTX.ccs.50X.fastq.gz
../../software/hifiasm-0.19.6/hifiasm -t 64 -o Col-0_XJTX Col-0_XJTX.ccs.50X.fastq.gz 1>hifisam.out 2>hifisam.err
grep "^S" Col-0_XJTX.bp.p_ctg.gfa |awk '{print ">"$2"\n"$3}' > Col-0_XJTX.bp.p_ctg.gfa.fa
minimap2 -ax map-hifi -t 64 Col-0_XJTX.bp.p_ctg.gfa.fa Col-0_XJTX.ccs.50X.fastq.gz | samtools sort -@12 -o Col-0_XJTX.bp.p_ctg.gfa.fa.Col-0_XJTX.ccs.50X.fastq.gz.sorted.bam -
minimap2 -x map-hifi -t 64 Col-0_XJTX.bp.p_ctg.gfa.fa Col-0_XJTX.ccs.50X.fastq.gz -o Col-0_XJTX.bp.p_ctg.gfa.fa.Col-0_XJTX.ccs.50X.fastq.gz.paf

#Inspector
ref=Col-0_XJTX.bp.p_ctg.gfa.fa
reads=Col-0_XJTX.ccs.50X.fastq.gz
source /tmp/global2/wxian/software/anaconda3/bin/activate
conda activate inspector
inspector.py -t 64 -c $ref -r $reads -o inspector_$ref\_1 --datatype hifi
inspector-correct.py -t 64 -i inspector_$ref\_1 --datatype pacbio-hifi -o inspector_$ref\_1

#Nextpolish1
python /ebio/abt6_projects7/small_projects/wxian/software/NextPolish/lib/nextpolish2.py -g Col-0_XJTX.bp.p_ctg.gfa.fa -l bam.txt -r hifi -p 48 -sp -o Col-0_XJTX.bp.p_ctg.gfa.nextpolish1.minimap2.fa
bam.txt:/tmp/global2/wxian/28.Auto_Assembly/Col-0_XJTU/Col-0_XJTX.bp.p_ctg.gfa.fa.Col-0_XJTX.ccs.50X.fastq.gz.sorted.bam

#Pilon
java -jar /tmp/global2/wxian/software/pilon-1.24.jar --genome ../Col-0_XJTX.bp.p_ctg.gfa.fa --pacbio ../Col-0_XJTX.bp.p_ctg.gfa.fa.Col-0_XJTX.ccs.50X.fastq.gz.sorted.bam --output Col-0_XJTX.bp.p_ctg.gfa.fa.pilon.minimap2.fa --fix snps,indels

#Racon
racon -t 40 ../Col-0_XJTX.ccs.50X.fastq.gz ../Col-0_XJTX.bp.p_ctg.gfa.fa.Col-0_XJTX.ccs.50X.fastq.gz.paf ../Col-0_XJTX.bp.p_ctg.gfa.fa 1>Col-0_XJTX.bp.p_ctg.gfa.fa.racon.fa 2> racon.err
```
Arabidopsis thaliana Ey15-2
```
wget ftp://ftp.sra.ebi.ac.uk/vol1/run/ERR866/ERR8666125/9994.q20.CCS.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/run/ERR866/ERR8666067/CLR_vs_HiFi_S2_L001_R1_001.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/run/ERR866/ERR8666067/CLR_vs_HiFi_S2_L001_R2_001.fastq.gz
/tmp/global2/wxian/software/fxTools/target/release/fxTools -s 7g 9994.q20.CCS.fastq.gz | /tmp/global2/wxian/software/pigz-master/pigz > Ey15-2.ccs.50X.fastq.gz
../../software/hifiasm-0.19.6/hifiasm -t 64 -o Ey15-2 Ey15-2.ccs.50X.fastq.gz 1>hifisam.out 2>hifisam.err
grep "^S" Ey15-2.bp.p_ctg.gfa |awk '{print ">"$2"\n"$3}' > Ey15-2.bp.p_ctg.gfa.fa
minimap2 -ax map-hifi -t 64 Ey15-2.bp.p_ctg.gfa.fa Ey15-2.ccs.50X.fastq.gz | samtools sort -@12 -o Ey15-2.bp.p_ctg.gfa.fa.Ey15-2.ccs.50X.fastq.gz.sorted.bam -
minimap2 -x map-hifi -t 64 Ey15-2.bp.p_ctg.gfa.fa Ey15-2.ccs.50X.fastq.gz -o Ey15-2.bp.p_ctg.gfa.fa.Ey15-2.ccs.50X.fastq.gz.paf
```
Maize Mo17
```
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/014/SRR15447414/SRR15447414_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/015/SRR15447415/SRR15447415_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/016/SRR15447416/SRR15447416_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/018/SRR15447418/SRR15447418_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/019/SRR15447419/SRR15447419_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/020/SRR15447420/SRR15447420_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/021/SRR15447421/SRR15447421_subreads.fastq.gz
cat SRR154474*gz > Mo17.ccs.fastq.gz
/tmp/global2/wxian/software/fxTools/target/release/fxTools -s 110g Mo17.ccs.fastq.gz | /tmp/global2/wxian/software/pigz-master/pigz > Mo17.ccs.50X.fastq.gz
rm Mo17.ccs.fastq.gz
../../software/hifiasm-0.19.6/hifiasm -t 64 -o Mo17 Mo17.ccs.50X.fastq.gz 1>hifisam.out 2>hifisam.err
grep "^S" Mo17.bp.p_ctg.gfa |awk '{print ">"$2"\n"$3}' > Mo17.bp.p_ctg.gfa.fa
minimap2 -ax map-hifi -t 64 Mo17.bp.p_ctg.gfa.fa Mo17.ccs.50X.fastq.gz | samtools sort -@12 -o Mo17.bp.p_ctg.gfa.fa.Mo17.ccs.50X.fastq.gz.sorted.bam -
minimap2 -x map-hifi -t 64 Mo17.bp.p_ctg.gfa.fa Mo17.ccs.50X.fastq.gz -o Mo17.bp.p_ctg.gfa.fa.Mo17.ccs.50X.fastq.gz.paf
```
Human CHM13
```
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR112/020/SRR11292120/SRR11292120_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR112/021/SRR11292121/SRR11292121_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR112/022/SRR11292122/SRR11292122_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR112/023/SRR11292123/SRR11292123_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR908/007/SRR9087597/SRR9087597_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR908/008/SRR9087598/SRR9087598_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR908/009/SRR9087599/SRR9087599_subreads.fastq.gz
wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR908/000/SRR9087600/SRR9087600_subreads.fastq.gz
cat *gz > CHM13.ccs.fastq.gz
../../software/hifiasm-0.19.6/hifiasm -t 88 -o CHM13 CHM13.ccs.fastq.gz 1>hifisam.out 2>hifisam.err
grep "^S" CHM13.bp.p_ctg.gfa |awk '{print ">"$2"\n"$3}' > CHM13.bp.p_ctg.gfa.fa
minimap2 -t 64 -ax map-hifi CHM13.bp.p_ctg.gfa.fa CHM13.ccs.fastq.gz | samtools sort -@12 -o CHM13.bp.p_ctg.gfa.fa.CHM13.ccs.fastq.gz.sorted.bam -
minimap2 -t 64 -x map-hifi CHM13.bp.p_ctg.gfa.fa CHM13.ccs.fastq.gz -o CHM13.bp.p_ctg.gfa.fa.CHM13.ccs.fastq.gz.paf
```
