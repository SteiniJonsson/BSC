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


#10. Reducing sequencing and PCR errors

mothur > set.dir(output=./outFiles)
Mothur's directories:
outputDir=/data/data02/asta/testrun/outFiles/

mothur > make.contigs(file=BSC16s.file,processors=10)

Using 10 processors.

>>>>>	Processing file pair B8_01_16s_R1.fastq - B8_01_16s_R2.fastq (files 1 of 10)	<<<<<
Making contigs...
Done.

It took 12 secs to assemble 53285 reads.


>>>>>	Processing file pair B8_02_16s_R1.fastq - B8_02_16s_R2.fastq (files 2 of 10)	<<<<<
Making contigs...
Done.

It took 11 secs to assemble 54223 reads.


>>>>>	Processing file pair B8_03_16s_R1.fastq - B8_03_16s_R2.fastq (files 3 of 10)	<<<<<
Making contigs...
Done.

It took 11 secs to assemble 57745 reads.


>>>>>	Processing file pair B8_04_16s_R1.fastq - B8_04_16s_R2.fastq (files 4 of 10)	<<<<<
Making contigs...
Done.

It took 10 secs to assemble 58440 reads.


>>>>>	Processing file pair B8_05_16s_R1.fastq - B8_05_16s_R2.fastq (files 5 of 10)	<<<<<
Making contigs...
Done.

It took 13 secs to assemble 63311 reads.


>>>>>	Processing file pair B8_06_16s_R1.fastq - B8_06_16s_R2.fastq (files 6 of 10)	<<<<<
Making contigs...
Done.

It took 10 secs to assemble 57959 reads.


>>>>>	Processing file pair B8_07_16s_R1.fastq - B8_07_16s_R2.fastq (files 7 of 10)	<<<<<
Making contigs...
Done.

It took 12 secs to assemble 59108 reads.


>>>>>	Processing file pair B8_08_16s_R1.fastq - B8_08_16s_R2.fastq (files 8 of 10)	<<<<<
Making contigs...
Done.

It took 10 secs to assemble 53536 reads.


>>>>>	Processing file pair B8_09_16s_R1.fastq - B8_09_16s_R2.fastq (files 9 of 10)	<<<<<
Making contigs...
Done.

It took 8 secs to assemble 45686 reads.


>>>>>	Processing file pair B8_10_16s_R1.fastq - B8_10_16s_R2.fastq (files 10 of 10)	<<<<<
Making contigs...
Done.

It took 9 secs to assemble 45934 reads.

It took 106 secs to process 549227 sequences.

Group count: 
B8_01	53285
B8_02	54223
B8_03	57745
B8_04	58440
B8_05	63311
B8_06	57959
B8_07	59108
B8_08	53536
B8_09	45686
B8_10	45934

Total of all groups is 549227

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.fasta
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.qual
/data/data02/asta/testrun/outFiles/BSC16s.contigs.report
/data/data02/asta/testrun/outFiles/BSC16s.scrap.contigs.fasta
/data/data02/asta/testrun/outFiles/BSC16s.scrap.contigs.qual
/data/data02/asta/testrun/outFiles/BSC16s.contigs.groups

[WARNING]: your sequence names contained ':'.  I changed them to '_' to avoid problems in your downstream analysis.

mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.fasta,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	1	250	250	0	3	1
2.5%-tile:	1	292	292	0	4	13731
25%-tile:	1	294	294	0	4	137307
Median: 	1	295	295	0	5	274614
75%-tile:	1	296	296	0	5	411921
97.5%-tile:	1	363	363	3	7	535497
Maximum:	1	500	500	95	250	549227
Mean:	1	298.604	298.604	0.346363	4.82365
# of Seqs:	549227

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.summary

It took 2 secs to summarize 549227 sequences.

mothur > screen.seqs(fasta=./outFiles/BSC16s.trim.contigs.fasta, group=./outFiles/BSC16s.contigs.groups, maxambig=0, maxlength=300,processors=10)

Using 10 processors.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.fasta
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.bad.accnos
/data/data02/asta/testrun/outFiles/BSC16s.contigs.good.groups


It took 4 secs to screen 549227 sequences.

# 20. Processing improved sequences

mothur > unique.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.fasta)
463980	420967

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.names
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.fasta


mothur > count.seqs(name=./outFiles/BSC16s.trim.contigs.good.names, group=./outFiles/BSC16s.contigs.good.groups,processors=10)

Using 10 processors.
It took 3 secs to create a table for 463980 sequences.


Total number of sequences: 463980

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.count_table


mothur > summary.seqs(count=./outFiles/BSC16s.trim.contigs.good.count_table,processors=10)
Using /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.fasta as input file for the fasta parameter.

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	1	250	250	0	3	1
2.5%-tile:	1	292	292	0	4	11600
25%-tile:	1	294	294	0	4	115996
Median: 	1	295	295	0	5	231991
75%-tile:	1	296	296	0	5	347986
97.5%-tile:	1	298	298	0	7	452381
Maximum:	1	300	300	0	37	463980
Mean:	1	294.736	294.736	0	4.74903
# of unique seqs:	420967
total # of seqs:	463980

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.summary

It took 4 secs to summarize 463980 sequences.

mothur > align.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.fasta, reference=silva.v5.fasta,processors=10)

Using 10 processors.

Reading in the silva.v5.fasta template sequences...	DONE.
It took 220 to read  135907 sequences.
Aligning sequences from ./outFiles/BSC16s.trim.contigs.good.unique.fasta ...
[WARNING]: Some of your sequences generated alignments that eliminated too many bases, a list is provided in /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.flip.accnos. If you set the flip parameter to true mothur will try aligning the reverse compliment as well.
It took 740 secs to align 420967 sequences.


Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.align
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.align.report
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.flip.accnos


mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.align, count=./outFiles/BSC16s.trim.contigs.good.count_table,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	0	0	0	0	1	1
2.5%-tile:	13862	23444	253	0	4	11600
25%-tile:	13862	23444	253	0	4	115996
Median: 	13862	23444	253	0	5	231991
75%-tile:	13862	23444	253	0	5	347986
97.5%-tile:	13862	23444	254	0	7	452381
Maximum:	26101	26105	277	0	22	463980
Mean:	13889.4	23407.5	251.503	0	4.72146
# of unique seqs:	420967
total # of seqs:	463980

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.summary

It took 78 secs to summarize 463980 sequences.

mothur > screen.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.align, count=./outFiles/BSC16s.trim.contigs.good.count_table, summary=./outFiles/BSC16s.trim.contigs.good.unique.summary, start=13862, end=23444, maxhomop=8,processors=10)

Using 10 processors.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.summary
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.align
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.bad.accnos
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.good.count_table


It took 180 secs to screen 420967 sequences.

mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.align, count=./outFiles/BSC16s.trim.contigs.good.good.count_table,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	13836	23444	239	0	3	1
2.5%-tile:	13862	23444	253	0	4	11490
25%-tile:	13862	23444	253	0	4	114900
Median: 	13862	23444	253	0	5	229800
75%-tile:	13862	23444	253	0	5	344699
97.5%-tile:	13862	23444	254	0	7	448109
Maximum:	13862	25358	276	0	8	459598
Mean:	13861.9	23444	253.148	0	4.73701
# of unique seqs:	416786
total # of seqs:	459598

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.summary

It took 76 secs to summarize 459598 sequences.

mothur > filter.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.align, vertical=T, trump=.,processors=10)

Using 10 processors.
Creating Filter... 


Running Filter... 



Length of filtered alignment: 550
Number of columns removed: 49450
Length of the original alignment: 50000
Number of sequences used to construct filter: 416786

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.filter
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.fasta


mothur > unique.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.fasta, count=./outFiles/BSC16s.trim.contigs.good.good.count_table)
416786	178747

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta


mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_02:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_03:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_04:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_05:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_06:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_07:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_08:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_09:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_01:

mothur > pre.cluster(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.count_table, diffs=2,processors=10)

Using 10 processors.

Processing group B8_10:
16742	4945	11797
Total number of sequences before pre.cluster was 16742.
pre.cluster removed 11797 sequences.

It took 22 secs to cluster 16742 sequences.
18961	7835	11126
Total number of sequences before pre.cluster was 18961.
pre.cluster removed 11126 sequences.

It took 45 secs to cluster 18961 sequences.
22617	8411	14206
Total number of sequences before pre.cluster was 22617.
pre.cluster removed 14206 sequences.

It took 54 secs to cluster 22617 sequences.
24292	9379	14913
Total number of sequences before pre.cluster was 24292.
pre.cluster removed 14913 sequences.

It took 65 secs to cluster 24292 sequences.
22654	9942	12712
Total number of sequences before pre.cluster was 22654.
pre.cluster removed 12712 sequences.

It took 70 secs to cluster 22654 sequences.
24277	11598	12679
Total number of sequences before pre.cluster was 24277.
pre.cluster removed 12679 sequences.

It took 81 secs to cluster 24277 sequences.
23368	10986	12382
Total number of sequences before pre.cluster was 23368.
pre.cluster removed 12382 sequences.

It took 83 secs to cluster 23368 sequences.
24885	11577	13308
Total number of sequences before pre.cluster was 24885.
pre.cluster removed 13308 sequences.

It took 88 secs to cluster 24885 sequences.
26341	13166	13175
Total number of sequences before pre.cluster was 26341.
pre.cluster removed 13175 sequences.

It took 102 secs to cluster 26341 sequences.
26106	12953	13153
Total number of sequences before pre.cluster was 26106.
pre.cluster removed 13153 sequences.

It took 105 secs to cluster 26106 sequences.
It took 124 secs to run pre.cluster.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.count_table
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_01.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_02.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_03.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_04.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_05.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_06.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_07.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_08.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_09.map
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.B8_10.map

**Lína 27**

mothur > chimera.uchime(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.count_table, dereplicate=t,processors=10)

Using 10 processors.

uchime by Robert C. Edgar
http://drive5.com/uchime
This code is donated to the public domain.

Checking sequences from ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta ...

It took 527 secs to check 4945 sequences from group B8_10.

It took 1146 secs to check 7835 sequences from group B8_09.

It took 1353 secs to check 8411 sequences from group B8_03.

It took 1548 secs to check 9379 sequences from group B8_05.

It took 1774 secs to check 9942 sequences from group B8_08.

It took 2076 secs to check 10986 sequences from group B8_02.

It took 2290 secs to check 11598 sequences from group B8_01.

It took 2329 secs to check 11577 sequences from group B8_07.

It took 2662 secs to check 13166 sequences from group B8_06.

It took 2704 secs to check 12953 sequences from group B8_04.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.chimeras
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.accnos

**Lína 28**

### <span style="color:red">*Athuga warning*</span>

mothur > remove.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta, accnos=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.accnos)
[WARNING]: This command can take a namefile and you did not provide one. The current namefile is /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.names which seems to match ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.fasta.
Removed 27597 sequences from your fasta file.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta

**Lína 29**

mothur > summary.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table,processors=10)

Using 10 processors.

		Start	End	NBases	Ambigs	Polymer	NumSeqs
Minimum:	1	550	239	0	3	1
2.5%-tile:	1	550	253	0	4	10720
25%-tile:	1	550	253	0	4	107196
Median: 	1	550	253	0	5	214392
75%-tile:	1	550	253	0	5	321587
97.5%-tile:	1	550	254	0	7	418063
Maximum:	1	550	273	0	8	428782
Mean:	1	550	253.1	0	4.71171
# of unique seqs:	51374
total # of seqs:	428782

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.summary

