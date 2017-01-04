Linux version

Using ReadLine

Running 64Bit Version

mothur v.1.38.1
Last updated: 8/9/2016

by
Patrick D. Schloss

Department of Microbiology & Immunology
University of Michigan
pschloss@umich.edu
http://www.mothur.org

When using, please cite:
Schloss, P.D., et al., Introducing mothur: Open-source, platform-independent, community-supported software for describing and comparing microbial communities. Appl Environ Microbiol, 2009. 75(23):7537-41.

Distributed under the GNU General Public License

Type 'help()' for information on the commands that are available

Type 'quit()' to exit program
Batch Mode


mothur > set.dir(output=./outFiles)
Mothur's directories:
outputDir=/home/asta/testcombi/outFiles/

mothur > make.contigs(file=BSC16s.file,processors=10)

Using 10 processors.

>>>>>	Processing file pair B8_allar_R1.fastq - B8_allar_R2.fastq (files 1 of 3)	<<<<<
Making contigs...
Done.

It took 105 secs to assemble 549227 reads.


>>>>>	Processing file pair G_allar_R1.fastq - G_allar_R2.fastq (files 2 of 3)	<<<<<
Making contigs...
Done.

It took 92 secs to assemble 508109 reads.


>>>>>	Processing file pair H8_allar_R1.fastq - H8_allar_R2.fastq (files 3 of 3)	<<<<<
Making contigs...
Done.

It took 100 secs to assemble 536989 reads.

It took 297 secs to process 1594325 sequences.

Group count: 
B8	549227
G	508109
H8	536989

Total of all groups is 1594325

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.fasta
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.qual
/home/asta/testcombi/outFiles/BSC16s.contigs.report
/home/asta/testcombi/outFiles/BSC16s.scrap.contigs.fasta
/home/asta/testcombi/outFiles/BSC16s.scrap.contigs.qual
/home/asta/testcombi/outFiles/BSC16s.contigs.groups

[WARNING]: your sequence names contained ':'.  I changed them to '_' to avoid problems in your downstream analysis.

mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.fasta,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	1	250	250	0	3	1
2.5%-tile:	1	292	292	0	4	39859
25%-tile:	1	294	294	0	4	398582
Median: 	1	295	295	0	5	797163
75%-tile:	1	296	296	0	5	1195744
97.5%-tile:	1	362	362	3	7	1554467
Maximum:	1	500	500	95	250	1594325
Mean:	1	298.519	298.519	0.345685	4.83609
# of Seqs:	1594325

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.summary

It took 6 secs to summarize 1594325 sequences.

mothur > screen.seqs(fasta=./outFiles/BSC16s.trim.contigs.fasta, group=./outFiles/BSC16s.contigs.groups, maxambig=0, maxlength=300,processors=10)

Using 10 processors.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.fasta
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.bad.accnos
/home/asta/testcombi/outFiles/BSC16s.contigs.good.groups


It took 11 secs to screen 1594325 sequences.

mothur > unique.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.fasta)
1347261	1140370

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.names
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.fasta


mothur > count.seqs(name=./outFiles/BSC16s.trim.contigs.good.names, group=./outFiles/BSC16s.contigs.good.groups,processors=10)

Using 10 processors.
It took 7 secs to create a table for 1347261 sequences.


Total number of sequences: 1347261

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.count_table


mothur > summary.seqs(count=./outFiles/BSC16s.trim.contigs.good.count_table,processors=10)
Using /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.fasta as input file for the fasta parameter.

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	1	250	250	0	3	1
2.5%-tile:	1	292	292	0	4	33682
25%-tile:	1	294	294	0	4	336816
Median: 	1	295	295	0	5	673631
75%-tile:	1	296	296	0	5	1010446
97.5%-tile:	1	298	298	0	7	1313580
Maximum:	1	300	300	0	41	1347261
Mean:	1	294.665	294.665	0	4.76457
# of unique seqs:	1140370
total # of seqs:	1347261

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.summary

It took 12 secs to summarize 1347261 sequences.

mothur > align.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.fasta, reference=silva.v5.fasta,processors=10)

Using 10 processors.

