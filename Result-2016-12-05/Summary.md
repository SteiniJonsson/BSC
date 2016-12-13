# Keyrsla 6. des 2016

## mothur10 - mothur.1480941150.logfile
### Kl. 12:38   
* **make.contigs(file=BSC16s.file,processors=10)**
* **summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.fasta,processors=10)**
* **screen.seqs(fasta=./outFiles/BSC16s.trim.contigs.fasta, group=./outFiles/BSC16s.contigs.groups, maxambig=0, maxlength=300,processors=10)**
      
   Engar villur/athugasemdir

## mothur20 - mothur.1480941508.logfile
### Kl. 16:14   
* **unique.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.fasta)**
* **count.seqs(name=./outFiles/BSC16s.trim.contigs.good.names, group=./outFiles/BSC16s.contigs.good.groups,processors=10)**
* **summary.seqs(count=./outFiles/BSC16s.trim.contigs.good.count_table,processors=10)**
* **align.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.fasta, reference=silva.v5.fasta,processors=10)**

   Hér kemur warning: [WARNING]: Some of your sequences generated alignments that eliminated too many bases, a list is provided in /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.flip.accnos. If you set the flip parameter to true mothur will try aligning the reverse compliment as well.

* **summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.align, count=./outFiles/BSC16s.trim.contigs.good.count_table,processors=10)**

   Start	End	NBases	Ambigs	Polymer	NumSeqs   
   Minimum:	0	0	0	0	1	1   
   2.5%-tile:	13862	23444	253	0	4	33682   
   25%-tile:	13862	23444	253	0	4	336816   
   Median: 	13862	23444	253	0	5	673631   
   75%-tile:	13862	23444	253	0	5	1010446   
   97.5%-tile:	13862	23444	254	0	7	1313580   
   Maximum:	26105	26105	296	0	25	1347261   
   Mean:	13898.7	23403.8	251.142	0	4.73304   
   no of unique seqs:	1140370   
   total # of seqs:	1347261   

* **screen.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.align, count=./outFiles/BSC16s.trim.contigs.good.count_table, summary=./outFiles/BSC16s.trim.contigs.good.unique.summary, start=13862, end=23444, maxhomop=8,processors=10)**
* **summary.seqs(fasta=current, count=current,processors=10)**  
* **filter.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.align, vertical=T, trump=.,processors=10)**
* **unique.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.fasta, count=./outFiles/BSC16s.trim.contigs.good.good.count_table)**
* **pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)**

* **chimera.uchime(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.count_table, dereplicate=t,processors=10)**
* **remove.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta, accnos=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.accnos)**

   Hér kemur warning: [WARNING]: This command can take a namefile and you did not provide one. The current namefile is /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.names which seems to match ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta.

* **summary.seqs(fasta=current, count=current,processors=10)**
* **classify.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, reference=./trainset/trainset14_032015.pds.fasta, taxonomy=./trainset/trainset14_032015.pds.tax, cutoff=80,processors=10)**

   <font color="Yellow">Hér koma 60 warning:</font> [WARNING]: M03555_131_000000000-ANG5J_1_2110_8359_5790 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.

* **remove.lineage(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.taxonomy, taxon=Chloroplast-Mitochondria-unknown-Archaea-Eukaryota)**

   Hér kemur 1 athugasemd: [NOTE]: The count file should contain only unique names, so mothur assumes your fasta, list and taxonomy files also contain only uniques.

## m19 - mothur.1480954466.logfile
### Kl. 16:40   
* **cluster.split(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, splitmethod=classify, taxlevel=4, cutoff=0.15,processors=10)**

> Engar athugasemdir   

## m20 - mothur.1480956027.logfile
### Kl. 16:40   
* **make.shared(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, label=0.03)**

> Engar athugasemdir   

## m21 - mothur.1480956038.logfile
### Kl. 16:40  

* **classify.otu(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, label=0.03)**

   Hér koma 5195 warning: [WARNING]: M03555_131_000000000-ANG5J_1_2105_9329_6374 is not in your taxonomy file.  I will not include it in the consensus.   
<font color="Yellow">Hér þarf að skoða hvort þetta sé stór hluti af niðurstöðunni og hvort þetta er eðililegt.</font>   

## m22 - mothur.1480956053.logfile
### Kl. 16:40   
* **phylotype(taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy)**
   Engar athugasemdir      