It took 2 secs to summarize 428782 sequences.

**Lína 30**

### <span style="color:red">*Athuga warning*</span>

mothur > classify.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, reference=./trainset/trainset14_032015.pds.fasta, taxonomy=./trainset/trainset14_032015.pds.tax, cutoff=80,processors=10)

Using 10 processors.
Reading template taxonomy...     DONE.
Reading template probabilities...     DONE.
It took 10 seconds get probabilities. 
Classifying sequences from ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta ...
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17071_2863 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_28179_16163 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_12761_24470 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24722_20398 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_18709_7583 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_19715_7001 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20164_15476 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_23455_19701 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_9966_22065 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19507_18928 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17430_4580 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_18477_1849 could not be classified. You can use the remove.lineage command with taxon=unknown; to remove such sequences.

It took 133 secs to classify 51374 sequences.


It took 3 secs to create the summary file for 51374 sequences.


Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.taxonomy
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.tax.summary

**Lína 31**

mothur > remove.lineage(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.taxonomy, taxon=Chloroplast-Mitochondria-unknown-Archaea-Eukaryota)

[NOTE]: The count file should contain only unique names, so mothur assumes your fasta, list and taxonomy files also contain only uniques.


Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pick.fasta
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.pick.count_table

**Lína 58**

mothur > cluster.split(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, splitmethod=classify, taxlevel=4, cutoff=0.15,processors=10)

Using 10 processors.
Splitting the file...
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.dist

It took 9 seconds to calculate the distances for 2216 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist

It took 3 seconds to calculate the distances for 1182 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist

It took 23 seconds to calculate the distances for 5630 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.dist

It took 1 seconds to calculate the distances for 613 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.dist

It took 2 seconds to calculate the distances for 775 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.dist

It took 1 seconds to calculate the distances for 199 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.dist

It took 1 seconds to calculate the distances for 191 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist

It took 69 seconds to calculate the distances for 11078 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.dist

It took 5 seconds to calculate the distances for 2037 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist

It took 3 seconds to calculate the distances for 954 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.dist

It took 12 seconds to calculate the distances for 3248 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.dist

It took 4 seconds to calculate the distances for 1970 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.dist

It took 4 seconds to calculate the distances for 1670 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.dist

It took 2 seconds to calculate the distances for 652 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.dist

It took 2 seconds to calculate the distances for 579 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.dist

It took 2 seconds to calculate the distances for 956 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.dist

It took 1 seconds to calculate the distances for 363 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist

It took 2 seconds to calculate the distances for 537 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.dist

It took 2 seconds to calculate the distances for 827 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.dist

It took 2 seconds to calculate the distances for 587 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.dist

It took 2 seconds to calculate the distances for 1287 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.dist

It took 1 seconds to calculate the distances for 259 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.dist

It took 2 seconds to calculate the distances for 623 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.dist

It took 1 seconds to calculate the distances for 406 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.dist

It took 2 seconds to calculate the distances for 419 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.dist

It took 2 seconds to calculate the distances for 539 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.dist

It took 2 seconds to calculate the distances for 1300 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.dist

It took 2 seconds to calculate the distances for 752 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.dist

It took 1 seconds to calculate the distances for 519 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.dist

It took 1 seconds to calculate the distances for 364 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist

It took 1 seconds to calculate the distances for 266 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.dist

It took 2 seconds to calculate the distances for 382 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.dist

It took 2 seconds to calculate the distances for 159 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.dist

It took 2 seconds to calculate the distances for 1036 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.dist

It took 1 seconds to calculate the distances for 259 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.dist

It took 2 seconds to calculate the distances for 119 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.dist

It took 1 seconds to calculate the distances for 456 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.dist

It took 2 seconds to calculate the distances for 38 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.dist

It took 1 seconds to calculate the distances for 17 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.dist

It took 2 seconds to calculate the distances for 578 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.dist

It took 2 seconds to calculate the distances for 11 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.dist

It took 1 seconds to calculate the distances for 98 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist

It took 2 seconds to calculate the distances for 89 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist

It took 1 seconds to calculate the distances for 184 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.dist

It took 2 seconds to calculate the distances for 98 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.dist

It took 1 seconds to calculate the distances for 77 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.dist

It took 2 seconds to calculate the distances for 337 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.dist

It took 1 seconds to calculate the distances for 239 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.dist

It took 2 seconds to calculate the distances for 626 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.dist

It took 2 seconds to calculate the distances for 7 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist

It took 1 seconds to calculate the distances for 173 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist

It took 2 seconds to calculate the distances for 177 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.dist

It took 1 seconds to calculate the distances for 43 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.dist

It took 1 seconds to calculate the distances for 239 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.dist

It took 2 seconds to calculate the distances for 217 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.dist

It took 1 seconds to calculate the distances for 54 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.dist

It took 2 seconds to calculate the distances for 198 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.dist

It took 1 seconds to calculate the distances for 26 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.dist

It took 1 seconds to calculate the distances for 228 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist

It took 2 seconds to calculate the distances for 47 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist

It took 1 seconds to calculate the distances for 62 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.dist

It took 2 seconds to calculate the distances for 40 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist

It took 1 seconds to calculate the distances for 33 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist

It took 2 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.dist

It took 1 seconds to calculate the distances for 19 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.dist

It took 2 seconds to calculate the distances for 74 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.dist

It took 1 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.dist

It took 2 seconds to calculate the distances for 50 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist

It took 2 seconds to calculate the distances for 23 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.dist

It took 1 seconds to calculate the distances for 11 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.dist

It took 1 seconds to calculate the distances for 11 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.dist

It took 2 seconds to calculate the distances for 58 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.dist

It took 1 seconds to calculate the distances for 54 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.dist

It took 2 seconds to calculate the distances for 17 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.dist

It took 1 seconds to calculate the distances for 30 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist

It took 2 seconds to calculate the distances for 22 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.dist

It took 1 seconds to calculate the distances for 23 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist

It took 2 seconds to calculate the distances for 5 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.dist

It took 1 seconds to calculate the distances for 6 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist

It took 2 seconds to calculate the distances for 14 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.dist

It took 1 seconds to calculate the distances for 5 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.dist

It took 1 seconds to calculate the distances for 4 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.dist

It took 1 seconds to calculate the distances for 9 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.dist

It took 1 seconds to calculate the distances for 4 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.dist

It took 1 seconds to calculate the distances for 12 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.dist

It took 1 seconds to calculate the distances for 3 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.dist

It took 0 seconds to calculate the distances for 3 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.dist

It took 2 seconds to calculate the distances for 7 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.dist

It took 0 seconds to calculate the distances for 4 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.dist

It took 2 seconds to calculate the distances for 5 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

It took 0 seconds to calculate the distances for 2 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.dist

It took 0 seconds to calculate the distances for 3 sequences.
/******************************************/
Running command: dist.seqs(fasta=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.temp, processors=10, cutoff=0.15, outputdir=/data/data02/asta/testrun/outFiles/)

Using 10 processors.
/******************************************/

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.dist

It took 1 seconds to calculate the distances for 3 sequences.
It took 307 seconds to split the distance file.
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.94.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.91.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.85.dist
Cutoff was 0.15 changed cutoff to 0.15

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.57.dist
Cutoff was 0.15 changed cutoff to 0.14

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.42.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.6.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.87.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.63.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.40.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.68.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.31.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.65.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.50.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.88.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.89.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.69.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.77.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.71.dist
Cutoff was 0.15 changed cutoff to 0.14

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.51.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.34.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.27.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.23.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.76.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.90.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.70.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.75.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.72.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.dist
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.24.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.54.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.82.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.83.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.74.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.52.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.35.dist
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.36.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.21.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.53.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.84.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.49.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.59.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.55.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.32.dist
Cutoff was 0.15 changed cutoff to 0.14

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.29.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.95.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.66.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.64.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.67.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.41.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.47.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.58.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.28.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.17.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.30.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.43.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.60.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.62.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.80.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.78.dist
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.93.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.dist
Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.92.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.81.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.73.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.61.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.44.dist
Cutoff was 0.15 changed cutoff to 0.1

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.5.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.33.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.16.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.46.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.14.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.18.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.4.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.3.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.19.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.39.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.22.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.48.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.dist
Cutoff was 0.15 changed cutoff to 0.12

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.9.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.20.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.15.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.1.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.26.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.dist
Cutoff was 0.15 changed cutoff to 0.07

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.11.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.25.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.12.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.13.dist
Cutoff was 0.15 changed cutoff to 0.08

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.56.dist
Cutoff was 0.15 changed cutoff to 0.09

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.dist
Cutoff was 0.15 changed cutoff to 0.07
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.45.dist
Cutoff was 0.15 changed cutoff to 0.11

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.37.dist
Cutoff was 0.15 changed cutoff to 0.14

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.38.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.79.dist

Reading /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.86.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.8.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.7.dist
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.0.dist
Cutoff was 0.15 changed cutoff to 0.07
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.10.dist
Cutoff was 0.15 changed cutoff to 0.07
Cutoff was 0.15 changed cutoff to 0.06
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************

Clustering /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.fasta.2.dist
Cutoff was 0.15 changed cutoff to 0.07
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.06
Cutoff was 0.15 changed cutoff to 0.07
Cutoff was 0.15 changed cutoff to 0.05

Cutoff was 0.15 changed cutoff to 0.05
It took 107 seconds to cluster
Merging the clustered files...
It took 9 seconds to merge.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list

**Lína 60**

mothur > make.shared(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, label=0.03)
0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.shared

**Lína 61**

### <span style="color:red">*Athuga warnings*</span>