Reading in the silva.v5.fasta template sequences...	DONE.
It took 237 to read  135907 sequences.
Aligning sequences from ./outFiles/BSC16s.trim.contigs.good.unique.fasta ...
[WARNING]: Some of your sequences generated alignments that eliminated too many bases, a list is provided in /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.flip.accnos. If you set the flip parameter to true mothur will try aligning the reverse compliment as well.
It took 2043 secs to align 1140370 sequences.


Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.align
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.align.report
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.flip.accnos


mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.align, count=./outFiles/BSC16s.trim.contigs.good.count_table,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	0	0	0	0	1	1
2.5%-tile:	13862	23444	253	0	4	33682
25%-tile:	13862	23444	253	0	4	336816
Median: 	13862	23444	253	0	5	673631
75%-tile:	13862	23444	253	0	5	1010446
97.5%-tile:	13862	23444	254	0	7	1313580
Maximum:	26105	26105	296	0	25	1347261
Mean:	13898.7	23403.8	251.142	0	4.73304
# of unique seqs:	1140370
total # of seqs:	1347261

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.summary

It took 230 secs to summarize 1347261 sequences.

mothur > screen.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.align, count=./outFiles/BSC16s.trim.contigs.good.count_table, summary=./outFiles/BSC16s.trim.contigs.good.unique.summary, start=13862, end=23444, maxhomop=8,processors=10)

Using 10 processors.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.summary
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.align
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.bad.accnos
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.good.count_table


It took 763 secs to screen 1140370 sequences.

mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.align, count=./outFiles/BSC16s.trim.contigs.good.good.count_table,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	13836	23444	239	0	3	1
2.5%-tile:	13862	23444	253	0	4	33307
25%-tile:	13862	23444	253	0	4	333063
Median: 	13862	23444	253	0	5	666126
75%-tile:	13862	23444	253	0	5	999188
97.5%-tile:	13862	23444	254	0	7	1298944
Maximum:	13862	25359	276	0	8	1332250
Mean:	13861.9	23444	253.148	0	4.75286
# of unique seqs:	1126753
total # of seqs:	1332250

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.summary

It took 213 secs to summarize 1332250 sequences.

mothur > filter.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.align, vertical=T, trump=.,processors=10)

Using 10 processors.
Creating Filter... 


Running Filter... 



Length of filtered alignment: 577
Number of columns removed: 49423
Length of the original alignment: 50000
Number of sequences used to construct filter: 1126753

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.filter
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.fasta


mothur > unique.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.fasta, count=./outFiles/BSC16s.trim.contigs.good.good.count_table)
1126753	457329

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta


mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group G:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group H8:
158490	48537	109953
Total number of sequences before pre.cluster was 158490.
pre.cluster removed 109953 sequences.

It took 1256 secs to cluster 158490 sequences.
178747	63032	115715
Total number of sequences before pre.cluster was 178747.
pre.cluster removed 115715 sequences.

It took 1976 secs to cluster 178747 sequences.
172224	66186	106038
Total number of sequences before pre.cluster was 172224.
pre.cluster removed 106038 sequences.

It took 2147 secs to cluster 172224 sequences.
It took 2184 secs to run pre.cluster.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.count_table
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8.map
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.G.map
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.H8.map


mothur > chimera.uchime(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.count_table, dereplicate=t,processors=10)

Using 10 processors.

uchime by Robert C. Edgar
http://drive5.com/uchime
This code is donated to the public domain.

Checking sequences from ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta ...

It took 35234 secs to check 48537 sequences from group G.

It took 52503 secs to check 63032 sequences from group B8.

It took 53879 secs to check 66186 sequences from group H8.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.chimeras
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.accnos


mothur > remove.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta, accnos=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.accnos)
[WARNING]: This command can take a namefile and you did not provide one. The current namefile is /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.names which seems to match ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta.
Removed 70091 sequences from your fasta file.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta


mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	1	577	239	0	3	1
2.5%-tile:	1	577	253	0	4	31078
25%-tile:	1	577	253	0	4	310774
Median: 	1	577	253	0	5	621547
75%-tile:	1	577	253	0	5	932320
97.5%-tile:	1	577	254	0	7	1212015
Maximum:	1	577	273	0	8	1243092
Mean:	1	577	253.099	0	4.72778
# of unique seqs:	96706
total # of seqs:	1243092

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.summary

It took 2 secs to summarize 1243092 sequences.