## m23 - mothur.1480956059.logfile
### Kl. 16:41   
* **make.shared(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, label=1)**

   <font color="Red">Hér koma 5195 villur:</font> [ERROR]: M03555_131_000000000-ANG5J_1_1101_10177_4300 is in your groupfile and not your listfile. Please correct.
   Þær eru tengdar warnings sem koma í classify.otu og því á sama athugasemd við hér og þar.

## m24 - mothur.1480956063.logfile
### Kl. 16:41   
* **classify.otu(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, label=1)**

   Engar athugasemdir   

## m25 - ekki keyrt
## m26 - ekki keyrt

## m27 - mothur.1480958996.logfile
* **mothur > system(mv ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.shared ./outFiles/BSC16s.an.shared)**
* **mothur > system(mv ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.taxonomy ./outFiles/BSC16s.an.cons.taxonomy)**   
   Engar athugasemdir   

## m28 - mothur.1480959017.logfile
* **mothur > count.groups(shared=./outFiles/BSC16s.an.shared)**
   * B8_01 contains 41878.
   * B8_02 contains 41523.
   * B8_03 contains 46241.
   * B8_04 contains 44744.
   * B8_05 contains 49954.
   * B8_06 contains 43502.
   * B8_07 contains 44889.
   * B8_08 contains 41396.
   * B8_09 contains 36619.
   * B8_10 contains 38036.
   * G_01 contains 35033.
   * G_02 contains 38991.
   * G_03 contains 42011.
   * G_04 contains 47549.
   * G_05 contains 47466.
   * G_06 contains 41295.
   * G_07 contains 35138.
   * G_08 contains 41442.
   * G_09 contains 37065.
   * G_10 contains 40194.
   * H8_01 contains 49457.
   * H8_02 contains 30597.
   * H8_03 contains 37188.
   * H8_04 contains 44568.
   * H8_05 contains 39951.
   * H8_06 contains 47882.
   * H8_07 contains 33153.
   * H8_08 contains 37163.
   * H8_09 contains 48533.
   * H8_10 contains 41781.
   
   Total seqs: 1245239.

## m29 - mothur.1480959029.logfile
* **mothur > sub.sample(shared=./outFiles/BSC16s.an.shared, size=2241)**
   Sampling 2241 from each group.
   0.03  
<font color="Yellow">Þarf að breyta size?</font>  

Output file ( BSC16s.an.0.03.subsample.shared ) er notað í eftirarandi skipunum:   
* heatmap.bin(shared=./outFiles/BSC16s.an.0.03.subsample.shared, scale=log2, numotu=50)
* venn(shared=./outFiles/BSC16s.an.0.03.subsample.shared, groups=F3D0-F3D1-F3D2-F3D3)
* corr.axes(axes=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes, shared=./outFiles/BSC16s.an.0.03.subsample.shared, method=spearman, numaxes=3)
* get.communitytype(shared=./outFiles/BSC16s.an.0.03.subsample.shared,processors=10)
* metastats(shared=./outFiles/BSC16s.an.0.03.subsample.shared, design=mouse.time.design,processors=10)
* classify.rf(shared=./outFiles/BSC16s.an.0.03.subsample.shared, design=mouse.time.design)
   

## m30 - mothur.1480959040.logfile
* **mothur > rarefaction.single(shared=./outFiles/BSC16s.an.shared, calc=sobs, freq=100,processors=10)**

## m31 - mothur.1480959078.logfile
* **mothur > summary.single(shared=./outFiles/BSC16s.an.shared, calc=nseqs-coverage-sobs-invsimpson, subsample=T)**  
<font color="Yellow">Er subsample rétt?</font>  

Breyttum subsample úr 2441 í T.  
Skv. manual þá er notuð stærð úr minnsta hópnum.
> The subsample parameter allows you to enter the size of the sample or you can set subsample=T and mothur will use the size of your smallest group in the case of a shared file. With a list, sabund or rabund file you must provide a subsample size.


## m32 - mothur.1480959215.logfile  
   Engar athugasemdir

## m33 - mothur.1480959229.logfile
   Engar athugasemdir  

## m34 - mothur.1480959552.logfile
   Engar athugasemdir  

## m35 - mothur.1480959563.logfile
   Engar athugasemdir  

## m36 - mothur.1480959573.logfile
   Engar athugasemdir  

## m37 - mothur.1480959586.logfile
   Engar athugasemdir  

## m38 - mothur.1480959597.logfile