mothur > classify.otu(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, label=0.03)
0.03	13220
[WARNING]: M03555_131_000000000-ANG5J_1_2105_9329_6374 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_25401_8662 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_5143_6780 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_22316_3732 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_13798_6237 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_16754_2477 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_21393_12761 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_19396_4735 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_2605_17868 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_6989_13179 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_12392_14481 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_4643_11745 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_19234_3850 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_28720_12099 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_27806_10180 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_16500_2671 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_16071_8329 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_6158_15159 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_26033_10853 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_18540_4616 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_27093_9146 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_11749_14081 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_19951_12662 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_19561_25035 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7983_19217 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_4917_15961 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_20030_17631 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_19853_5159 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_4901_6569 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_5376_16839 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_16407_24969 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_10148_7616 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_28659_12689 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_14896_8334 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_15545_3766 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_18034_4874 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_8072_21556 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_10059_6971 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21838_17154 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_27555_14671 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_19755_13903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_24906_14601 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_23661_7326 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22159_12412 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_23832_7409 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_19182_20362 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_19656_2411 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_17607_14606 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24339_20797 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_17113_7903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_19825_3272 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_19147_26979 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21930_17444 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_10136_13238 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_20868_23902 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22328_12605 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_6782_9449 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_3909_20213 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_17228_10423 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_7264_9069 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_10615_6546 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_24051_8527 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_25132_10504 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_12528_10506 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_7437_17164 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_11253_20223 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_4002_16689 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_16607_4174 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_7987_18192 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_4091_10729 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_10192_24148 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_6518_11709 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_21160_5509 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_3984_14753 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_16887_3700 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_15429_24348 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_9084_13270 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_23058_14364 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_5388_8077 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_18696_25524 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_11689_21000 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_14314_1502 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_9032_23223 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_9222_25592 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_13662_2696 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_22195_26368 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_24871_6721 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_19816_10175 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_22177_18915 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_23261_19339 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_3362_19192 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_12285_15886 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_11657_13078 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_12210_23773 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_19802_15143 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_3331_10466 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_4469_10978 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_22374_5248 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_11898_12075 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_5810_20950 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_23565_9691 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_21788_14200 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_8316_7959 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_12888_7866 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_7076_9481 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_23763_3951 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_4906_13512 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_23270_7298 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_3924_11644 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_15270_18946 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27979_17707 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_24564_25622 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_20899_8562 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_22514_13582 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_18477_1849 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22727_18976 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_6023_23425 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_17397_2899 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_19873_6121 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_18143_6650 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_18497_15507 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_24477_8022 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_24217_6085 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_13031_7200 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_25130_22082 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_26334_9401 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_15888_9394 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_28413_15780 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_5545_10474 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_14812_21836 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_24258_19550 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_22887_6534 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_7388_4583 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24274_21650 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_23019_9232 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_27056_21548 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_11906_9914 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_19564_17256 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_16991_25039 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_26005_19517 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_2316_17092 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_9528_26952 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_26152_11585 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_15780_16235 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_19881_15100 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_15681_25818 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_5122_15160 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_3191_11819 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_22612_9491 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_21062_24453 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_5076_14343 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_10085_6269 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_18287_22639 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_14249_14060 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_6558_11400 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_13185_18405 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_9262_3221 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_28876_10577 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_23219_17216 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_4579_21710 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12236_18094 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_13830_14089 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_10783_11815 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_12086_9077 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25884_23471 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_20747_11441 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_23630_10774 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_16140_8954 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_11624_21661 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_13828_18469 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_12787_25097 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_11151_18224 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_4868_14766 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_27795_14116 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_20437_19049 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_5522_8680 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_19041_23469 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_7896_25038 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_16190_7707 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_26995_18635 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_10126_7106 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_10372_5873 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_10733_15932 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_26386_14772 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_6655_15851 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_14918_28357 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_11910_16411 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_8389_9935 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_15602_2464 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17762_11668 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_25722_9265 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_23455_19701 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_19691_12086 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_14842_5145 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_11354_12611 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_5187_11707 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_28930_19726 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_8562_17650 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_12231_19428 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_14869_11590 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_14694_11697 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_21971_26802 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_23573_5169 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_13819_7145 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20472_9933 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_13628_13841 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_22505_15112 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_13716_25057 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_6719_25546 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_6364_6020 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_14359_6429 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_26760_20175 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_23333_7920 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_17837_22329 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_5570_8935 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12307_9295 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_5729_15479 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_21224_21170 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_10824_24428 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_23429_9629 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_10500_10570 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27450_10406 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_27097_18920 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_10816_11892 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_15108_11908 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_9893_16269 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_28688_11522 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_13983_4064 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_17317_8081 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_21998_24231 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_5111_17968 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_7436_12651 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_28344_20195 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_17866_5796 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_15668_14419 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_9414_18469 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_11160_5836 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_4400_10778 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_4951_15044 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_26136_15754 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_19400_5766 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_18864_5980 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_21305_7720 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_23343_11886 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_12698_5946 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_8914_24899 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_23086_8912 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_13584_10075 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_20420_21792 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_19186_27640 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_10771_17079 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_25085_15575 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17071_2863 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15207_2597 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20465_15956 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_13735_3398 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_22060_13282 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_11266_21510 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27043_19139 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_24595_7117 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_4496_11463 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_12336_11586 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_17826_8227 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_19438_12540 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_20115_4161 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_25606_17268 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_12571_6806 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_12594_7351 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12728_9077 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_24490_11115 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_6624_17473 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12456_20601 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_25102_12362 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_23934_6401 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_15876_16794 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_26308_7400 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_21578_15823 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_16448_17914 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_11442_7339 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_20811_5307 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_7419_24367 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_3111_20479 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_4690_9001 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_11824_9519 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_7309_12815 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_9723_21709 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_19132_20028 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_17487_23411 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_6174_15577 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_23518_13565 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_20688_2652 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_4107_21030 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_27225_16023 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_19728_8926 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_5670_17507 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_14914_5381 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_19631_5375 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_25348_24891 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_13725_13889 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_11329_26337 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_19037_20702 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_23663_19153 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_5441_18464 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_11770_2562 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_29084_12632 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_14246_16104 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_4650_13874 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_28439_17515 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_8707_9429 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_22130_27567 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_12809_7814 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_22764_12125 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_9573_18213 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_12686_7446 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_14386_19884 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_16922_7209 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_20595_13691 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_8154_22049 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_19838_18725 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_9006_17629 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_19544_27710 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14765_22583 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_25279_8175 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_27380_8203 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_4005_10371 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_27165_13446 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_20681_17689 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_24180_6589 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_26341_9133 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_16591_13670 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_9574_17423 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_23773_26297 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_23101_14492 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_10012_6762 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_23879_10583 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_28179_16163 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_12683_19300 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_11872_25596 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_17554_11167 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_21885_11207 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_21677_5523 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_18068_15839 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_24011_21089 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_21789_6503 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_17421_10327 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_22229_11151 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_24003_12347 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_8756_14955 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_17876_17506 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_29567_13394 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_5300_20108 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_19793_20414 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_24358_7275 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_8011_8321 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_10243_12300 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_26307_14274 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_13562_16738 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_7622_18253 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_5565_18847 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_21045_21841 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_6331_18657 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_13160_21725 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_27282_18285 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_14391_6430 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15177_21810 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_24568_24953 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_7455_14310 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_14248_18887 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_10535_26297 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_6650_6715 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_9501_20158 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_5259_19167 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_21110_9952 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_25467_13217 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_20852_6724 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_2683_11620 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_13230_14902 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_15226_21458 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_2723_15872 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20659_14680 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_10538_22818 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_15863_2977 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_13435_11302 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_6157_22183 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_12571_2371 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_21285_2602 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10070_12812 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_13610_2308 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_12882_2634 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_28163_10061 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_14891_11759 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_17686_15997 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_28342_16367 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_7120_12766 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_11091_13705 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_6383_20674 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_20681_20476 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7935_23071 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_4143_8244 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_14547_1778 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_13032_9335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_28768_11714 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_13616_11888 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_19326_17347 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_20284_25890 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_20056_27347 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_5229_6731 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_15648_7340 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_28866_17644 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_8799_22248 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_5701_13202 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_25782_17796 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_25209_10710 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_29481_12989 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_26117_19868 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_13630_21513 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_24551_25023 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_15538_3183 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_12620_3725 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_16450_5798 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_19715_7001 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_21749_17388 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_23285_17889 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_17175_25793 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_19013_6107 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_21616_6651 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_22569_6831 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_15268_10149 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_20121_14030 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_9183_21792 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_7450_22938 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_7747_23083 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_11069_27785 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_3461_21862 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_22615_14835 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_24100_12641 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_9966_22065 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_24530_21992 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_26895_10841 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_8953_6515 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_8638_25643 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_21035_4995 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_24122_24319 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_18646_19743 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_4033_11334 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_13461_22817 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27967_22002 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_5939_21412 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_25780_18726 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_8957_18109 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_25657_24882 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_12346_20528 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21427_18894 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_25023_15690 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_2838_20382 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_11603_17910 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_24841_6061 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_5808_20097 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_27090_7263 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_15402_7024 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_11208_24832 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_23454_24353 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_11479_8080 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14197_3940 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_10812_12978 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_25419_15086 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_20365_13233 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_10069_12296 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_12154_13481 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_3006_13320 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_16146_12590 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_19078_7676 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_14997_7518 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_24810_18209 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_19106_2173 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_8000_17167 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_22224_22062 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_16474_15384 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_15432_21996 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_19722_22444 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_7899_5865 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_27914_20850 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_9285_25837 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_6995_9403 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_26804_13244 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_2613_17396 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_7177_6104 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21039_8030 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21768_10980 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_7306_25955 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_2978_15841 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_19799_16783 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_19886_19416 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_25265_21963 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21748_26470 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17854_7336 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_18464_8558 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_24041_15953 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_29080_16480 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_23344_9801 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_26454_13783 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_14213_15446 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_28088_16859 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_13023_19599 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_5624_24024 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_12965_5700 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_20931_14662 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_8635_4065 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_24989_9445 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_21124_20180 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_18471_1662 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_16597_5097 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_8057_11509 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_26697_12719 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_21595_27093 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_15808_14178 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_10204_14755 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_26080_19976 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_10421_16570 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_28093_21642 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_12761_24470 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_21786_26014 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_24592_21670 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_6670_13620 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_10218_14424 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_4870_18696 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_22001_22552 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_17661_7585 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_15013_9934 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_5711_18686 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_24864_15158 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_8997_4611 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_25977_8579 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_5885_12527 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_7955_22989 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_21196_23657 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17430_4580 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_22295_10552 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_23640_10903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_4546_10669 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_5635_12360 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_24034_15864 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_25398_20304 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_6035_8821 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_15616_10335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_9605_21149 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_11070_6787 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_20972_10488 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_16973_15015 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_22635_16661 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_16263_18534 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_28415_21229 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_24046_26035 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_21907_9371 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_27353_19699 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_20310_7610 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_4838_12137 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_22699_13655 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_14896_14972 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_13149_21530 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_17450_23038 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_4672_13288 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_16441_13587 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_23902_23922 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_14027_4322 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_21589_4715 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_4519_11836 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_15759_12080 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_10020_26871 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_28738_15130 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_21744_7812 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_12661_6752 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_26699_17677 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_6607_18355 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_16771_19288 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_16981_13782 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_20050_21030 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_16276_22112 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_5110_7602 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_22797_8579 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_6731_11014 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_9604_12015 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_17879_21260 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_25585_23901 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_8061_5651 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_18609_5744 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_14356_7335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_27333_11209 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_7952_4963 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_25094_6132 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_26334_20028 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_16414_15659 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_24287_17700 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_19578_6003 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_8972_8903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_2174_13157 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_11407_19854 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14287_19964 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_12338_25444 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_7072_4746 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_17723_19053 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_20067_27789 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_8310_13285 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_16819_14718 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_20387_21070 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_21304_13178 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_16365_20634 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_18529_2455 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_21221_16481 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_19453_4077 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_8587_10579 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_17157_6660 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_24339_8816 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_24541_20601 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_10868_12492 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_24186_7401 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7322_8000 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_22895_23167 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_24818_15580 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_9831_23489 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_17437_10856 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_15982_15865 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_6012_17061 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17050_14532 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_4858_21725 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_13888_2572 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_13989_2263 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_8551_4335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_23265_14829 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_20391_22923 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_28125_14140 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_17792_19087 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_2487_19278 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_19260_24117 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_11667_25784 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_16611_26499 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19947_4237 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_4049_11320 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_16633_15497 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_6001_18128 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_11630_26896 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_19003_10673 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10393_17165 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_9741_21172 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_19918_23100 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_7411_24544 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_19017_3702 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_7078_11673 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_5583_13712 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_2565_13935 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_5627_17132 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_18656_17457 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_25699_18018 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_4189_14456 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_22231_20580 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_13651_26430 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_14775_4305 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_24583_9439 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_3490_13057 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_6291_19264 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_8202_25067 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_15698_10360 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_3860_9335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_27221_11065 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_4868_18269 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_14276_7499 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_3113_11601 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_22490_12150 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_2878_12491 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_13679_13029 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_4484_17323 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_20470_25053 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_23175_26817 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_12590_2524 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_17546_7895 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_16469_11420 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_12987_17084 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_11316_19378 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_20632_26379 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_18342_5893 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_19426_6835 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_13876_8129 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_15655_9875 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_21766_19500 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19981_7061 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_26732_9336 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_16983_11610 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_21577_14491 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_6092_17116 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_3125_17561 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_26521_19020 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_17441_3458 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_23759_4627 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_29192_15801 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_11636_16068 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_20742_6577 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_25053_13294 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_11840_14784 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_5653_14215 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_22687_10062 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_22363_18921 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_14455_3811 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15539_4237 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_8533_13171 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_6729_17570 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15804_18359 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_10293_18673 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_24130_18450 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_8859_13346 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_18804_3434 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_19457_6468 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_3933_10511 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_4326_12847 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_7297_15266 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_14528_22431 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_16797_2935 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_18617_7362 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_25929_14147 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_12906_15822 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_18645_17726 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_5673_19602 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_4285_19779 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_18379_20290 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_7156_22688 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_21574_25309 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_13743_6326 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_13289_28420 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_10728_11459 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_7976_15499 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_11262_16897 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_17752_20487 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_19740_4106 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_9466_5476 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_9517_14423 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_17984_19413 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_12254_20158 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_12004_21624 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_7509_25231 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_9165_4639 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_7801_9311 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_25795_15154 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_27105_15741 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_9617_19771 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_13945_23740 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_14382_3314 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_4789_21621 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27380_11322 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_8622_13161 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_25077_13465 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_15533_16630 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_15948_17143 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_25896_24279 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_17659_24586 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_15536_27134 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_9329_27361 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_11947_4983 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_15400_5986 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_8646_25194 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_17065_1906 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_22278_7884 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_22507_15392 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_20919_20370 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_19026_1749 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_19412_2394 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_15833_2403 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_5853_9485 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_4106_20737 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_17962_8764 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_20023_14405 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_6479_20148 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_19205_22496 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_26392_23070 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_17177_8423 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_18139_5951 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_21009_13712 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_18514_13312 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_9845_8838 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_24973_12713 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_20895_23056 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25632_11906 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_2089_14211 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_15006_10101 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_18757_20846 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_15627_23369 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_2530_14754 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_21021_11550 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_21597_14721 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_5819_15460 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_27146_9376 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_23947_20920 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_8488_26323 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_24913_25878 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_16101_24967 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_10886_24657 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_17903_11018 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_11951_24626 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_10970_18449 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_4513_20802 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_21985_13659 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_29280_16054 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_23377_13290 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_9881_23367 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_24791_9276 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_19636_9502 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_28061_11067 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_16756_22719 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_16419_13761 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_6162_22324 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_8653_24850 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25023_21369 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_7612_17521 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_3314_8857 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_22084_17058 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_26560_16180 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_23911_14182 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24722_20398 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_18748_12305 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_17971_18083 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_9697_19236 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_2334_12431 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_26926_15409 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_15078_4192 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_23716_11033 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_9846_22332 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_22898_8216 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_27360_13452 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_5781_16549 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15151_1950 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_5772_10634 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_11878_16691 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_20493_24063 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_23522_3783 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_25768_9746 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_19079_14597 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_12868_18781 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_28343_20039 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_20620_10502 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_24572_19721 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_26248_19781 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_10064_28088 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_8667_25943 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_19046_13331 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_7543_22324 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23335_16963 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_18830_14440 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_26904_12158 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_19041_11047 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_22802_17789 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_18756_10703 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_13410_10335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_14590_13416 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_15321_12933 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_13491_23065 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_26053_10499 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_28065_12058 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_26286_17513 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_14183_16985 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_16569_13270 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_16153_22157 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_28304_9486 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_15302_5935 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_24089_15232 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_4452_17109 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_21996_16598 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_11193_13434 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_13943_6714 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_8239_9130 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_9986_5764 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_10687_12780 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_28379_9378 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_16421_23510 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_23729_21659 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_15864_18497 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_27927_20103 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_21005_12691 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_15459_19614 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_13298_12413 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_6195_22577 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_6406_17446 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_10566_14220 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_29453_16635 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_27126_8492 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_13172_3186 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_19066_24168 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_19895_18977 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_15008_7909 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_26428_10769 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_12212_27490 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_4454_22807 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_16908_23180 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_16636_12795 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_4822_14474 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_11132_17604 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15036_17358 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_5146_11205 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_20506_6931 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_23508_7398 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_6157_14162 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_13135_25142 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_10791_27016 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_16423_2690 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_17031_5480 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_22420_8635 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_10058_8957 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7121_11602 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_15506_23868 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_15743_14444 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7351_18355 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_25033_18663 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_15708_20589 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_7440_25161 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_13299_3702 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_24404_23047 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_16189_2839 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_20538_12464 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_19516_13511 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_17479_13654 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25772_15361 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_12648_6898 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_24775_24636 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_18829_2199 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_22049_10302 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_18017_15660 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_8600_17362 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_12560_19861 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_23376_22312 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_14965_4071 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_14465_14306 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_8348_15559 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_25202_15874 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_26195_16337 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_23627_18000 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_12934_18027 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_11415_18161 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_21068_21713 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_24791_21717 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_23259_4681 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_18709_7583 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_24565_10848 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_28319_12021 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_11784_13729 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_5183_15808 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_5750_15907 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_25902_16722 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_27941_18558 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_21300_20412 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_18560_24100 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_25982_7356 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_7721_10113 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_8011_11976 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_24866_13212 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_14788_16125 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22460_16996 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_27501_17975 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_18216_19097 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_15126_19789 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_10209_21858 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_10385_10707 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_14608_15039 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_11178_15079 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_12727_15685 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_7013_17545 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_21982_24856 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_13458_1950 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_17847_21608 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_14622_10683 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_7515_22077 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_20434_22857 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_19216_9238 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_6178_16101 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_19312_18646 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_26448_19616 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_24183_20307 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_17628_20991 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_17218_6842 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_5182_21698 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_11068_21982 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_11544_3674 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19040_4997 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_24089_10092 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_6502_10453 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17349_12995 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_7233_13435 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_22986_13693 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_6728_11116 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_6840_19137 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_18267_2088 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_26005_7712 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_20867_8345 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_24198_11160 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_2553_17765 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_14830_2130 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_2960_14018 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_3461_15602 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_8491_17675 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_17005_6214 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_10848_27593 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_21219_7487 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_20983_9111 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_14482_11647 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_3323_14292 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_6148_17446 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_8813_21458 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_12686_12057 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_9130_5658 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_15510_19253 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_6979_5577 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_26809_11177 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_28329_11661 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_26568_16434 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_22083_17053 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_12831_20159 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_16519_24043 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_23967_6584 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_15829_14052 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_21298_21917 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_26055_24218 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_20736_13779 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19700_18683 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_20444_21111 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_10312_22609 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_17942_5638 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_12145_5674 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_5930_17992 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_6813_19721 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_11282_2184 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_4810_8061 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_25106_5931 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_17864_8081 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27746_9831 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_13922_13166 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_26099_22057 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_13371_4810 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_3665_11101 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_24084_18150 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_2751_19722 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_21007_4893 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_23524_9306 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_21840_17308 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14528_3154 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_28168_20453 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_4330_23322 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_28008_21417 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_27208_13351 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_19657_7359 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_4398_16455 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_14843_10485 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_8944_9069 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_23530_6586 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_15155_5979 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_18478_4495 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_24144_23541 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_8755_8751 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_8186_20335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_24424_23143 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_10113_25334 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_20008_18879 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_22528_21096 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_2341_18814 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_28661_18723 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_24868_18215 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_19825_17183 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_12000_7321 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_21712_3194 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_9535_5720 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_11362_23264 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_27999_17085 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_22830_17655 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_27035_14647 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_15140_10734 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_23686_14218 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_13922_1967 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_9445_5111 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_22741_6807 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_14316_7879 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_18354_23210 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_12653_8251 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_2844_18214 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_14252_23185 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_21525_27936 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_7274_16771 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_11005_10047 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_12616_13958 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_14442_27270 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_26143_20083 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_22847_15051 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_18355_19543 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_13244_3332 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_4140_15125 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_27458_9617 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_21081_8369 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_9466_14065 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_12475_25195 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_15648_2923 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_2960_10423 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_21286_14013 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2104_8489_15653 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_5192_13647 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_5951_17166 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_15905_24572 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_28490_20651 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_13449_14629 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_26300_13297 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_8673_13842 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_14376_10430 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_20693_20439 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_26457_9220 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_7634_7373 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_22291_7941 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_11872_14479 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2101_11140_7176 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_26147_13281 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_17595_13015 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_19279_3446 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_18396_12406 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_12780_10738 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_9001_8221 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10112_27808 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_24881_23873 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_21829_23522 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19507_18928 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2102_21308_24745 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_17683_6567 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23468_26086 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_7262_25604 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23262_23104 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_17071_13001 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_6716_10814 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_8541_8603 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_21741_4538 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_20763_3589 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_27495_16245 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_18263_11979 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_25787_10911 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_17365_9241 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_4403_10007 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_17701_3085 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_2696_14684 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_13848_23001 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_4705_23087 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_13500_23327 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_12193_25287 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23897_26030 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_13462_26405 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_14596_6448 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_2736_13053 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_17461_15725 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_5336_18657 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_14109_6587 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_4157_7818 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_25026_15903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_19408_13756 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_17877_11182 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_13158_24414 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_7563_17902 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_4269_18591 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_12218_18940 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_19589_21671 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_25173_23912 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_23647_24907 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_17384_2299 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_9097_3328 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_21359_3512 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_20100_4871 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_22866_16878 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_9373_21166 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_18803_22333 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_11502_24339 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_17143_1806 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_19473_2217 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_13417_4841 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_7746_5379 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_20106_10616 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_10613_10807 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_20360_11879 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_6314_13720 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_22430_16438 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_6275_16543 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_25951_21158 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_2355_19461 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_21721_19946 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_16310_20934 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_18138_26027 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_20316_2433 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_18989_2681 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_22772_8378 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_28449_11104 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_6507_13359 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_9157_14855 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_8309_15328 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_12048_4910 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_25543_16756 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_20361_17164 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27787_17458 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27292_19380 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27738_19468 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_5285_19594 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_24192_19994 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_26181_21103 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_8122_22037 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_8787_24555 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_21846_7179 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_4945_7451 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_10752_7790 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_12514_10163 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_6374_10452 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_6926_10672 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_13397_11166 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_8169_11903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_15828_12623 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_23070_13198 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_4340_18959 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_9475_20413 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_3967_15497 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_9680_15065 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_11932_22250 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10269_8879 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_3773_9058 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_26077_21630 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_27131_21435 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_10571_9728 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_26660_8627 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_24695_18493 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_23908_25025 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_19791_27777 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_13046_2800 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_11537_15498 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_19390_4371 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_7072_4627 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_24214_6261 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_13048_8107 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_5935_19876 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_27002_9097 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_16434_9531 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_16500_10127 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_22280_10360 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_7560_10432 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_13085_10555 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_17449_13335 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_9151_13455 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_25806_17129 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_19063_14206 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_4842_12363 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14179_12049 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_11100_11219 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14020_7697 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_21583_6755 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_22872_6337 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_16079_2418 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_20047_26005 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_22020_20156 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_5573_19180 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_18140_19109 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_5594_18621 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_18383_18179 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_15785_18131 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_20815_17057 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_21643_16603 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_17480_15243 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_23566_14338 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_27370_17748 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_23080_7406 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_20957_7341 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_10503_5255 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_6149_22123 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_12233_6477 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_13795_6177 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25463_5879 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_10886_3226 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_20537_7512 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_11323_9743 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_10544_10650 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_5980_12147 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_16664_16991 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_19307_17219 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_10205_18981 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12212_20860 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12450_22017 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_15510_1683 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_19860_2797 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_6099_5555 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_5113_8148 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_6866_10686 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_13525_13645 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_18960_20668 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_5036_21632 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_16234_22510 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_29486_16531 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_13520_5369 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_16339_7718 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_15923_17702 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_21502_17715 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_18421_18310 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_9123_20247 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_19750_19814 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_20438_23975 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_12650_3034 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_14859_6290 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_3048_10069 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_15012_10918 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_7365_15112 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_21956_15268 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_21781_16561 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_18304_15744 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_9526_16943 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_12516_25003 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_15870_27855 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20931_4385 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_12046_7191 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_14796_11761 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_15045_15392 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_12648_2958 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_14513_4073 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_13212_5978 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_25841_6806 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_3722_8565 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_23588_9698 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_15150_10894 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_7710_12059 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_4148_14649 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_27531_15582 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_19160_17803 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_22261_19652 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_24520_21962 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_10059_2952 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_9219_4448 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_5526_14758 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_20633_15104 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_23271_21541 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_17392_24669 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_5848_25229 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_12837_25435 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25229_9232 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_20469_6369 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_11837_6491 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_25139_8669 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_15340_8340 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_26291_9502 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_23551_10028 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_16115_10369 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_17961_9265 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_15019_16085 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_8504_19261 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_26184_8254 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_10539_19902 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_18577_21005 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_25672_21754 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_21277_27381 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_18461_3874 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_15855_5102 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_13448_7614 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_12566_7269 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_15106_6826 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_26248_15559 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_24617_15857 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_25572_18073 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_19366_18971 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_3959_21195 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_21765_26353 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_21150_5227 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_13068_5392 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_22260_9282 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_4231_10779 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_14089_12942 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_18996_14181 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_28655_15159 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_3549_15434 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_29202_16264 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_13386_16889 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_6334_5692 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_21272_24483 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_11870_17791 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_7883_23976 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23494_19409 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27831_19686 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_8527_20308 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_11205_20800 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_7987_21108 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_21854_21944 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23249_22544 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_21755_22879 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_10584_17884 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_15818_20698 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_25859_17939 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_11229_17267 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_27956_20423 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_24517_20632 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_23110_14638 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_27884_13688 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_14180_10493 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_15588_6492 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_8400_5772 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_12217_22217 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_17191_25731 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_23700_24102 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_15146_19481 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_7462_24627 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2110_23991_25745 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_2263_18026 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_7083_4316 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_22981_17571 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_18653_16052 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_15352_15749 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_15612_4742 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_21225_7293 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27078_17021 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_15393_7650 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_28471_14855 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_16757_5442 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_16686_6638 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_8555_7097 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_5121_7810 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_11313_7828 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27045_8157 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_24441_12473 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_12660_8524 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_4163_11969 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_9601_10497 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27934_8848 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_27628_9027 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_13309_9862 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_22268_11271 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_2797_11470 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_10884_11819 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_28098_12832 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_23580_14484 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_6188_15089 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_22902_16542 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_22736_13493 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_9335_13133 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_26810_10062 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_4454_19676 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_9921_19438 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_10851_24240 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_9754_18551 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_12360_8318 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_21869_22975 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_13535_20509 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_16009_22634 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_21104_17667 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_17344_14971 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_24787_12474 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_25472_11999 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_14086_8833 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_9344_7995 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1104_11431_4026 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_22465_21046 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_23346_21855 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_10568_19909 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_21481_19838 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_6882_19250 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_9791_20794 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_14704_14830 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_8213_13948 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1102_9682_12093 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1101_24343_16234 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_8609_16386 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_8496_12012 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_6903_7869 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_16582_16889 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_12189_24293 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2112_11166_24025 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_23960_20238 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_11282_17078 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1103_15986_15845 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_8553_22161 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_9105_12208 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_13740_7924 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1106_14728_1731 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_26443_12740 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1105_7653_11880 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2109_20592_27237 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_17632_9300 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_11690_4317 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_11661_7141 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_7831_22012 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_20164_15476 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_17608_21126 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_12929_1820 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_20812_18267 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_10153_14830 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_15983_19270 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_12848_28096 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_9374_26189 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1108_24929_23353 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_16363_11117 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_10283_15502 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_26000_11852 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_18917_8593 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_13544_5672 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1113_10640_18578 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_28778_15374 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_18681_10868 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1109_24851_9484 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1112_10456_24715 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_13381_13938 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_21961_13676 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_20802_24866 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_13253_24727 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2105_16371_7187 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1110_22315_26173 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_12635_9258 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2107_15949_19241 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2103_22892_7294 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_11035_23660 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2111_23914_15903 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2114_18510_9287 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2106_9825_25452 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_27301_12168 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_11270_9905 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2113_9096_6554 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_8808_17418 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_18337_12711 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_2108_23528_7980 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_11636_20943 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_2256_13458 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_15334_17900 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1111_23241_21186 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_14076_17624 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_13491_23856 is not in your taxonomy file.  I will not include it in the consensus.
[WARNING]: M03555_131_000000000-ANG5J_1_1114_17701_6852 is not in your taxonomy file.  I will not include it in the consensus.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.taxonomy
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.tax.summary