mothur > classify.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, reference=./trainset/trainset14_032015.pds.fasta, taxonomy=./trainset/trainset14_032015.pds.tax, cutoff=80,processors=10)

Using 10 processors.
Reading template taxonomy...     DONE.
Reading template probabilities...     DONE.
It took 10 seconds get probabilities. 
Classifying sequences from ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta ...
[WARNING]: M03555_131_000000000-ANG5J_1_1111_25289_9776 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_19715_7001 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_21155_23614 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7494_5232 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_3634_18060 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_28902_15277 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_8163_16392 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_12647_9095 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_14833_6029 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_6528_24251 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_25073_5358 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_17857_12829 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_20545_26915 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_17848_8718 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_9077_23786 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_9198_19726 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_11100_23408 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19507_18928 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17430_4580 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_8359_5790 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17071_2863 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_19349_23830 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22462_10441 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_19146_26206 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24722_20398 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19926_6238 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_12761_24470 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_16894_10881 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_13410_24700 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_28179_16163 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_5877_13877 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_18477_1849 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_7322_21890 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_15693_2055 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24880_13823 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_20540_17710 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_14705_19522 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_11346_20568 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_19729_18668 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_17363_22510 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_11644_16755 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_7769_10263 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10412_27917 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_19446_11226 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_15416_21023 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_3848_19386 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_27003_17585 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_18787_22679 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_22550_26361 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_3266_14826 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_20108_9521 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20164_15476 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.

It took 246 secs to classify 96706 sequences.


It took 5 secs to create the summary file for 96706 sequences.


Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.taxonomy
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.tax.summary


mothur > remove.lineage(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.taxonomy, taxon=unknown)

[NOTE]: The count file should contain only unique names, so mothur assumes your fasta, list and taxonomy files also contain only uniques.


Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pick.fasta
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.pick.count_table


mothur > cluster.split(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, splitmethod=classify, taxlevel=4, cutoff=0.15,processors=10)

Using 10 processors.
Splitting the file...
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.dist

It took 15 seconds to calculate the distances for 2909 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist

It took 50 seconds to calculate the distances for 8776 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist

It took 197 seconds to calculate the distances for 21272 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.dist

It took 1 seconds to calculate the distances for 947 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.dist

It took 14 seconds to calculate the distances for 3675 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.dist

It took 1 seconds to calculate the distances for 564 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.dist

It took 2 seconds to calculate the distances for 579 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist

It took 6 seconds to calculate the distances for 2375 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.dist

It took 14 seconds to calculate the distances for 3584 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist

It took 5 seconds to calculate the distances for 2188 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.dist

It took 2 seconds to calculate the distances for 1189 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.dist

It took 11 seconds to calculate the distances for 3184 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.dist

It took 2 seconds to calculate the distances for 683 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.dist

It took 1 seconds to calculate the distances for 400 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.dist

It took 2 seconds to calculate the distances for 711 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.dist

It took 1 seconds to calculate the distances for 329 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.dist

It took 3 seconds to calculate the distances for 1480 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist

It took 7 seconds to calculate the distances for 2297 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.dist

It took 2 seconds to calculate the distances for 957 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.dist

It took 4 seconds to calculate the distances for 1813 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.dist

It took 2 seconds to calculate the distances for 69 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.dist

It took 8 seconds to calculate the distances for 2902 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.dist

It took 3 seconds to calculate the distances for 1342 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.dist

It took 2 seconds to calculate the distances for 1135 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.dist

It took 2 seconds to calculate the distances for 646 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.dist

It took 21 seconds to calculate the distances for 4313 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.dist

It took 30 seconds to calculate the distances for 5275 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.dist

It took 3 seconds to calculate the distances for 1484 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.dist

It took 6 seconds to calculate the distances for 2090 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.dist

It took 2 seconds to calculate the distances for 863 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist

It took 3 seconds to calculate the distances for 1071 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.dist

It took 1 seconds to calculate the distances for 716 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.dist

It took 2 seconds to calculate the distances for 574 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.dist

It took 4 seconds to calculate the distances for 1500 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.dist

It took 4 seconds to calculate the distances for 1300 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.dist

It took 2 seconds to calculate the distances for 843 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.dist

It took 1 seconds to calculate the distances for 701 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.dist

