## Step1. download the HiFi data of 54 speices
```
Acorus_gramineus: wget https://ftp.cngb.org/pub/CNSA/data5/CNP0002281/CNS0462037/CNX0584248/CNR0677470/m64268e_221222_020614.hifi.reads.fq.gz
Actinidia_chinensis: kingfisher get -r SRR21031553 -m ena-ascp aws-http prefetch
Amborella_trichopoda: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR288/027/SRR28888927/SRR28888927_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR288/028/SRR28888928/SRR28888928_subreads.fastq.gz
Adenosma_buchneroides: wget https://download.cncb.ac.cn/gsa2/CRA011236/CRR793707/CRR793707.bam
Arabidopsis_thaliana: wget https://download.cncb.ac.cn/gsa/CRA004538/CRR302668/CRR302668.fastq.gz
Arabidopsis_lyrata: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR992/003/ERR9920863/ERR9920863.fastq.gz
Capparis_spinosa: kingfisher get -r SRR17373648 -m ena-ascp aws-http prefetch
Capsicum_pubescens: kingfisher get -r SRR23352910 -m ena-ascp aws-http prefetch
Carya_illinoinensis: kingfisher get -r SRR13439040 -m ena-ascp aws-http prefetch; kingfisher get -r SRR13439041 -m ena-ascp aws-http prefetch; kingfisher get -r SRR13439042 -m ena-ascp aws-http prefetch; kingfisher get -r SRR13430771 -m ena-ascp aws-http prefetch
Chlamydomonas_reinhardtii: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR222/023/SRR22216323/SRR22216323_subreads.fastq.gz
Cinnamomum_camphora: kingfisher get -r SRR15881621 -m ena-ascp aws-http prefetch
Citrullus_lanatus: wget ftp://download.big.ac.cn/gsa/CRA005990/CRR380038/CRR380038.bam
Citrus_australis: kingfisher get -r SRR22943481 -m ena-ascp aws-http prefetch; kingfisher get -r SRR22922917 -m ena-ascp aws-http prefetch
Coriaria_nepalensis: kingfisher get -r SRR22412655 -m ena-ascp aws-http prefetch
Cucumis_melo: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR248/039/SRR24821439/SRR24821439_subreads.fastq.gz
Daucus_carota: kingfisher get -r SRR24710331 -m ena-ascp aws-http prefetch
Euphorbia_peplus: kingfisher get -r SRR19901591 -m ena-ascp aws-http prefetch
Fragaria_vesca: kingfisher get -r SRR22495382 -m ena-ascp aws-http prefetch
Galdieria_sulphuraria: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR197/012/SRR19760112/SRR19760112_subreads.fastq.gz
Glycine_max: kingfisher get -r SRR23004521 -m aws-http -f fasta --download-threads 8
Glycyrrhiza_uralensis: kingfisher get -r DRR400303	 -m ena-ascp aws-http prefetch
Haematococcus_pluvialis: kingfisher get -r SRR25425436 -m ena-ascp aws-http prefetch; kingfisher get -r SRR25425437 -m ena-ascp aws-http prefetch
Haloxylon_ammodendron: kingfisher get -r SRR17129371 -m ena-ascp aws-http prefetch
Helichrysum_umbraculigerum: kingfisher get -r ERR10735439 -m ena-ascp aws-http prefetch; kingfisher get -r ERR10735438 -m ena-ascp aws-http prefetch; kingfisher get -r ERR10735437 -m ena-ascp aws-http prefetch
Herpetospermum_pedunculosum: kingfisher get -r SRR22426905 -m ena-ascp aws-http prefetch
Ipomoea_cairica: kingfisher get -r SRR18493763 -m ena-ascp aws-http prefetch
Juglans_mandshurica: kingfisher get -r SRR14637189 -m ena-ascp aws-http prefetch
Kobresia_myosuroides: kingfisher get -r SRR20480255 -m ena-ascp aws-http prefetch
Linum_usitatissimum: kingfisher get -r SRR14339745 -m ena-ascp aws-http prefetch
Lycopodium_japonicum: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR247/035/SRR24785435/SRR24785435_subreads.fastq.gz
Manihot_esculenta: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR548/001/ERR5485301/ERR5485301.fastq.gz
Musa_acuminata: kingfisher get -r SRR24350321 -m ena-ascp aws-http prefetch
Ochroma_pyramidale: https://ftp.cngb.org/pub/CNSA/data5/CNP0001860/CNS0382078/CNX0400125/CNR0481800/m64154_210729_162945.subreads.ccs.fastq.gz; https://ftp.cngb.org/pub/CNSA/data5/CNP0001860/CNS0382078/CNX0400126/CNR0481801/m64236_210803_094029.subreads.ccs.fastq.gz
Oryza_sativa: wget https://download.cncb.ac.cn/gsa/CRA006531/CRR453545/CRR453545.bam; wget https://download.cncb.ac.cn/gsa/CRA006531/CRR453546/CRR453546.bam
Panicum_miliaceum: kingfisher get -r SRR20315261 -m ena-ascp aws-http prefetch; kingfisher get -r SRR20315262 -m ena-ascp aws-http prefetch; kingfisher get -r SRR20315263 -m ena-ascp aws-http prefetch
Perilla_frutescens: kingfisher get -r DRR361636 -m ena-ascp aws-http prefetch
Persea_americana: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR135/047/SRR13510947/SRR13510947_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR135/046/SRR13510946/SRR13510946_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR135/045/SRR13510945/SRR13510945_subreads.fastq.gz
Pohlia_nutans: wget https://download.cncb.ac.cn/gsa/CRA006048/CRR383826/CRR383826.bam
Rhodomyrtus_tomentosa: kingfisher get -r SRR24786875 -m ena-ascp aws-http prefetch
Salvia_hispanica: kingfisher get -r SRR20761289 -m ena-ascp aws-http prefetch
Sesamum_indicum: kingfisher get -r SRR21601246 -m ena-ascp aws-http prefetch
Silene_conica: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR224/055/SRR22499155/SRR22499155_subreads.fastq.gz
Solanum_lycopersicum: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR152/007/SRR15243707/SRR15243707_subreads.fastq.gz
Solanum_rostratum: kingfisher get -r SRR23354533 -m ena-ascp aws-http prefetch
Solanum_tuberosum: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/095/SRR15458995/SRR15458995_subreads.fastq.gz
Taxus_chinensis: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR147/067/SRR14756467/SRR14756467_subreads.fastq.gz
Thymus_quinquecostatus: kingfisher get -r SRR17509707 -m ena-ascp aws-http prefetch
Trapa_bicornis: kingfisher get -r SRR22185067 -m ena-ascp aws-http prefetch
Trifolium_repens: kingfisher get -r SRR24821882 -m ena-ascp aws-http prefetch; kingfisher get -r SRR24821883 -m ena-ascp aws-http prefetch
Triticum_monococcum: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/014/ERR11203114/ERR11203114.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/013/ERR11203113/ERR11203113.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/012/ERR11203112/ERR11203112.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/011/ERR11203111/ERR11203111.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/010/ERR11203110/ERR11203110.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/009/ERR11203109/ERR11203109.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/008/ERR11203108/ERR11203108.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR112/007/ERR11203107/ERR11203107.fastq.gz
Vitis_vinifera: kingfisher get -r SRR20810426 -m ena-ascp aws-http prefetch
Xanthoceras_sorbifolia: kingfisher get -r SRR23095608 -m ena-ascp aws-http prefetch
Zea_mays: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/014/SRR15447414/SRR15447414_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/015/SRR15447415/SRR15447415_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/016/SRR15447416/SRR15447416_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/018/SRR15447418/SRR15447418_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/019/SRR15447419/SRR15447419_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/020/SRR15447420/SRR15447420_subreads.fastq.gz; wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR154/021/SRR15447421/SRR15447421_subreads.fastq.gz
Zygnema_circumcarinatum: wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR244/096/SRR24451196/SRR24451196_subreads.fastq.gz
```