# 50.10 Phylotypes
**Lína 66**

### <span style="color:red">*Athuga warning*</span>

mothur > phylotype(taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy)
[WARNING]: This command can take a namefile and you did not provide one. The current namefile is /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.names which seems to match ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy.
1
2
3
4
5
6

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.sabund
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.rabund
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list


**Lína 67**

### <span style="color:red">*Athuga errors*</span>

mothur > make.shared(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, label=1)
[ERROR]: M03555_131_000000000-ANG5J_1_1101_10752_7790 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_10783_11815 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_10886_24657 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_11091_13705 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_11502_24339 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_11636_16068 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_11840_14784 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_11872_14479 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_12048_4910 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_12514_10163 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_13172_3186 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_13371_4810 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_13397_11166 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_13876_8129 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_14246_16104 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_15008_7909 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_15655_9875 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_15828_12623 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_17595_13015 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_18342_5893 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_18803_22333 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_19279_3446 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_19426_6835 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_20620_10502 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_21846_7179 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_22130_27567 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_22687_10062 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_23070_13198 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_23902_23922 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_23947_20920 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_24084_18150 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_24144_23541 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_24343_16234 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_24424_23143 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_25053_13294 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_25398_20304 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_25951_21158 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_26147_13281 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_27353_19699 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_2751_19722 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_29192_15801 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_3665_11101 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_4340_18959 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_4945_7451 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_5951_17166 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_6374_10452 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_6926_10672 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_7120_12766 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_8072_21556 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_8169_11903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_9373_21166 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1101_9475_20413 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_10113_25334 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_10613_10807 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_12000_7321 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_12154_13481 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_13149_21530 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_13160_21725 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_13417_4841 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_14027_4322 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_14386_19884 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_14704_14830 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_14896_14972 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_16310_20934 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_17143_1806 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_17450_23038 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_18138_26027 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_19473_2217 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_19825_17183 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_20106_10616 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_20310_7610 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_20360_11879 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_20742_6577 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_21589_4715 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_21712_3194 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_21721_19946 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_22430_16438 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_22528_21096 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_22699_13655 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_22764_12125 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_22866_16878 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_23270_7298 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_2341_18814 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_2355_19461 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_23640_10903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_23773_26297 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_24868_18215 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_28661_18723 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_4838_12137 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_5653_14215 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_6035_8821 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_6275_16543 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_6314_13720 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_6331_18657 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_7436_12651 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_7746_5379 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_8213_13948 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_8562_17650 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_9605_21149 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_9682_12093 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1102_9791_20794 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_10070_12812 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_10112_27808 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_10269_8879 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_10393_17165 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_10571_9728 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_11266_21510 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_11282_17078 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_12145_5674 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_12571_2371 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_13679_13029 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_14109_6587 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_14276_7499 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_15013_9934 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_15986_15845 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_16263_18534 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_17384_2299 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_17441_3458 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_17661_7585 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_17942_5638 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_18540_4616 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_19003_10673 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_19791_27777 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_19918_23100 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_20100_4871 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_20470_25053 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_21035_4995 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_21285_2602 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_21359_3512 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_22465_21046 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_22490_12150 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_22635_16661 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_23175_26817 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_23759_4627 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_23908_25025 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_23960_20238 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_24046_26035 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_24595_7117 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_25806_17129 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_27056_21548 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_27370_17748 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_28415_21229 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_2878_12491 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_3113_11601 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_3773_9058 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_4157_7818 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_4484_17323 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_4868_18269 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_5146_11205 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_5930_17992 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_6149_22123 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_6813_19721 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_7411_24544 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_7896_25038 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_8638_25643 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_9097_3328 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1103_9741_21172 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_10020_26871 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_10566_14220 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_10733_15932 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_11282_2184 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_11316_19378 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_11431_4026 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_12590_2524 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_12780_10738 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_12882_2634 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_12987_17084 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_13046_2800 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_13048_8107 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_13085_10555 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_13610_2308 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_13922_13166 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_14086_8833 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_14891_11759 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_15429_24348 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_15616_10335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_15759_12080 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_16009_22634 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_16434_9531 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_16469_11420 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_16500_10127 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_17157_6660 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_17344_14971 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_17449_13335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_17546_7895 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_17686_15997 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_17864_8081 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_18396_12406 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_19017_3702 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_19390_4371 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_20361_17164 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_20506_6931 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_20632_26379 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_21005_12691 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_21104_17667 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_21766_19500 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_21907_9371 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_22280_10360 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_23508_7398 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_24034_15864 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_24192_19994 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_24214_6261 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_24787_12474 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_25106_5931 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_25472_11999 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_25543_16756 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_26099_22057 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_26181_21103 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_26660_8627 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_26995_18635 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27002_9097 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27043_19139 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27292_19380 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27738_19468 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27746_9831 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27787_17458 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_27979_17707 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_28163_10061 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_28342_16367 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_28930_19726 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_4002_16689 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_4519_11836 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_4546_10669 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_5285_19594 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_5522_8680 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_5635_12360 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_7072_4627 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_7560_10432 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_8122_22037 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_8239_9130 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_8787_24555 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_8953_6515 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_9001_8221 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_9151_13455 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_9344_7995 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1104_9680_15065 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_10584_17884 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_10884_11819 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_11068_21982 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_11205_20800 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_11313_7828 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_11667_25784 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_11870_17791 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_12193_25287 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_12660_8524 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_13309_9862 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_13461_22817 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_13462_26405 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_13500_23327 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_13848_23001 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_14391_6430 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_15533_16630 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_15536_27134 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_15612_4742 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_15948_17143 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_16611_26499 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_16686_6638 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_16757_5442 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_16908_23180 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_17071_13001 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_17177_8423 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_17628_20991 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_17659_24586 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_17792_19087 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_17847_21608 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_18656_17457 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_19041_23469 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_19216_9238 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_19260_24117 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_19312_18646 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_20763_3589 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_21110_9952 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_21196_23657 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_21741_4538 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_21755_22879 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_21854_21944 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_22268_11271 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_22902_16542 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23249_22544 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23262_23104 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23335_16963 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23468_26086 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23494_19409 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23580_14484 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_23897_26030 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_24100_12641 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_24183_20307 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_2487_19278 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_25077_13465 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_25467_13217 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_2565_13935 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_25780_18726 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_25896_24279 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_25977_8579 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_26443_12740 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_26448_19616 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27045_8157 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27078_17021 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_2723_15872 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27380_11322 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27450_10406 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27628_9027 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27831_19686 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27934_8848 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_27967_22002 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_2797_11470 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_28098_12832 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_4454_22807 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_4579_21710 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_4705_23087 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_4789_21621 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_5121_7810 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_5182_21698 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_5583_13712 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_5627_17132 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_5885_12527 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_5939_21412 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_6178_16101 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_6188_15089 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_6716_10814 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_7078_11673 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_7083_4316 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_7262_25604 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_7653_11880 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_7955_22989 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_7987_21108 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_8527_20308 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_8541_8603 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_8555_7097 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_8622_13161 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_8957_18109 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_8997_4611 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1105_9329_27361 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_10312_22609 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_11132_17604 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_11544_3674 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_11630_26896 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_11947_4983 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_12218_18940 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_13158_24414 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_13435_11302 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_13740_7924 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_14596_6448 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_14728_1731 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_15400_5986 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_15602_2464 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_15863_2977 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_16633_15497 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_16636_12795 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_16983_11610 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_17349_12995 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_17430_4580 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_17683_6567 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_17762_11668 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_18646_19743 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19040_4997 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19507_18928 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19589_21671 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19700_18683 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19947_4237 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_19981_7061 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_20444_21111 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_21577_14491 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_21829_23522 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_22001_22552 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_22291_7941 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_22295_10552 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_22986_13693 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_23647_24907 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_24089_10092 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_24122_24319 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_24881_23873 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_25173_23912 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_26521_19020 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_26732_9336 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_26895_10841 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_2696_14684 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_2736_13053 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_3125_17561 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_4033_11334 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_4049_11320 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_4269_18591 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_4496_11463 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_4822_14474 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_4870_18696 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_5711_18686 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_6001_18128 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_6092_17116 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_6157_22183 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_6502_10453 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_7233_13435 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_7563_17902 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_8389_9935 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_8553_22161 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1106_9105_12208 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_10568_19909 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_10970_18449 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_11070_6787 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_11329_26337 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_11537_15498 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_12686_7446 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_12809_7814 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_12848_28096 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_14482_11647 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_14997_7518 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_15155_5979 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_16146_12590 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_16441_13587 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_16591_13670 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_16922_7209 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_16973_15015 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_17903_11018 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_18478_4495 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_18989_2681 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_19078_7676 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_19793_20414 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_20316_2433 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_20972_10488 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_20983_9111 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_21219_7487 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_21481_19838 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_22772_8378 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_23346_21855 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_23530_6586 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_23663_19153 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_24180_6589 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_24592_21670 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_24695_18493 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_24929_23353 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_26341_9133 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_28439_17515 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_28449_11104 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_28738_15130 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_3006_13320 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_3323_14292 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_3967_15497 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_4398_16455 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_4513_20802 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_4650_13874 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_4672_13288 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_5300_20108 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_5935_19876 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_6148_17446 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_6507_13359 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_6882_19250 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_6979_5577 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_8309_15328 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_8813_21458 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_8944_9069 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_9157_14855 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_9374_26189 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_9573_18213 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1108_9574_17423 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_10209_21858 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_11229_17267 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_12620_3725 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_14180_10493 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_14213_15446 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_15538_3183 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_15588_6492 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_16234_22510 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_16363_11117 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_16365_20634 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_16450_5798 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_17175_25793 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_17228_10423 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_17607_14606 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_18681_10868 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_18960_20668 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_19438_12540 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_19715_7001 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_20736_13779 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_20895_23056 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_21007_4893 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_21304_13178 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_21578_15823 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_21749_17388 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_23110_14638 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_23285_17889 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_23344_9801 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_24851_9484 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_25859_17939 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_26454_13783 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_27884_13688 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_28088_16859 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_28778_15374 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_29481_12989 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_4454_19676 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_5036_21632 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_5441_18464 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_8400_5772 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_9754_18551 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_9845_8838 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1109_9921_19438 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_10085_6269 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_10812_12978 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_11069_27785 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_11951_24626 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_12212_27490 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_12233_6477 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_13023_19599 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_13253_24727 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_13448_7614 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_13520_5369 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_13544_5672 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_13795_6177 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_14843_10485 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_15006_10101 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_15268_10149 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_15340_8340 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_15627_23369 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_16101_24967 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_16189_2839 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_16756_22719 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_17479_13654 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_17961_9265 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_18514_13312 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_18529_2455 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_18757_20846 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_18917_8593 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_19013_6107 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_19037_20702 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_19516_13511 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_20008_18879 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_20121_14030 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_20537_7512 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_20538_12464 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_2089_14211 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_21009_13712 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_21221_16481 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_21616_6651 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_22084_17058 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_22177_18915 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_22315_26173 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_22569_6831 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_22736_13493 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_24404_23047 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_24775_24636 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_24913_25878 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_24973_12713 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25023_21369 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25139_8669 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25229_9232 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_2530_14754 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25463_5879 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25632_11906 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25772_15361 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_25884_23471 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_26000_11852 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_26184_8254 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_26386_14772 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_26560_16180 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_26810_10062 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_3461_21862 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_5624_24024 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_6099_5555 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_6174_15577 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_7419_24367 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_7450_22938 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_7612_17521 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_7747_23083 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_8488_26323 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_9183_21792 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_9335_13133 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_9528_26952 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1110_9881_23367 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_10851_24240 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_11208_24832 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_11362_23264 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_11479_8080 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_11636_20943 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_12336_11586 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_12831_20159 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_13381_13938 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_15334_17900 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_16419_13761 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_16519_24043 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_17365_9241 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_17461_15725 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_17554_11167 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_17701_3085 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_17723_19053 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_17877_11182 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_18068_15839 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_18864_5980 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_19408_13756 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_19636_9502 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_20067_27789 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_21272_24483 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_21305_7720 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_21885_11207 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_21961_13676 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_22083_17053 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_2256_13458 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_23101_14492 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_23241_21186 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_23454_24353 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_23524_9306 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_24011_21089 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_25026_15903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_26568_16434 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_26809_11177 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_27035_14647 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_27146_9376 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_28061_11067 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_28329_11661 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_4403_10007 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_5111_17968 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_5336_18657 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_6162_22324 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_7072_4746 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_7883_23976 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1111_8653_24850 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_10069_12296 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_10456_24715 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_12360_8318 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_13630_21513 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_15140_10734 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_15146_19481 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_15352_15749 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_15393_7650 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_15402_7024 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_15829_14052 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_16448_17914 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_16819_14718 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_17191_25731 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_17421_10327 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_17826_8227 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_17876_17506 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_18653_16052 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_20365_13233 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_20387_21070 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_20595_13691 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_20681_17689 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_21225_7293 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_21298_21917 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_21595_27093 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_21789_6503 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_22229_11151 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_2263_18026 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_22830_17655 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_22981_17571 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_23686_14218 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_23911_14182 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_23967_6584 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_24003_12347 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_24441_12473 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_24551_25023 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_25279_8175 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_25419_15086 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_26055_24218 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_26117_19868 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_27165_13446 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_27282_18285 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_27380_8203 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_27999_17085 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_28168_20453 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_28471_14855 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_3314_8857 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_3909_20213 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_4005_10371 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_4163_11969 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_6334_5692 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_8310_13285 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_8756_14955 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_9006_17629 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_9535_5720 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1112_9601_10497 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_10218_14424 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_10243_12300 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_10503_5255 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_10640_18578 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_12686_12057 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_13535_20509 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_13562_16738 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_14896_8334 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_15785_18131 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_15983_19270 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_16414_15659 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_17480_15243 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_18140_19109 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_18383_18179 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_19544_27710 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_19657_7359 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_19838_18725 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_20047_26005 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_20815_17057 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_20957_7341 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_21045_21841 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_21643_16603 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_21869_22975 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_21985_13659 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_22020_20156 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_22195_26368 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_22615_14835 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_23080_7406 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_23566_14338 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_24287_17700 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_24358_7275 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_25348_24891 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_26307_14274 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_27208_13351 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_28008_21417 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_29280_16054 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_29567_13394 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_4330_23322 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_4901_6569 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_5565_18847 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_5573_19180 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_5594_18621 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_6670_13620 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_7622_18253 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_8011_8321 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_8154_22049 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1113_8707_9429 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_10012_6762 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_10848_27593 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_11100_11219 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_11407_19854 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_11770_2562 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_11872_25596 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_11932_22250 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_12338_25444 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_12683_19300 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_13491_23856 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14020_7697 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14076_17624 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14179_12049 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14197_3940 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14287_19964 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14528_3154 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_14765_22583 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_15510_19253 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_16079_2418 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_17701_6852 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_19063_14206 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_19578_6003 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_19631_5375 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_20802_24866 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_21583_6755 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_21677_5523 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_2174_13157 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_21840_17308 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_22872_6337 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_23019_9232 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_23377_13290 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_23879_10583 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_26077_21630 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_27131_21435 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_28179_16163 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_3111_20479 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_4842_12363 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_4868_14766 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_8972_8903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_1114_9130_5658 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_10421_16570 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_10687_12780 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_10816_11892 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_11140_7176 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_11415_18161 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_11442_7339 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_12761_24470 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_12934_18027 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_13032_9335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_13289_28420 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_13458_1950 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_13616_11888 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_13828_18469 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_14314_1502 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_14465_14306 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_15108_11908 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_15545_3766 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_15681_25818 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_15698_10360 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_15808_14178 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_19326_17347 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_19656_2411 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_19755_13903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_20056_27347 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_20284_25890 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_20693_20439 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_21068_21713 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_21786_26014 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_22797_8579 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_22898_8216 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_23627_18000 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_24274_21650 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_24339_20797 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_24722_20398 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_24791_21717 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_25085_15575 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_25202_15874 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_26195_16337 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_26334_9401 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_26697_12719 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_28093_21642 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_28379_9378 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_28768_11714 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_3191_11819 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_3331_10466 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_5110_7602 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_5122_15160 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_6383_20674 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_6518_11709 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_7264_9069 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_8057_11509 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_8348_15559 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_8673_13842 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2101_9893_16269 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_10615_6546 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_10728_11459 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_11160_5836 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_11193_13434 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_11262_16897 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_11784_13729 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_13651_26430 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_13943_6714 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_14316_7879 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_14965_4071 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_15459_19614 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_15648_7340 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_15888_9394 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_17752_20487 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_17971_18083 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_18354_23210 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_18560_24100 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_18709_7583 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_18748_12305 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_19853_5159 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_20688_2652 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_21160_5509 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_21300_20412 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_21308_24745 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_21996_16598 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_22231_20580 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_23259_4681 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_24565_10848 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_25902_16722 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_27221_11065 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_27941_18558 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_28319_12021 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_28866_17644 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_3860_9335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_4189_14456 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_4452_17109 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_5183_15808 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_5229_6731 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_5750_15907 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_7634_7373 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_7976_15499 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_8799_22248 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_9697_19236 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2102_9986_5764 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_11661_7141 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_12210_23773 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_12528_10506 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_12648_6898 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_12868_18781 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_13298_12413 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_13299_3702 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_14788_16125 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_15126_19789 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_16597_5097 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_16771_19288 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_16887_3700 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_18216_19097 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_18471_1662 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_19079_14597 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_19182_20362 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_19561_25035 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_19881_15100 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_20493_24063 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_21744_7812 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_22159_12412 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_22328_12605 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_22460_16996 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_22727_18976 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_22892_7294 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_23429_9629 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_23522_3783 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_23630_10774 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_24089_15232 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_24866_13212 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_24871_6721 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_25094_6132 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_25130_22082 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_25768_9746 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_25982_7356 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_26136_15754 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_26152_11585 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_26699_17677 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_27501_17975 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_27927_20103 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_28343_20039 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_4143_8244 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_6607_18355 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_6731_11014 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_6782_9449 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_7721_10113 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_7952_4963 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_8011_11976 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2103_9604_12015 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_10064_28088 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_10385_10707 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_10500_10570 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_11178_15079 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_12661_6752 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_12727_15685 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_13725_13889 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_14547_1778 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_14608_15039 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_15648_2923 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_15864_18497 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_16276_22112 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_16421_23510 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_16981_13782 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_18477_1849 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_19951_12662 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_20050_21030 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_20811_5307 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_21286_14013 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_21982_24856 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_22612_9491 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_23058_14364 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_23729_21659 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_23934_6401 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_24339_8816 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_24541_20601 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_24572_19721 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_25102_12362 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_26248_19781 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_28659_12689 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_2960_10423 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_3984_14753 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_4091_10729 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_4400_10778 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_5187_11707 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_7013_17545 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_8202_25067 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2104_8489_15653 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_10283_15502 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_10791_27016 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_10868_12492 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_11749_14081 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_11910_16411 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_12086_9077 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_12231_19428 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_12560_19861 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_12965_5700 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_13135_25142 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_13798_6237 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_15506_23868 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_15876_16794 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_16371_7187 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_16407_24969 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_16754_2477 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_17397_2899 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_17608_21126 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_17879_21260 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_18017_15660 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_18139_5951 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_18829_2199 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_19066_24168 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_19186_27640 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_19234_3850 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_19396_4735 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_19453_4077 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_19895_18977 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_20115_4161 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_20681_20476 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_20931_14662 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_21021_11550 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_21597_14721 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_22049_10302 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_22316_3732 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_23376_22312 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_23518_13565 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_23763_3951 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_25401_8662 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_25585_23901 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_2605_17868 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_26334_20028 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_26428_10769 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_27806_10180 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_29084_12632 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_4643_11745 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_5143_6780 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_5819_15460 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_6158_15159 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_7831_22012 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_8186_20335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_8587_10579 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_8600_17362 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_8755_8751 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2105_9329_6374 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_10058_8957 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_10148_7616 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_10192_24148 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_10771_17079 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_10824_24428 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_11253_20223 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_11898_12075 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_12285_15886 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_12392_14481 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_12475_25195 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_14356_7335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_14812_21836 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_15270_18946 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_15708_20589 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_15743_14444 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_15905_24572 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_16071_8329 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_16423_2690 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_16500_2671 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_17031_5480 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_17113_7903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_18034_4874 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_18609_5744 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_19400_5766 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_21124_20180 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_21224_21170 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_21393_12761 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_22374_5248 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_22420_8635 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_22895_23167 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_23832_7409 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_24186_7401 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_24791_9276 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_24989_9445 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_25033_18663 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_25606_17268 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_26308_7400 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_27126_8492 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_27333_11209 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_27795_14116 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_28720_12099 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_29453_16635 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_5192_13647 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_5376_16839 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_5729_15479 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_6023_23425 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_6157_14162 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_6195_22577 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_6406_17446 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7121_11602 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7322_8000 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7351_18355 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7440_25161 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7935_23071 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_7983_19217 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_8061_5651 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_8635_4065 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2106_9825_25452 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_10204_14755 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_11657_13078 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_11906_9914 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_12004_21624 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_12254_20158 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_12571_6806 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_12635_9258 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_12648_2958 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_13212_5978 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_13491_23065 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_13743_6326 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_13983_4064 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_14183_16985 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_14513_4073 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_14918_28357 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_15045_15392 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_15150_10894 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_15949_19241 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_17632_9300 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_17984_19413 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_18696_25524 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_18830_14440 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_19160_17803 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_19740_4106 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_19816_10175 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_19825_3272 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_20030_17631 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_20747_11441 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_20852_6724 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_20899_8562 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_21998_24231 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_22261_19652 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_22514_13582 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_23261_19339 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_2334_12431 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_23588_9698 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_23661_7326 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_24520_21962 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_25699_18018 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_25782_17796 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_25841_6806 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_26080_19976 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_26286_17513 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_26926_15409 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_27531_15582 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_28304_9486 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_3722_8565 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_4148_14649 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_4917_15961 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_5545_10474 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_5701_13202 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_7306_25955 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_7437_17164 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_7509_25231 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_7710_12059 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_9032_23223 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_9222_25592 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_9414_18469 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_9466_5476 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2107_9517_14423 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_10059_2952 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_11354_12611 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_13230_14902 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_13735_3398 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_13922_1967 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_13945_23740 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_14590_13416 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_14694_11697 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_14775_4305 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_15078_4192 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_15226_21458 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_15321_12933 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_17837_22329 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_18337_12711 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_19750_19814 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_20438_23975 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_21062_24453 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_21081_8369 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_21781_16561 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_21971_26802 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_22060_13282 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_22741_6807 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_23528_7980 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_23716_11033 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_24051_8527 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_24564_25622 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_24583_9439 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_24810_18209 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_25209_10710 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_25795_15154 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_2683_11620 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_27093_9146 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_27105_15741 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_3490_13057 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_5388_8077 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_5526_14758 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_6291_19264 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_6364_6020 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_7274_16771 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_7801_9311 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_8000_17167 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_8808_17418 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_9165_4639 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_9219_4448 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_9445_5111 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_9466_14065 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_9617_19771 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2108_9846_22332 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_10205_18981 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_10372_5873 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_10535_26297 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_10544_10650 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_11323_9743 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12212_20860 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12236_18094 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12307_9295 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12450_22017 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12456_20601 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12566_7269 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_12728_9077 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_13449_14629 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_13989_2263 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_14376_10430 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_14830_2130 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_15855_5102 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_16339_7718 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_16582_16889 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_16664_16991 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_17065_1906 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_18461_3874 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_19307_17219 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_19564_17256 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_20391_22923 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_20437_19049 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_20592_27237 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_20919_20370 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_22278_7884 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_22507_15392 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_23086_8912 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_23265_14829 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_24530_21992 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_25023_15690 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_25722_9265 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_26300_13297 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_27097_18920 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_27914_20850 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_28344_20195 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_28490_20651 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_28876_10577 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_2960_14018 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_3461_15602 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_4107_21030 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_5570_8935 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_5980_12147 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_6655_15851 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_6903_7869 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_7899_5865 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_8491_17675 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_8496_12012 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_8551_4335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_8609_16386 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_8667_25943 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_9084_13270 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2109_9285_25837 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_10886_3226 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_12217_22217 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_13525_13645 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_13584_10075 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_14622_10683 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_15510_1683 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_15668_14419 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_15780_16235 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_15818_20698 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_15833_2403 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_15923_17702 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_17005_6214 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_17218_6842 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_17317_8081 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_17866_5796 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_18263_11979 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_18421_18310 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_19026_1749 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_19046_13331 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_19412_2394 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_19860_2797 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_20420_21792 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_20434_22857 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_20868_23902 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_21502_17715 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_2316_17092 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_23700_24102 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_23991_25745 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_24490_11115 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_24517_20632 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_24818_15580 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_24864_15158 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_25787_10911 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_26033_10853 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_26457_9220 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_26804_13244 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_27225_16023 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_27495_16245 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_27956_20423 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_28125_14140 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_28688_11522 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_29486_16531 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_3362_19192 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_4106_20737 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_4906_13512 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_4951_15044 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_5113_8148 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_5810_20950 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_5853_9485 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_6624_17473 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_6650_6715 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_6866_10686 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_6995_9403 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_7462_24627 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_7515_22077 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_7543_22324 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_7987_18192 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_9123_20247 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_9501_20158 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2110_9966_22065 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_10136_13238 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_10293_18673 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_11878_16691 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_12787_25097 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_12837_25435 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_13068_5392 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_13244_3332 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_13386_16889 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_13830_14089 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_14089_12942 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_14442_27270 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_14455_3811 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_14842_5145 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_14869_11590 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_14914_5381 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15036_17358 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15106_6826 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15151_1950 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15177_21810 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15207_2597 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15539_4237 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_15804_18359 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_16153_22157 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_16569_13270 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_17050_14532 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_17071_2863 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_17392_24669 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_17854_7336 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_18143_6650 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_18355_19543 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_18379_20290 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_18464_8558 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_18996_14181 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_19802_15143 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_21150_5227 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_21574_25309 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_21788_14200 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_22224_22062 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_22260_9282 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_23271_21541 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_23914_15903 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_24041_15953 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_24258_19550 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_24568_24953 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_26053_10499 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_2613_17396 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_26143_20083 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_26760_20175 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_27090_7263 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_28065_12058 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_28655_15159 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_29080_16480 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_29202_16264 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_3549_15434 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_4231_10779 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_4285_19779 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_4469_10978 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_4858_21725 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_5259_19167 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_5670_17507 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_5673_19602 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_5772_10634 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_5808_20097 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_5848_25229 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_6729_17570 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_6840_19137 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_7156_22688 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_7309_12815 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2111_8533_13171 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_10126_7106 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_10539_19902 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_11166_24025 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_11603_17910 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_11624_21661 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_11824_9519 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_11837_6491 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_12189_24293 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_13031_7200 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_13888_2572 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_14248_18887 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_14382_3314 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_15019_16085 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_15302_5935 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_15432_21996 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_16115_10369 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_16474_15384 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_16607_4174 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_16991_25039 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_17962_8764 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_18267_2088 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_18577_21005 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_19205_22496 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_19691_12086 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_19722_22444 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_19728_8926 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_19873_6121 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_20023_14405 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_20469_6369 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_20633_15104 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_20867_8345 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_21277_27381 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_22887_6534 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_23333_7920 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_23455_19701 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_23551_10028 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_23565_9691 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_24198_11160 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_24841_6061 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_2553_17765 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_25672_21754 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_26005_19517 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_26005_7712 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_26291_9502 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_26392_23070 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_2838_20382 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_28413_15780 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_4690_9001 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_6479_20148 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_6728_11116 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_7076_9481 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_7455_14310 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_8316_7959 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_8504_19261 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_8646_25194 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_8914_24899 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2112_9831_23489 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_10059_6971 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_10153_14830 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_11035_23660 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_11270_9905 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_11689_21000 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_11690_4317 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_12516_25003 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_12650_3034 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_12653_8251 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_12698_5946 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_12888_7866 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_13185_18405 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_13410_10335 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_14252_23185 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_14359_6429 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_14528_22431 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_14859_6290 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_15012_10918 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_15870_27855 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_17437_10856 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_18304_15744 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_18497_15507 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_18756_10703 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_18804_3434 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_19041_11047 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_19106_2173 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_19457_6468 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_20812_18267 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_21525_27936 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_21956_15268 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_23573_5169 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_24217_6085 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_24477_8022 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_24906_14601 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_26904_12158 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_27301_12168 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_27360_13452 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_2844_18214 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_3048_10069 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_3924_11644 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_3933_10511 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_4326_12847 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_5076_14343 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_5781_16549 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_7297_15266 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_7365_15112 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_7388_4583 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_8859_13346 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_9096_6554 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_9262_3221 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_9526_16943 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2113_9723_21709 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_10538_22818 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_11005_10047 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_11151_18224 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_12046_7191 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_12346_20528 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_12594_7351 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_12616_13958 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_12906_15822 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_12929_1820 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_13628_13841 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_13662_2696 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_13716_25057 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_13819_7145 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_14249_14060 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_14796_11761 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_15982_15865 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_16140_8954 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_16190_7707 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_16797_2935 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_17487_23411 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_18287_22639 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_18510_9287 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_18617_7362 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_18645_17726 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_19132_20028 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_19147_26979 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_19366_18971 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_19799_16783 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_19886_19416 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_20164_15476 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_20465_15956 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_20472_9933 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_20659_14680 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_20931_4385 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21039_8030 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21427_18894 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21748_26470 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21765_26353 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21768_10980 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21838_17154 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_21930_17444 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_22363_18921 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_22505_15112 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_22802_17789 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_22847_15051 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_23219_17216 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_23343_11886 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_24130_18450 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_24617_15857 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_25132_10504 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_25265_21963 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_25572_18073 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_25657_24882 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_25929_14147 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_26248_15559 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_27458_9617 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_27555_14671 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_2978_15841 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_3959_21195 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_4140_15125 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_4810_8061 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_6012_17061 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_6558_11400 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_6719_25546 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_6989_13179 is in your groupfile and not your listfile. Please correct.
[ERROR]: M03555_131_000000000-ANG5J_1_2114_7177_6104 is in your groupfile and not your listfile. Please correct.
Your group file contains 51374 sequences and list file contains 49853 sequences. Please correct.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.shared