It took 2 seconds to calculate the distances for 194 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.dist

It took 1 seconds to calculate the distances for 493 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.dist

It took 2 seconds to calculate the distances for 364 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.dist

It took 1 seconds to calculate the distances for 134 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.dist

It took 2 seconds to calculate the distances for 786 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist

It took 1 seconds to calculate the distances for 17 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist

It took 1 seconds to calculate the distances for 306 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.dist

It took 1 seconds to calculate the distances for 61 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.dist

It took 2 seconds to calculate the distances for 24 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.dist

It took 1 seconds to calculate the distances for 226 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.dist

It took 1 seconds to calculate the distances for 91 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.dist

It took 2 seconds to calculate the distances for 174 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.dist

It took 1 seconds to calculate the distances for 20 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist

It took 1 seconds to calculate the distances for 69 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist

It took 2 seconds to calculate the distances for 858 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.dist

It took 1 seconds to calculate the distances for 100 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.dist

It took 1 seconds to calculate the distances for 86 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.dist

It took 2 seconds to calculate the distances for 343 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.dist

It took 1 seconds to calculate the distances for 302 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.dist

It took 2 seconds to calculate the distances for 18 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.dist

It took 2 seconds to calculate the distances for 1203 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.dist

It took 2 seconds to calculate the distances for 175 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist

It took 1 seconds to calculate the distances for 440 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist

It took 1 seconds to calculate the distances for 344 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.dist

It took 2 seconds to calculate the distances for 494 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist

It took 1 seconds to calculate the distances for 357 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist

It took 1 seconds to calculate the distances for 198 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.dist

It took 1 seconds to calculate the distances for 13 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.dist

It took 2 seconds to calculate the distances for 307 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.dist

It took 1 seconds to calculate the distances for 245 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.dist

It took 1 seconds to calculate the distances for 392 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist

It took 1 seconds to calculate the distances for 80 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.dist

It took 2 seconds to calculate the distances for 106 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.dist

It took 1 seconds to calculate the distances for 85 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.dist

It took 1 seconds to calculate the distances for 99 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.dist

It took 2 seconds to calculate the distances for 63 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.dist

It took 1 seconds to calculate the distances for 62 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.dist

It took 1 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist

It took 1 seconds to calculate the distances for 10 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.dist

It took 1 seconds to calculate the distances for 68 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.dist

It took 2 seconds to calculate the distances for 8 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist

It took 1 seconds to calculate the distances for 21 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.dist

It took 1 seconds to calculate the distances for 89 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist

It took 1 seconds to calculate the distances for 29 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.dist

It took 2 seconds to calculate the distances for 12 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.dist

It took 1 seconds to calculate the distances for 38 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.dist

It took 1 seconds to calculate the distances for 16 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.dist

It took 1 seconds to calculate the distances for 12 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.dist

It took 2 seconds to calculate the distances for 25 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.dist

It took 0 seconds to calculate the distances for 4 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.dist is blank. This can result if there are no distances below your cutoff.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.dist

It took 2 seconds to calculate the distances for 7 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.dist

It took 1 seconds to calculate the distances for 43 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.dist

It took 1 seconds to calculate the distances for 14 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.dist

It took 1 seconds to calculate the distances for 32 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

It took 1 seconds to calculate the distances for 11 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.dist

It took 2 seconds to calculate the distances for 19 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.dist

It took 1 seconds to calculate the distances for 10 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.96.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.96.dist

It took 1 seconds to calculate the distances for 16 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.97.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.97.dist

It took 1 seconds to calculate the distances for 13 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.98.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.98.dist is blank. This can result if there are no distances below your cutoff.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.98.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.99.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.99.dist

It took 1 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.100.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.100.dist

It took 2 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.101.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.101.dist

It took 1 seconds to calculate the distances for 4 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.102.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.102.dist

It took 1 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.103.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.103.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.104.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.104.dist

It took 1 seconds to calculate the distances for 10 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.105.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.105.dist

It took 1 seconds to calculate the distances for 5 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

It took 1 seconds to calculate the distances for 3 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist

It took 1 seconds to calculate the distances for 4 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.108.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.108.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.109.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.109.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.110.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.110.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.111.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.111.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.112.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.112.dist