* **mothur > parsimony(tree=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre, group=mouse.time.design,  groups=all,processors=10)**  
   Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
   Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design
   
   Using 10 processors.  
   <font color="Red">[ERROR]: did not complete parsimony.  
   Hér þarf að skoða parameters!</font>      

<font color="Yellow">Hvernig á mouse.time.design að líta út?
Dæmi af wiki er:
> F3D0	Early  
> F3D1	Early  
> F3D141	Late  
> F3D142	Late  
> F3D143	Late  
> F3D144	Late
</font>  

## m39 - mothur.1480960067.logfile
   Engar athugasemdir   

## m40 - mothur.1480960080.logfile
* **mothur > nmds(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist)**
   Processing Dimension: 2
   1
   2
   3
   4
   5
   6
   7
   8
   9
   10
   
   Number of dimensions:	2
   Lowest stress :	0.216387
   R-squared for configuration:	0.85933

## m41 - mothur.1480960090.logfile
* **mothur > nmds(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, mindim=3, maxdim=3)**
   Processing Dimension: 3
   1
   2
   3
   4
   5
   6
   7
   8
   9
   10
   
   Number of dimensions:	3
   Lowest stress :	0.1514
   R-squared for configuration:	0.886948

## m42 - mothur.1480960104.logfile
* **mothur > amova(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, design=mouse.time.design)**   
   Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
   Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design  
   <font color="Red">[ERROR]: did not complete amova.  
   Hér þarf að skoða parameters!</font>


## m43 - mothur.1480960226.logfile
* **mothur > homova(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, design=mouse.time.design)**
   Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
   Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design  
   <font color="Red">[ERROR]: did not complete homova.  
   Hér þarf að skoða parameters!</font>

## m44 - mothur.1480960259.logfile
* **mothur > corr.axes(axes=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes, shared=./outFiles/BSC16s.an.0.03.subsample.shared, method=spearman, numaxes=3)**
   You did not provide a label, I will use the first label in your inputfile.  
   <font color="Yellow">Þarf að bæta við label?</font>   

## m45 - mothur.1480960278.logfile
* **mothur > corr.axes(axes=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes, metadata=mouse.dpw.metadata, method=spearman, numaxes=3)**   
   Unable to open mouse.dpw.metadata. Trying default /usr/local/bin/mouse.dpw.metadata
   Unable to open /usr/local/bin/mouse.dpw.metadata. Trying mothur's location /usr/local/bin/mouse.dpw.metadata
   Unable to open /usr/local/bin/mouse.dpw.metadata. Trying output directory /data/data02/asta/testrun/outFiles/mouse.dpw.metadata
   Unable to open /data/data02/asta/testrun/outFiles/mouse.dpw.metadata
   You did not provide a label, I will use the first label in your inputfile.  
   <font color="Red">[ERROR]: did not complete corr.axes.  
   Hér þarf að skoða parameters!</font>

## m46 - mothur.1480960307.logfile
      
* mothur > get.communitytype(shared=./outFiles/BSC16s.an.0.03.subsample.shared,processors=10)   
   Using 1 processor
   0.03
   K	NLE		logDet	BIC		AIC		Laplace
   1	99950.2	5398.9	110508	106158	96944.92	109477	-3417.06	130594	121894	96358.4
   quitting command...
   3	123067	-12755.1	154742	141693	99573.3  
<font color="Red">Þetta fékk trúlega ekki að klára. Þarf að keyra aftur.</font>


## ?? - mothur.1480966892.logfile
   Engar athugasemdir   

## ?? - mothur.1481066810.logfile
* mothur > get.communitytype(shared=./outFiles/BSC16s.an.0.03.subsample.shared,processors=10)   
   Using 1 processor
   0.03
   K	NLE		logDet	BIC		AIC		Laplace
   1	99950.2	5398.9	110508	106158	96944.92	109477	-3421.14	130594	121894	96356.43	124296	-14139.4	155972	142922	1001114	140046	inf	182280	164881	inf5	153334	-35888.3	206127	184378	106862

## m47 - mothur.1481101793.logfile
* mothur > metastats(shared=./outFiles/BSC16s.an.0.03.subsample.shared, design=mouse.time.design,processors=10)   
   Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
   Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
   Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design

   Using 10 processors.   
   <font color="Red">[ERROR]: did not complete metastats.   
   Hér þarf að skoða parameters!      
   </font>

## m48, m49, m50 og m51 hafa ekki verið keyrð.
# Endir