**Lína 68**

mothur > classify.otu(list=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.list, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, taxonomy=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.taxonomy, label=1)
1	330

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.1.cons.taxonomy
/data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.pds.wang.pick.tx.1.cons.tax.summary


# 60. Analysis
**Lína 80**

mothur > system(mv ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.shared ./outFiles/BSC16s.an.shared)


**Lína 81**

mothur > system(mv ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.an.unique_list.0.03.cons.taxonomy ./outFiles/BSC16s.an.cons.taxonomy)

**Lína 83**

mothur > count.groups(shared=./outFiles/BSC16s.an.shared)
B8_01 contains 41878.
B8_02 contains 41523.
B8_03 contains 46241.
B8_04 contains 44744.
B8_05 contains 49954.
B8_06 contains 43502.
B8_07 contains 44889.
B8_08 contains 41396.
B8_09 contains 36619.
B8_10 contains 38036.

Total seqs: 428782.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.count.summary

**Lína 84**

mothur > sub.sample(shared=./outFiles/BSC16s.an.shared, size=2241)
Sampling 2241 from each group.
0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.shared


# 70. OTU-based analysis

## 70.10 Alpha diversity

**Lína 93**

mothur > rarefaction.single(shared=./outFiles/BSC16s.an.shared, calc=sobs, freq=100,processors=10)