It took 0 seconds to calculate the distances for 3 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.113.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.113.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.114.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.114.dist

It took 1 seconds to calculate the distances for 3 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.115.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.115.dist

It took 1 seconds to calculate the distances for 5 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.116.temp, processors=10, cutoff=0.15, outputdir=/home/asta/testcombi/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.116.dist

It took 0 seconds to calculate the distances for 2 sequences.
It took 576 seconds to split the distance file.
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
Cutoff was 0.15 changed cutoff to 0.13

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.109.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.109.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.101.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.101.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.97.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.97.dist
Cutoff was 0.15 changed cutoff to 0.15

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.96.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.96.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.103.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.103.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.112.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.112.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.102.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.102.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.110.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.110.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.99.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.99.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.116.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.116.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.100.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.100.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.dist
Cutoff was 0.15 changed cutoff to 0.14

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.114.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.114.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.dist
Cutoff was 0.15 changed cutoff to 0.15

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.113.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.113.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.115.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.115.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.dist
Cutoff was 0.15 changed cutoff to 0.14

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.108.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.107.dist
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.106.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.108.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.104.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.104.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.dist
Cutoff was 0.15 changed cutoff to 0.05

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.dist
Cutoff was 0.15 changed cutoff to 0.06

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.dist
Cutoff was 0.15 changed cutoff to 0.13

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.105.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.105.dist

Reading /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.111.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.111.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.dist
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.06
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.dist
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.05
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.05

Cutoff was 0.15 changed cutoff to 0.05
It took 346 seconds to cluster
Merging the clustered files...
It took 17 seconds to merge.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list


mothur > make.shared(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, label=0.03)
0.03

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.shared


mothur > classify.otu(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, label=0.03)
0.03	22866
[WARNING]: M03555_131_000000000-ANG5J_1_2104_18477_1849 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_7322_21890 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_9077_23786 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_11346_20568 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_17848_8718 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17071_2863 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_21155_23614 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22462_10441 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_15693_2055 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_19146_26206 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_7769_10263 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_8359_5790 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19926_6238 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_27003_17585 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_20108_9521 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_19349_23830 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_3266_14826 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_25073_5358 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_20540_17710 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_17363_22510 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7494_5232 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_19729_18668 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_20545_26915 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_28902_15277 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_19446_11226 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_14705_19522 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_11100_23408 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_12647_9095 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_16894_10881 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19507_18928 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_13410_24700 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24722_20398 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17430_4580 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_12761_24470 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_8163_16392 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_19715_7001 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_28179_16163 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_17857_12829 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_11644_16755 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_18787_22679 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_5877_13877 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_22550_26361 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24880_13823 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_14833_6029 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_6528_24251 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_3848_19386 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_25289_9776 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10412_27917 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20164_15476 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_15416_21023 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_9198_19726 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_3634_18060 is not in your taxonomy file.  I will not include it in the consensus.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.taxonomy
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.tax.summary


mothur > phylotype(taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy)
[WARNING]: This command can take a namefile and you did not provide one. The current namefile is /home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.names which seems to match ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy.
1
2
3
4
5
6

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.sabund](BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.sabund)  
[/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.rabund](BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.rabund)  
[/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list](BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list)  


mothur > make.shared(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, label=1)
[ERROR]: M03555_131_000000000-ANG5J_1_1101_18787_22679 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_20108_9521 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_3266_14826 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_3848_19386 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_19446_11226 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_10412_27917 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_17430_4580 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19507_18928 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19926_6238 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_19715_7001 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_6528_24251 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_14833_6029 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_28902_15277 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_3634_18060 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_25289_9776 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_7322_21890 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_7769_10263 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_19729_18668 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_28179_16163 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_12761_24470 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_24722_20398 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_24880_13823 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_19146_26206 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_9077_23786 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_22462_10441 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_5877_13877 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_8163_16392 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_18477_1849 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_9198_19726 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_25073_5358 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_12647_9095 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7494_5232 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_11644_16755 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_20545_26915 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_21155_23614 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_27003_17585 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_15416_21023 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_17363_22510 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_17848_8718 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_11346_20568 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_13410_24700 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_14705_19522 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_16894_10881 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_20540_17710 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_22550_26361 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_8359_5790 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_17071_2863 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_17857_12829 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_15693_2055 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_19349_23830 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_11100_23408 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_20164_15476 is in your groupfile and not your listfile. Please correct.
Your group file contains 96706 sequences and list file contains 96654 sequences. Please correct.