Using 10 processors.

Processing group B8_01

0.03

Processing group B8_02

0.03

Processing group B8_03

0.03

Processing group B8_04

0.03

Processing group B8_05

0.03

Processing group B8_06

0.03

Processing group B8_07

0.03

Processing group B8_08

0.03

Processing group B8_09

0.03

Processing group B8_10

0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.groups.rarefaction

**Lína 94**

mothur > summary.single(shared=./outFiles/BSC16s.an.shared, calc=nseqs-coverage-sobs-invsimpson, subsample=2441)

Processing group B8_01

0.03

Processing group B8_02

0.03

Processing group B8_03

0.03

Processing group B8_04

0.03

Processing group B8_05

0.03

Processing group B8_06

0.03

Processing group B8_07

0.03

Processing group B8_08

0.03

Processing group B8_09

0.03

Processing group B8_10

0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.groups.ave-std.summary
/data/data02/asta/testrun/outFiles/BSC16s.an.groups.summary

## 70.20 Beta diversity measurements

**Lína 99**

mothur > heatmap.bin(shared=./outFiles/BSC16s.an.0.03.subsample.shared, scale=log2, numotu=50)
0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.heatmap.bin.svg

**Lína 100**

mothur > dist.shared(shared=./outFiles/BSC16s.an.shared, calc=thetayc-jclass, subsample=2241,processors=10)

Using 10 processors.
0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.dist
/data/data02/asta/testrun/outFiles/BSC16s.an.jclass.0.03.lt.dist
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.std.dist
/data/data02/asta/testrun/outFiles/BSC16s.an.jclass.0.03.lt.ave.dist
/data/data02/asta/testrun/outFiles/BSC16s.an.jclass.0.03.lt.std.dist

**Lína 101**

mothur > heatmap.sim(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist)

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.heatmap.sim.svg

**Lína 102**

mothur > heatmap.sim(phylip=./outFiles/BSC16s.an.jclass.0.03.lt.ave.dist)

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.jclass.0.03.lt.ave.heatmap.sim.svg

**Lína 103**

mothur > venn(shared=./outFiles/BSC16s.an.0.03.subsample.shared, groups=F3D0-F3D1-F3D2-F3D3)
F3D0 is not a valid group, and will be disregarded.
F3D1 is not a valid group, and will be disregarded.
F3D2 is not a valid group, and will be disregarded.
F3D3 is not a valid group, and will be disregarded.
You provided no valid groups. I will run the command using all the groups in your file.
0.03

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_04.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_04.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_05.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_05.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_03-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_05.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_05.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_04-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_05-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_02-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_05.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_05.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_04-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_05-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_03-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_05-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_04-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_05-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_06-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_07-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_07-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_07-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_07-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_07-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_07-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_01-B8_08-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_05.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_05.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_04-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_05-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_03-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_05-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_04-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_05-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_06-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_07-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_07-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_07-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_07-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_07-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_07-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_02-B8_08-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_06.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_06.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_05-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_04-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_05-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_06-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_07-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_07-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_07-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_07-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_07-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_07-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_03-B8_08-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_07.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_07.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_06-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_05-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_06-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_07-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_07-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_07-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_07-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_07-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_07-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_04-B8_08-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_07-B8_08.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_07-B8_08.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_07-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_07-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_07-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_07-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_06-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_07-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_07-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_07-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_07-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_07-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_07-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_05-B8_08-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_07-B8_08-B8_09.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_07-B8_08-B8_09.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_07-B8_08-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_07-B8_08-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_07-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_07-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_06-B8_08-B8_09-B8_10.sharedotus
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_07-B8_08-B8_09-B8_10.svg
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.sharedsobs.B8_07-B8_08-B8_09-B8_10.sharedotus