Output File Names: 
/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.shared


mothur > classify.otu(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, label=1)
1	426

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.1.cons.taxonomy](BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.1.cons.taxonomy)  
[/home/asta/testcombi/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.1.cons.tax.summary](BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.1.cons.tax.summary)  


mothur > system(mv ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.shared ./outFiles/BSC16s.an.shared)


mothur > system(mv ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.taxonomy ./outFiles/BSC16s.an.cons.taxonomy)


mothur > count.groups(shared=./outFiles/BSC16s.an.shared)
B8 contains 428134.
G contains 406296.
H8 contains 408662.

Total seqs: 1243092.

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.count.summary](BSC16s.an.count.summary)  


mothur > sub.sample(shared=./outFiles/BSC16s.an.shared, size=30597)
Sampling 30597 from each group.
0.03

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.0.03.subsample.shared](BSC16s.an.0.03.subsample.shared)  


mothur > rarefaction.single(shared=./outFiles/BSC16s.an.shared, calc=sobs, freq=100,processors=10)

Using 10 processors.

Processing group B8

0.03

Processing group G

0.03

Processing group H8

0.03

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.groups.rarefaction](BSC16s.an.groups.rarefaction)  


mothur > summary.single(shared=./outFiles/BSC16s.an.shared, calc=nseqs-coverage-sobs-invsimpson, subsample=T)

Processing group B8

0.03

Processing group G

0.03

Processing group H8

0.03

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.groups.ave-std.summary](BSC16s.an.groups.ave-std.summary)  
[/home/asta/testcombi/outFiles/BSC16s.an.groups.summary](BSC16s.an.groups.summary)  


mothur > heatmap.bin(shared=./outFiles/BSC16s.an.0.03.subsample.shared, scale=log2, numotu=50)
0.03

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.0.03.subsample.0.03.heatmap.bin.svg](BSC16s.an.0.03.subsample.0.03.heatmap.bin.svg)  


mothur > dist.shared(shared=./outFiles/BSC16s.an.shared, calc=thetayc-jclass, subsample=2241,processors=10)

Using 10 processors.
0.03

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.dist](BSC16s.an.thetayc.0.03.lt.dist)  
[/home/asta/testcombi/outFiles/BSC16s.an.jclass.0.03.lt.dist](BSC16s.an.jclass.0.03.lt.dist)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist](BSC16s.an.thetayc.0.03.lt.ave.dist)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.std.dist](BSC16s.an.thetayc.0.03.lt.std.dist)  
[/home/asta/testcombi/outFiles/BSC16s.an.jclass.0.03.lt.ave.dist](BSC16s.an.jclass.0.03.lt.ave.dist)  
[/home/asta/testcombi/outFiles/BSC16s.an.jclass.0.03.lt.std.dist](BSC16s.an.jclass.0.03.lt.std.dist)  


mothur > heatmap.sim(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist)

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.heatmap.sim.svg](BSC16s.an.thetayc.0.03.lt.ave.heatmap.sim.svg)  


mothur > heatmap.sim(phylip=./outFiles/BSC16s.an.jclass.0.03.lt.ave.dist)

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.jclass.0.03.lt.ave.heatmap.sim.svg](BSC16s.an.jclass.0.03.lt.ave.heatmap.sim.svg)  


mothur > venn(shared=./outFiles/BSC16s.an.0.03.subsample.shared, groups=birki_vidi_eyjur_H-birki_vidi_eyjur_B-vakalag)
birki_vidi_eyjur_B is not a valid group, and will be disregarded.
birki_vidi_eyjur_H is not a valid group, and will be disregarded.
vakalag is not a valid group, and will be disregarded.
You provided no valid groups. I will run the command using all the groups in your file.
0.03

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8-G-H8.svg](BSC16s.an.0.03.subsample.0.03.sharedsobs.B8-G-H8.svg)  
[/home/asta/testcombi/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8-G-H8.sharedotus](BSC16s.an.0.03.subsample.0.03.sharedsobs.B8-G-H8.sharedotus)  


mothur > tree.shared(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist,processors=10)