**Lína 104**

mothur > tree.shared(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist,processors=10)

Using 10 processors.
********************#****#****#****#****#****#****#****#****#****#****#
Reading matrix:     |||||||||||||||||||||||||||||||||||||||||||||||||||
***********************************************************************
Tree complete. 

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre

**Lína 105**

###<span style="color:red"> *Skoða error*</span>

mothur > parsimony(tree=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.tre, group=mouse.time.design,  groups=all,processors=10)
Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design

Using 10 processors.
[ERROR]: did not complete parsimony.

**Lína 106**

mothur > pcoa(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist)

Processing...
Rsq 1 axis: 0.88897
Rsq 2 axis: 0.90678
Rsq 3 axis: 0.92909

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.pcoa.axes
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.pcoa.loadings

**Lína 107**

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
Lowest stress :	0.242277
R-squared for configuration:	0.722589

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.iters
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.stress
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes

**Lína 108**

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
Lowest stress :	0.156318
R-squared for configuration:	0.801497

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.iters
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.stress
/data/data02/asta/testrun/outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes

**Lína 109**

### <span style="color:red"> *Athuga error*</span>

mothur > amova(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, design=mouse.time.design)
Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design
[ERROR]: did not complete amova.

**Lína 110**

### <span style="color:red"> *Athuga error*</span>

mothur > homova(phylip=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.dist, design=mouse.time.design)
Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design
[ERROR]: did not complete homova.

**Lína 111**

mothur > corr.axes(axes=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes, shared=./outFiles/BSC16s.an.0.03.subsample.shared, method=spearman, numaxes=3)
You did not provide a label, I will use the first label in your inputfile.

Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.spearman.corr.axes


**Lína 112**

###<span style="color:red"> *Athuga error*</span>

mothur > corr.axes(axes=./outFiles/BSC16s.an.thetayc.0.03.lt.ave.nmds.axes, metadata=mouse.dpw.metadata, method=spearman, numaxes=3)
Unable to open mouse.dpw.metadata. Trying default /usr/local/bin/mouse.dpw.metadata
Unable to open /usr/local/bin/mouse.dpw.metadata. Trying mothur's location /usr/local/bin/mouse.dpw.metadata
Unable to open /usr/local/bin/mouse.dpw.metadata. Trying output directory /data/data02/asta/testrun/outFiles/mouse.dpw.metadata
Unable to open /data/data02/asta/testrun/outFiles/mouse.dpw.metadata
You did not provide a label, I will use the first label in your inputfile.
[ERROR]: did not complete corr.axes.

**Lína 113**

mothur > get.communitytype(shared=./outFiles/BSC16s.an.0.03.subsample.shared,processors=10)
Using 1 processor
0.03
K	NLE		logDet	BIC		AIC		Laplace
1	31642.3	2629.11	35311.4	34829.3	30028.22	38432	-1509.69	45771.5	44807	31818.93	45757.8	-6531.22	56767.6	55320.8	33704.44	53442.7	-12346.9	68122.8	66193.7	35551.85	61780.2	inf	80130.6	77719.2	inf
Output File Names: 
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.mix.fit
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.1.mix.posterior
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.1.mix.relabund
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.2.mix.posterior
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.2.mix.relabund
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.3.mix.posterior
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.3.mix.relabund
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.4.mix.posterior
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.4.mix.relabund
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.5.mix.posterior
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.5.mix.relabund
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.mix.design
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.mix.parameters
/data/data02/asta/testrun/outFiles/BSC16s.an.0.03.subsample.0.03.dmm.mix.summary


## 70.30 Population-level analysis

**Lína 118**

###<span style="color:red"> *Athuga error*</span>

mothur > metastats(shared=./outFiles/BSC16s.an.0.03.subsample.shared, design=mouse.time.design,processors=10)
Unable to open mouse.time.design. Trying default /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying mothur's location /usr/local/bin/mouse.time.design
Unable to open /usr/local/bin/mouse.time.design. Trying output directory /data/data02/asta/testrun/outFiles/mouse.time.design
Unable to open /data/data02/asta/testrun/outFiles/mouse.time.design

Using 10 processors.
[ERROR]: did not complete metastats.

**Lína 119**

mothur > classify.rf(shared=./outFiles/BSC16s.an.0.03.subsample.shared, design=mouse.time.design)

# 80. Phylogeny-based analysis

## 80.10 Alpha diversity

**Lína 128**

###<span style="color:red"> *Athuga error*</span>

mothur > phylo.diversity(tree=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre, count=./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.denovo.uchime.pick.count_table, rarefy=T,processors=10)
Unable to open ./outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre. Trying default /usr/local/bin/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre
Unable to open /usr/local/bin/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre. Trying mothur's location /usr/local/bin/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre
Unable to open /usr/local/bin/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre. Trying output directory /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre
Unable to open /data/data02/asta/testrun/outFiles/BSC16s.trim.contigs.good.unique.good.filter.unique.precluster.pick.phylip.tre

Using 10 processors.
[ERROR]: did not complete phylo.diversity.

mothur > quit()


************************************************************
************************************************************
************************************************************
Detected 1527 [ERROR] messages, please review.
************************************************************
************************************************************
************************************************************


<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
Detected 1527 [WARNING] messages, please review.
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<^>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