Using 10 processors.
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************
Tree complete. 

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre](BSC16s.an.thetayc.0.03.lt.ave.tre)  


mothur > parsimony(tree=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre, group=skan.sample.design,  groups=all,processors=10)

Using 10 processors.
********************#****#****#****#****#****#****#****#****#****#****#
Comparing to random:|||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************
Tree#	Groups	ParsScore	ParsSig
1	birki_vidi_eyjur_B-birki_vidi_eyjur_H	1	1
1	birki_vidi_eyjur_B-vakalag	1	1
1	birki_vidi_eyjur_H-vakalag	1	1

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre.parsimony](BSC16s.an.thetayc.0.03.lt.ave.tre.parsimony)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre.psummary](BSC16s.an.thetayc.0.03.lt.ave.tre.psummary)  


mothur > pcoa(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist)

Processing...
Rsq 1 axis: 0.998589
Rsq 2 axis: 1
Rsq 3 axis: 1

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.pcoa.axes](BSC16s.an.thetayc.0.03.lt.ave.pcoa.axes)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.pcoa.loadings](BSC16s.an.thetayc.0.03.lt.ave.pcoa.loadings)  


mothur > nmds(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist)
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
Lowest stress :	3.56958e-12
R-squared for configuration:	1

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.iters](BSC16s.an.thetayc.0.03.lt.ave.nmds.iters)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.stress](BSC16s.an.thetayc.0.03.lt.ave.nmds.stress)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes](BSC16s.an.thetayc.0.03.lt.ave.nmds.axes)  


mothur > nmds(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, mindim=3, maxdim=3)
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
Lowest stress :	3.3984e-12
R-squared for configuration:	1

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.iters](BSC16s.an.thetayc.0.03.lt.ave.nmds.iters)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.stress](BSC16s.an.thetayc.0.03.lt.ave.nmds.stress)  
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes](BSC16s.an.thetayc.0.03.lt.ave.nmds.axes)  


mothur > amova(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, design=skan.sample.design)
birki_vidi_eyjur_B-birki_vidi_eyjur_H-vakalag	Among	Within	Total
SS	0.319649	0	0.319649
df	2	0	2
MS	0.159824	-nan

Fs:	-nan
p-value: 1

Experiment-wise error rate: 0.05
If you have borderline P-values, you should try increasing the number of iterations

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.amova](BSC16s.an.thetayc.0.03.lt.ave.amova)  


mothur > homova(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, design=skan.sample.design)
HOMOVA	BValue	P-value	SSwithin/(Ni-1)_values
birki_vidi_eyjur_B-birki_vidi_eyjur_H-vakalag	-nan	<0.001*	-nan	-nan	-nan
birki_vidi_eyjur_B-birki_vidi_eyjur_H	-nan	<0.001*	-nan	-nan
birki_vidi_eyjur_B-vakalag	-nan	<0.001*	-nan	-nan
birki_vidi_eyjur_H-vakalag	-nan	<0.001*	-nan	-nan

Experiment-wise error rate: 0.05
Pair-wise error rate (Bonferroni): 0.0166667
If you have borderline P-values, you should try increasing the number of iterations

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.thetayc.0.03.lt.ave.homova](BSC16s.an.thetayc.0.03.lt.ave.homova)  


mothur > corr.axes(axes=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes, shared=./outFiles/BSC16s.an.0.03.subsample.shared, method=spearman, numaxes=3)
You did not provide a label, I will use the first label in your inputfile.

Output File Names: 
[/home/asta/testcombi/outFiles/BSC16s.an.0.03.subsample.spearman.corr.axes](BSC16s.an.0.03.subsample.spearman.corr.axes)  


mothur > metastats(shared=./outFiles/BSC16s.an.0.03.subsample.shared, design=skan.sample.design,processors=10)

Using 10 processors.
0.03
Comparing birki_vidi_eyjur_H and birki_vidi_eyjur_B...

Comparing vakalag and birki_vidi_eyjur_B...





Comparing vakalag and birki_vidi_eyjur_H...




Output File Names: 


mothur > quit()


************************************************************
************************************************************
************************************************************
Detected 52 [ERROR] messages, please review.
************************************************************
************************************************************
************************************************************


<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
Detected 58 [WARNING] messages, please review.
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
