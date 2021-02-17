# Katie's Advanced Genomics Notebook   
  
## Day 02 Exercise 2021-Jan-22 
# 

	#1- Logon to cluster @turing.hpc.odu.edu
	$ ssh kpark049@turing.hpc.odu.edu

	#2- Make a directory in your course workspace called data   
	$ cd /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker
	$ mkdir data  

	#3- Make a directory called exercises in your data directory
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data  

	$ cd /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data
	$ mkdir exercises  

	#4- execute a pwd command and start a log of your commands with a header for today's date in your README.md github logfile in your workspace
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/exercises 

	#5- cp the Exercise2.fasta.gz and Exercise2.fastq.tar.gz files into your exercises directory from the /cm/shared/courses/dbarshis/21AdvGenomics/assignments_exercises/day02 directory
	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/assignments_exercises/day02/Exercise2.fast* ./  

	$ ls 
	Exercise2.fasta  Exercise2.fasta.gz  Exercise2.fastq.tar.gz  

	$ ls -alh (list all files and long format with readable file size)
	total 37M
	drwxrwxrwx 2 kpark049 users  109 Jan 22 14:09 .
	drwxrwxrwx 3 kpark049 users   27 Jan 22 13:46 ..
	-rwxrwxrwx 1 kpark049 users  17M Jan 22 14:09 Exercise2.fasta
	-rwxr-xr-x 1 kpark049 users 4.3M Jan 22 13:40 Exercise2.fasta.gz
	-rwxr-xr-x 1 dbarshis users 4.3M Jan 22 13:52 Exercise2.fastq.tar.gz

	#6- unzip and untar the files
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/exercises  

	$ gunzip -c Exercise2.fasta.gz > Exercise2.fasta
	$ ls
	$ Exercise2.fasta  Exercise2.fasta.gz  Exercise2.fastq  Exercise2.fastq.tar.g  

	$ ls -alh
	total 62M
	drwxrwxrwx 2 kpark049 users  142 Jan 24 13:59 .
	drwxrwxrwx 3 kpark049 users   27 Jan 22 13:46 ..
	-rwxrwxrwx 1 kpark049 users  17M Jan 24 14:03 Exercise2.fasta
	-rwxr-xr-x 1 kpark049 users 4.3M Jan 22 13:40 Exercise2.fasta.gz
	-rw-r--r-- 1 kpark049 users  18M Sep  2  2015 Exercise2.fastq
	-rwxr-xr-x 1 dbarshis users 4.3M Jan 22 13:52 Exercise2.fastq.tar.gz  

	$ tar -zxvf Exercise2.fastq.tar.gz 
	Exercise2.fastq  

	$ ls -alh
	total 62M
	drwxrwxrwx 2 kpark049 users  142 Jan 24 13:59 .
	drwxrwxrwx 3 kpark049 users   27 Jan 22 13:46 ..
	-rwxrwxrwx 1 kpark049 users  17M Jan 22 14:09 Exercise2.fasta
	-rwxr-xr-x 1 kpark049 users 4.3M Jan 22 13:40 Exercise2.fasta.gz
	-rw-r--r-- 1 kpark049 users  18M Sep  2  2015 Exercise2.fastq
	-rwxr-xr-x 1 dbarshis users 4.3M Jan 22 13:52 Exercise2.fastq.tar.gz
	
	#7- add these commands to your notebook file
	\ (•◡•) /

	#8- calculate how many sequences are in each file and add these results to your notebook file
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/exercises  

	$ head -1 Exercise2.fasta
	>scaffold10078|size20675  
	
	$ grep -c '>' Exercise2.fasta
	138  

	$ head -1 Exercise2.fastq
	@HS3:541:HAYTUADXX:1:1101:1297:1938 1:N:0:AGTTCC

	$grep -c '@HS3' Exercise2.fastq
	61304

	$ wc -l Exercise2.fastq
	245216 Exercise2.fastq

	$ echo 245216/4 | bc -l
	61304.00000000000000000000

	#9- cp the avg_cov_len_fasta_advbioinf.py from the /cm/shared/courses/dbarshis/21AdvGenomics/scripts directory into your class scripts directory
	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/scripts/avg_cov_len_fasta_advbioinf.py ../scripts/
	

	#10- start an interactive compute session and re-navigate to your exercises directory
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/exercises  
	
	$ salloc
	salloc: Pending job allocation 9269196
	salloc: job 9269196 queued and waiting for resources
	salloc: job 9269196 has been allocated resources
	salloc: Granted job allocation 9269196  

	#11- run the avg_cov_len_fasta_DJB.py script on your Exercise2.fasta file by typing the path to the script followed by the Exercise2.fasta file name
	$ ../../scripts/avg_cov_len_fasta_advbioinf.py Exercise2.fasta
	The total number of sequences is 138
	The average sequence length is 126640
	The total number of bases is 17476447
	The minimum sequence length is 1122
	The maximum sequence length is 562680
	The N50 is 187037
	Median Length = 92612
	contigs < 150bp = 0
	contigs >= 500bp = 138
	contigs >= 1000bp = 138
	contigs >= 2000bp = 135  

	12- did you add all these entries to your notebook file, including the results of the script?
	I believe so!  

	13- push your notebook file to your github page
	

## Day 03 Exercise 2021-Jan-27
### Day 02 Homework  

### 1- Write an sbatch script to cp the files /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/originalfastqs/ into your own data directory: KatieP-HADB03
	
	$ ssh kpark049@turing.hpc.odu.edu
	$ cd /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data

	$pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data
 

### 2- Add the content of your sbatch script to your logfile 
	
	$ nano KPCopyLane03.sh

	#!/bin/bash -l

	#SBATCH -o KPCopyLane03.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KPCopyLane03

	cp /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/originalfastqs/HADB03*.fastq.gz /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data


### 3- submit the slurm script (sbatch scripname.sh) and verify that it's working (by squeue -u yourusername multiple times and checking the destination directory to make sure the files are being created)

	$ sbatch KPCopyLane03.sh
	Submitted batch job 9270445

	$ squeue -u kpark049
	
### 4- Make sure this is all documented on your github notebook
	\ (•◡•) /
	


### 5- Write a sbatch script to gunzip all the fastq.gz files in your data directory

	$nano KPGunzipLane03.sh

	#!/bin/bash -l

	#SBATCH -o KPGunzipLane03.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KPCopyLane03

	gunzip *.fastq.gz  

	$ sbatch KPGunzipLane03.sh
	$squeue -u kpark049


### 6- Push your notebook file to your github page (document everything on your github notebook, drink a beer, and realize that all that work was just to get the data organized to start looking at it!)  

	\ (•◡•) /  


### Day03 Homework


### 1- cp the /cm/shared/courses/dbarshis/21AdvGenomics/assignments_exercises/day03 directory (and files) to your sandbox

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker
	
	$ cp-r /cm/shared/courses/dbarshis/21AdvGenomics/assignments_exercises/day03 ./

	$ ls
	data  day03  groundrules.txt  KP_exercise1.txt  nano.save  nano.save.1  scripts  


### 2- mkdir a fastq directory in your data directory and mv all the .fastq files into this directory
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data

	$ mkdir fastq  
	$ mv *.fastq fastq/
	$ ls
	exercises  KPCopyLane03.sh   KPGunzipLane03.sh
	fastq      KPCopyLane03.txt  KPGunzipLane03.txt



### 3a- cp the renamingtable_complete.txt from the day03 directory into your fastq directory 
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data

	$ cp ../day03/renamingtable_complete.txt ./fastq/

### 3b- cp the /cm/shared/courses/dbarshis/21AdvGenomics/scripts/renamer_advbioinf.py script into your sandbox scripts folder 

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker

	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/scripts/renamer_advbioinf.py ./scripts/

### 3c- less the new script and check out the usage statement
	
	$ $ head ../scripts/renamer_advbioinf.py

	#!/usr/bin/env python
	####usage renamer.py renamingtable
	#### this script take the entries in the first column of table and renames (mv's) them to files with the names in the second column
	import sys
	import os

	fin=open(sys.argv[1],'r')
	linecount=0
	for line in fin:
        linecount+=1


### 4- run the renamer_advbioinf.py script in your fastq folder using the renamingtable_complete.txt as practice and verify the output to the screen by hand

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq



 	$../../scripts/renamer_advbioinf.py renamingtable_complete.txt
	mv HADB01-A_S17_L002_R1_001.fastq VA_W_01_14.fastq
	mv HADB01-B_S18_L002_R1_001.fastq VA_B_01_14.fastq
	mv HADB01-C_S19_L002_R1_001.fastq RI_W_01_14.fastq
	mv HADB01-D_S20_L002_R1_001.fastq RI_B_01_14.fastq
	mv HADB01-E_S21_L002_R1_001.fastq VA_W_01_22.fastq
	mv HADB01-F_S22_L002_R1_001.fastq VA_B_01_22.fastq
	mv HADB01-G_S23_L002_R1_001.fastq RI_W_01_22.fastq
	mv HADB01-H_S24_L002_R1_001.fastq RI_B_01_22.fastq
	mv HADB01-I_S25_L002_R1_001.fastq VA_W_01_18.fastq
	mv HADB01-J_S26_L002_R1_001.fastq VA_B_01_18.fastq
	mv HADB01-K_S27_L002_R1_001.fastq RI_W_01_18.fastq
	mv HADB01-L_S28_L002_R1_001.fastq RI_B_01_18.fastq
	mv HADB01-M_S29_L002_R1_001.fastq VA_W_08_SNP.fastq
	mv HADB01-N_S30_L002_R1_001.fastq VA_B_09_SNP.fastq
	mv HADB01-O_S31_L002_R1_001.fastq RI_W_08_SNP.fastq
	mv HADB01-P_S32_L002_R1_001.fastq RI_B_08_SNP.fastq
	mv HADB02-A_S33_L003_R1_001.fastq VA_W_02_14.fastq
	mv HADB02-B_S34_L003_R1_001.fastq VA_B_02_14.fastq
	mv HADB02-C_S35_L003_R1_001.fastq RI_W_02_14.fastq
	mv HADB02-D_S36_L003_R1_001.fastq RI_B_02_14.fastq
	mv HADB02-E_S37_L003_R1_001.fastq VA_W_02_22.fastq
	mv HADB02-F_S38_L003_R1_001.fastq VA_B_02_22.fastq
	mv HADB02-G_S39_L003_R1_001.fastq RI_W_02_22.fastq
	mv HADB02-H_S40_L003_R1_001.fastq RI_B_02_22.fastq
	mv HADB02-I_S41_L003_R1_001.fastq VA_W_02_18.fastq
	mv HADB02-J_S42_L003_R1_001.fastq VA_B_02_18.fastq
	mv HADB02-K_S43_L003_R1_001.fastq RI_W_02_18.fastq
	mv HADB02-L_S44_L003_R1_001.fastq RI_B_02_18.fastq
	mv HADB02-M_S45_L003_R1_001.fastq VA_W_09_SNP.fastq
	mv HADB02-N_S46_L003_R1_001.fastq VA_B_08_SNP.fastq
	mv HADB02-O_S47_L003_R1_001.fastq RI_W_09_SNP.fastq
	mv HADB02-P_S48_L003_R1_001.fastq RI_B_09_SNP.fastq
	mv HADB03-A_S49_L004_R1_001.fastq VA_W_03_14.fastq
	mv HADB03-B_S50_L004_R1_001.fastq VA_B_03_14.fastq
	mv HADB03-C_S51_L004_R1_001.fastq RI_W_03_14.fastq
	mv HADB03-D_S52_L004_R1_001.fastq RI_B_03_14.fastq
	mv HADB03-E_S53_L004_R1_001.fastq VA_W_03_22.fastq
	mv HADB03-F_S54_L004_R1_001.fastq VA_B_03_22.fastq
	mv HADB03-G_S55_L004_R1_001.fastq RI_W_03_22.fastq
	mv HADB03-H_S56_L004_R1_001.fastq RI_B_03_22.fastq
	mv HADB03-I_S57_L004_R1_001.fastq VA_W_03_18.fastq
	mv HADB03-J_S58_L004_R1_001.fastq VA_B_03_18.fastq
	mv HADB03-K_S59_L004_R1_001.fastq RI_W_03_18.fastq
	mv HADB03-L_S60_L004_R1_001.fastq RI_B_03_18.fastq
	mv HADB03-M_S61_L004_R1_001.fastq VA_W_10_SNP.fastq
	mv HADB03-N_S62_L004_R1_001.fastq VA_B_10_SNP.fastq
	mv HADB03-O_S63_L004_R1_001.fastq RI_W_10_SNP.fastq
	mv HADB03-P_S64_L004_R1_001.fastq RI_B_10_SNP.fastq
	mv HADB04-A_S65_L005_R1_001.fastq VA_W_04_14.fastq
	mv HADB04-B_S66_L005_R1_001.fastq VA_B_04_14.fastq
	mv HADB04-C_S67_L005_R1_001.fastq RI_W_04_14.fastq
	mv HADB04-D_S68_L005_R1_001.fastq RI_B_04_14.fastq
	mv HADB04-E_S69_L005_R1_001.fastq VA_W_04_22.fastq
	mv HADB04-F_S70_L005_R1_001.fastq VA_B_04_22.fastq
	mv HADB04-G_S71_L005_R1_001.fastq RI_W_04_22.fastq
	mv HADB04-H_S72_L005_R1_001.fastq RI_B_04_22.fastq
	mv HADB04-I_S73_L005_R1_001.fastq VA_W_04_18.fastq
	mv HADB04-J_S74_L005_R1_001.fastq VA_B_04_18.fastq
	mv HADB04-K_S75_L005_R1_001.fastq RI_W_04_18.fastq
	mv HADB04-L_S76_L005_R1_001.fastq RI_B_04_18.fastq
	mv HADB04-M_S77_L005_R1_001.fastq VA_W_05_14.fastq
	mv HADB04-N_S78_L005_R1_001.fastq VA_B_05_14.fastq
	mv HADB04-O_S79_L005_R1_001.fastq RI_W_05_14.fastq
	mv HADB04-P_S80_L005_R1_001.fastq RI_B_05_14.fastq
	mv HADB05-A_S81_L006_R1_001.fastq VA_W_05_22.fastq
	mv HADB05-B_S82_L006_R1_001.fastq VA_B_05_22.fastq
	mv HADB05-C_S83_L006_R1_001.fastq RI_W_05_22.fastq
	mv HADB05-D_S84_L006_R1_001.fastq RI_B_05_22.fastq
	mv HADB05-E_S85_L006_R1_001.fastq VA_W_05_18.fastq
	mv HADB05-F_S86_L006_R1_001.fastq VA_B_05_18.fastq
	mv HADB05-G_S87_L006_R1_001.fastq RI_W_05_18.fastq
	mv HADB05-H_S88_L006_R1_001.fastq RI_B_05_18.fastq
	mv HADB05-I_S89_L006_R1_001.fastq VA_W_06_14.fastq
	mv HADB05-J_S90_L006_R1_001.fastq VA_B_06_14.fastq
	mv HADB05-K_S91_L006_R1_001.fastq RI_W_06_14.fastq
	mv HADB05-L_S92_L006_R1_001.fastq RI_B_06_14.fastq
	mv HADB05-M_S93_L006_R1_001.fastq VA_W_06_22.fastq
	mv HADB05-N_S94_L006_R1_001.fastq VA_B_06_22.fastq
	mv HADB05-O_S95_L006_R1_001.fastq RI_W_06_22.fastq
	mv HADB05-P_S96_L006_R1_001.fastq RI_B_06_22.fastq
	mv HADB06-A_S97_L007_R1_001.fastq VA_W_06_18.fastq
	mv HADB06-B_S98_L007_R1_001.fastq VA_B_06_18.fastq
	mv HADB06-C_S99_L007_R1_001.fastq RI_W_06_18.fastq
	mv HADB06-D_S100_L007_R1_001.fastq RI_B_06_18.fastq
	mv HADB06-E_S101_L007_R1_001.fastq VA_W_07_14.fastq
	mv HADB06-F_S102_L007_R1_001.fastq VA_B_07_14.fastq
	mv HADB06-G_S103_L007_R1_001.fastq RI_W_07_14.fastq
	mv HADB06-H_S104_L007_R1_001.fastq RI_B_07_14.fastq
	mv HADB06-I_S105_L007_R1_001.fastq VA_W_07_22.fastq
	mv HADB06-J_S106_L007_R1_001.fastq VA_B_07_22.fastq
	mv HADB06-K_S107_L007_R1_001.fastq RI_W_07_22.fastq
	mv HADB06-L_S108_L007_R1_001.fastq RI_B_07_22.fastq
	mv HADB06-M_S109_L007_R1_001.fastq VA_W_07_18.fastq
	mv HADB06-N_S110_L007_R1_001.fastq VA_B_07_18.fastq
	mv HADB06-O_S111_L007_R1_001.fastq RI_W_07_18.fastq
	mv HADB06-P_S112_L007_R1_001.fastq RI_B_07_18.fastq


### 5- Uncomment the last line of the renaming script in your scripts folder that starts with os.popen and comment out the next to last line that starts with print

	$pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/scripts

	$nano renamer_advbioinf.py  
	#!/usr/bin/env python
	####usage renamer.py renamingtable
	#### this script take the entries in the first column of table and renames (mv's) them to files with the names in the second column
	import sys
	import os

	fin=open(sys.argv[1],'r')
	linecount=0
	for line in fin:
        linecount+=1
        if linecount>=2:
                cols=line.rstrip().split('\t')
	    #       print 'mv %s %s' %(cols[0], cols[1])
                os.popen('mv %s %s' %(cols[0], cols[1])) 
	

### 6- write a sbatch script and submit it to rename all the .fastq files according to the renaming table using your renamer_advbioinf.py script
	$pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq

	$nano KparkersRename.sh
	#!/bin/bash -l


	#SBATCH -o kparkersRename.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KPrenameFastq

	../../scripts/renamer_advbioinf.py renamingtable_complete.txt  
	
	$ sbatch ./kparkersRename.sh
	Submitted batch job 9270562  

	$ squeue -u kpark049
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
           9270562      main KPrename kpark049 PD       0:00      1 (Priority)
           9269196      main       sh kpark049  R 3-04:18:22      1 coreV1-22-005
           9270432      main       sh kpark049  R    5:48:21      1 coreV2-25-072


### 7- Make sure this is all documented on your github page
### 8- The naming convention for the files is as follows:
* SOURCEPOPULATION_SYMBIOTICSTATE_GENOTYPE_TEMPERATURE.fastq
* There are 2 sources: Virginia and Rhode Island
* There are 2 symbiotic states: Brown and White  

### 9- Next, you're going to start the process of adapter clipping and quality trimming all the renamed .fastq files in batches, by lane

### 10- cp the script /cm/shared/courses/dbarshis/21AdvGenomics/scripts/Trimclipfilterstatsbatch_advbioinf.py into your scripts directory  
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/

	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/scripts/Trimclipfilterstatsbatch_advbioinf.py ./scripts/
	$ cd scripts
	$ $ ls
	avg_cov_len_fasta_advbioinf.py  renamer_advbioinf.py  Trimclipfilterstatsbatch_advbioinf.py

### 11- Less/head the new script and check out the usage statement

	$ head Trimclipfilterstatsbatch_advbioinf.py
	#!/usr/bin/env python
	# Written by Dan Barshis

	import sys, os

	########### Usage #############
	# Trimclipfilterstatsbatch.py barcodefile.txt anynumberoffastqfiles
	# This should be run from within the folder with all of your original .fastqstrim
	# Will quality trim multiple SINGLE-END fastq files
	# Things to customize for your particular platform:

### 12- cp the /cm/shared/courses/dbarshis/21AdvGenomics/assignments_exercises/day03/adapterlist_advbioinf.txt into the working directory with your fastq files

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq
	
	$cp /cm/shared/courses/dbarshis/21AdvGenomics/assignments_exercises/day03/adapterlist_advbioinf.txt ./

### 13. Make a sbatch script for the Trimclipfilter... script and run it on your fastq files

	$ mkdir testing
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/Testing  

	$ nano TestTrimClip.sh
	#!/bin/bash -l

	#SBATCH -o kptestTrimclip.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=kpTrimTest

	../../../scripts/Trimclipfilterstatsbatch_advbioinf.py adapterlist_advbioinf.txt *.fastq

	$ salloc
	salloc: Pending job allocation 9270564
	salloc: job 9270564 queued and waiting for resources
	salloc: job 9270564 has been allocated resources
	salloc: Granted job allocation 9270564

	$ sbatch TestTrimClip.sh 
	Submitted batch job 9270565

	$ squeue -u kpark049
	JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
           9269196      main       sh kpark049  R 3-04:41:06      1 coreV1-22-005
           9270432      main       sh kpark049  R    6:11:05      1 coreV2-25-072
           9270564      main       sh kpark049  R       2:04      1 coreV2-25-007

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq

	$ nano kpFullTrimClip.sh

	#!/bin/bash -l

	#SBATCH -o kpFullTrimclip.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=kpTrimFull

	../../scripts/Trimclipfilterstatsbatch_advbioinf.py adapterlist_advbioinf.txt *.fastq

	$ sbatch kpFullTripClip.sh
	Submitted batch job 9270566
	$ squeue -u kpark049
	             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
	           9270566      main kpTrimFu kpark049 PD       0:00      1 (Priority)
	           9269196      main       sh kpark049  R 3-04:46:58      1 coreV1-22-005
	           9270432      main       sh kpark049  R    6:16:57      1 coreV2-25-072
	           9270564      main       sh kpark049  R       7:56      1 coreV2-25-007
	
### 14- This will take a while (like days)
### 15- Now might be a good time to update everything on your github  

## Day 04 Homework 2021-Jan-29

### 1- Add your trimclipstats.txt output to the full class datafile /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/Fulltrimclipstatstable.txt using the following steps

### 1a- run /cm/shared/courses/dbarshis/21AdvGenomics/scripts/Schafran_trimstatstable_advbioinf_clippedtrimmed.py -h to examine usage  

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq

	$ /cm/shared/courses/dbarshis/21AdvGenomics/scripts/Schafran_trimstatstable_advbioinf_clippedtrimmed.py -h 
	Written by Peter Schafran pscha005@odu.edu 5-Oct-2015

	This script takes a stats output file from fastx_clipper and converts it into a table.

	Usage: Schafran_trimstatstable.py [-c, -v, -h] inputfile.txt outputfile.txt

	Options (-c and -v must be listed separately to run together):
	-h      Display this help message
	-c      Use comma delimiter instead of tabs
	-v      Verbose mode (print steps to stdout)

### 1b- Run the script on your data with the outputfilename YOURNAME_trimclipstatsout.txt  

	$ /cm/shared/courses/dbarshis/21AdvGenomics/scripts/Schafran_trimstatstable_advbioinf_clippedtrimmed.py trimclipstats.txt KP_trimclipstatsout.txt 

	$ ls
	filteringstats     kparkersRename.txt  kpFullTripClip.sh        originalfastqs  renamingtable_complete.txt  trimclipstats.txt
	kparkersRename.sh  kpFullTrimclip.txt  KP_trimclipstatsout.txt  QCFastqs        Testing 

### 1c- Add YOURNAME_trimclipstatsout.txt to the class file by running tail -n +2 YOURNAME_trimclipstatsout.txt >> /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/Fulltrimclipstatstable.txt  

	$ tail -n +2 KP_trimclipstatsout.txt >> /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/Fulltrimclipstatstable.txt  

### 2- Now we're going to map our reads back to our assembly using the bowtie2 alignment algorithm (starting to follow this pipeline https://github.com/bethsheets/SNPcalling_tutorial)  

### 3- write an sbatch script to do the following commands in sequence on your _clippedtrimmedfilterd.fastq datafiles from your lane of data
	
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs

	$ nano 
	#!/bin/bash -l

	#SBATCH -o KP_bowtiealn.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KPnewbowtie

	module load bowtie2/2.4
	for i in *_clippedtrimmed.fastq; do bowtie2 --rg-id ${i%_clippedtrimmed.fastq} \
	--rg SM:${i%_clippedtrimmed.fastq} \
	--very-sensitive -x /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/refassembly/Apoc_hostsym -U $i \
	> ${i%_clippedtrimmedfilterd.fastq}.sam --no-unal -k 5; done
	
	$ salloc 
	salloc: Pending job allocation 9271181
	salloc: job 9271181 queued and waiting for resources
	salloc: job 9271181 has been allocated resources
	salloc: Granted job allocation 9271181

	$ sbatch KP_bowtiealn.sh
	Submitted batch job 9271182  

	$ squeue -u kpark049
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
           9269196      main       sh kpark049  R 5-22:30:02      1 coreV1-22-005
           9270432      main       sh kpark049  R 3-00:00:01      1 coreV2-25-072
           9271182      main KPnewbow kpark049  R       0:25      1 coreV2-25-049
           9271181      main       sh kpark049  R       4:55      1 coreV2-25-049  

### 4- Submit and add everything to your logfile
		\ (•◡•) /  


## Day 05 Homework 2021-Feb-03

### 1- Team up with a partner for this one and work only on a combined set of data for your two lanes of sequences
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs

	$ mkdir Trinity 
	$ mv *.fastq ./Trinity

	# Ivan copied his fastq files into the Trinity directory in my sandbox

	$ ls *.fastq head -32 > 32fileslist.txt
	# used regex to list out list all files on one line separated by comma and copy/pasted into the Trinitybash.sh file


### 2- Run the Trinity denovo assembler on your clippedtrimmed.fastq files for your two lanes together 
### 3- Modify the below sbatch script (note the differences in the header compared to the previous one)


	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs/Trinity

	$ nano Trinitybash.sh

	#!/bin/bash -l

	#SBATCH -o Katie_Ivan_Trinity.txt
	#SBATCH -n 32
	#SBATCH -p himem
	#SBATCH --mail-user=ilope002@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KatieIvanTrinity

	enable_lmod
	module load container_env trinity

	crun Trinity --seqType fq --max_memory 768G --single RI_B_02_14_clippedtrimmed.fastq,RI_B_02_18_clippedtrimmed.fastq,RI_B_02_22_clippedtrimmed.fastq,RI_B_03_14_clippedtrimmed.fastq,RI_B_03_18_clippedtrimmed.fastq,RI_B_03_22_clippedtrimmed.fastq,RI_B_09_SNP_clippedtrimmed.fastq,RI_B_10_SNP_clippedtrimmed.fastq,RI_W_02_14_clippedtrimmed.fastq,RI_W_02_18_clippedtrimmed.fastq,RI_W_02_22_clippedtrimmed.fastq,RI_W_03_14_clippedtrimmed.fastq,RI_W_03_18_clippedtrimmed.fastq,RI_W_03_22_clippedtrimmed.fastq,RI_W_09_SNP_clippedtrimmed.fastq,RI_W_10_SNP_clippedtrimmed.fastq,VA_B_02_14_clippedtrimmed.fastq,VA_B_02_18_clippedtrimmed.fastq,VA_B_02_22_clippedtrimmed.fastq,VA_B_03_14_clippedtrimmed.fastq,VA_B_03_18_clippedtrimmed.fastq,VA_B_03_22_clippedtrimmed.fastq,VA_B_08_SNP_clippedtrimmed.fastq,VA_B_10_SNP_clippedtrimmed.fastq,VA_W_02_14_clippedtrimmed.fastq,VA_W_02_18_clippedtrimmed.fastq,VA_W_02_22_clippedtrimmed.fastq,VA_W_03_14_clippedtrimmed.fastq,VA_W_03_18_clippedtrimmed.fastq,VA_W_03_22_clippedtrimmed.fastq,VA_W_09_SNP_clippedtrimmed.fastq,VA_W_10_SNP_clippedtrimmed.fastq --CPU 32
	
	$ salloc
	salloc: Pending job allocation 9272354
	salloc: job 9272354 queued and waiting for resources
	salloc: job 9272354 has been allocated resources
	salloc: Granted job allocation 9272354
	
	$ sbatch Trinitybash.sh
	Submitted batch job 9272386
### 4- Check https://trinityrnaseq.github.io/ for usage info
### 5- Submit your trinity script

## Day 06 Homework 2021-Feb-05  

### Assembly quality assessment (following the first two steps in the recommended trinity assessment protocol from https://github.com/trinityrnaseq/trinityrnaseq/wiki/Transcriptome-Assembly-Quality-Assessment) 

### 1- start an interactive session via salloc and run the /cm/shared/apps/trinity/2.0.6/util/TrinityStats.pl script on your Trinity.fasta output from your assembly

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs/Trinity/djb_trinity_out  
	
	$ salloc 
	salloc: Pending job allocation 9272891
	salloc: job 9272891 queued and waiting for resources
	salloc: job 9272891 has been allocated resources
	salloc: Granted job allocation 9272891

	$ /cm/shared/apps/trinity/2.0.6/util/TrinityStats.pl Trinity.fasta  
		################################
	## Counts of transcripts, etc.
	################################
	Total trinity 'genes':  34661
	Total trinity transcripts:      36565
	Percent GC: 44.57
	
	########################################
	Stats based on ALL transcript contigs:
	########################################

        Contig N10: 1476
        Contig N20: 874
        Contig N30: 619
        Contig N40: 476
        Contig N50: 388

        Median contig length: 285
        Average contig: 388.75
        Total assembled bases: 14214539


	#####################################################
	## Stats based on ONLY LONGEST ISOFORM per 'GENE':
	#####################################################

        Contig N10: 1217
        Contig N20: 746
        Contig N30: 554
        Contig N40: 440
        Contig N50: 368

        Median contig length: 282
        Average contig: 371.25
        Total assembled bases: 12867801
	
	

### 2- compare this with the output from avg_cov_len_fasta_advbioinf.py on our class reference assembly (/cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/refassembly/15079_Apoc_hostsym.fasta) and add both to your logfile

	$ /cm/shared/courses/dbarshis/21AdvGenomics/scripts/avg_cov_len_fasta_advbioinf.py /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/refassembly/15079_Apoc_hostsym.fasta
	
	The total number of sequences is 15079
	The average sequence length is 876
	The total number of bases is 13210470
	The minimum sequence length is 500
	The maximum sequence length is 10795
	The N50 is 881
	Median Length = 578
	contigs < 150bp = 0
	contigs >= 500bp = 15079
	contigs >= 1000bp = 3660
	contigs >= 2000bp = 536


### 3- less or head your bowtie2 job output file to look at your alignment statistics and calculate the following from the information:
	$ less KP_bowtiealn.txt
	
### 3a-the mean percent "overall alignment rate"
	
	$ grep "overall alignment rate" KP_bowtiealn.txt
	
	1.61% overall alignment rate
	2.98% overall alignment rate
	1.43% overall alignment rate
	1.37% overall alignment rate
	1.90% overall alignment rate
	2.41% overall alignment rate
	2.13% overall alignment rate
	1.34% overall alignment rate
	1.77% overall alignment rate
	1.73% overall alignment rate
	1.75% overall alignment rate
	1.61% overall alignment rate
	1.54% overall alignment rate
	8.43% overall alignment rate
	1.61% overall alignment rate
	1.81% overall alignment rate

	*edited in excel to get average percent*
	
	
### 3b-the mean percent reads "aligned exactly 1 time"
	
	$ grep "aligned exactly 1 time" KP_bowtiealn.txt
	
	199136 (1.11%) aligned exactly 1 time
	6309 (1.09%) aligned exactly 1 time
    244035 (0.99%) aligned exactly 1 time
    294912 (0.93%) aligned exactly 1 time
    288242 (1.24%) aligned exactly 1 time
    441624 (1.62%) aligned exactly 1 time
    365338 (1.41%) aligned exactly 1 time
    155231 (0.93%) aligned exactly 1 time
    264639 (1.19%) aligned exactly 1 time
    297344 (1.11%) aligned exactly 1 time
    300536 (1.11%) aligned exactly 1 time
    247561 (1.04%) aligned exactly 1 time
    295472 (1.09%) aligned exactly 1 time
    138704 (4.59%) aligned exactly 1 time
    308675 (1.16%) aligned exactly 1 time
    268125 (0.99%) aligned exactly 1 time 

	*edited in excel to get average percent*
	
### 3c-the mean number of reads "aligned exactly 1 time"
	
	$ grep "aligned exactly 1 time" KP_bowtiealn.txt  

	199136 (1.11%) aligned exactly 1 time
	6309 (1.09%) aligned exactly 1 time
    244035 (0.99%) aligned exactly 1 time
    294912 (0.93%) aligned exactly 1 time
    288242 (1.24%) aligned exactly 1 time
    441624 (1.62%) aligned exactly 1 time
    365338 (1.41%) aligned exactly 1 time
    155231 (0.93%) aligned exactly 1 time
    264639 (1.19%) aligned exactly 1 time
    297344 (1.11%) aligned exactly 1 time
    300536 (1.11%) aligned exactly 1 time
    247561 (1.04%) aligned exactly 1 time
    295472 (1.09%) aligned exactly 1 time
    138704 (4.59%) aligned exactly 1 time
    308675 (1.16%) aligned exactly 1 time
    268125 (0.99%) aligned exactly 1 time 
	
	*edited in excel to get average percent*
	
### 3d-the mean percent reads "aligned >1 times"
	
	90147 (0.50%) aligned >1 times
    10960 (1.89%) aligned >1 times
    108147 (0.44%) aligned >1 times
    136328 (0.43%) aligned >1 times
    153600 (0.66%) aligned >1 times
    214633 (0.79%) aligned >1 times
    187386 (0.72%) aligned >1 times
    69361 (0.41%) aligned >1 times
    128013 (0.58%) aligned >1 times
    165104 (0.62%) aligned >1 times
    173888 (0.64%) aligned >1 times
    137053 (0.57%) aligned >1 times
    121462 (0.45%) aligned >1 times
    115710 (3.83%) aligned >1 times
    121835 (0.46%) aligned >1 times
    223001 (0.82%) aligned >1 times
	
	*edited in excel to get average percent*

### 4- add your statistics as single rows to the shared table /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/alignmentstatstable.txt as tab-delimited text in the following order: LaneX_yourinitials	b-the mean percent "overall alignment rate"	c-the mean percent reads "aligned exactly 1 time"	d-the mean number of reads "aligned exactly 1 time"	e-the mean percent reads "aligned >1 times"

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs
	
	$ nano LaneX_KP.txt
	
	2.21375 1.35    257242.6875     0.863125
	
	$ cat LaneX_KP.txt >> /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/alignmentstatstable.txt


### 5- Data cleanup and archiving:
### 5a- mv your Trinity.fasta file from your trinity_out_dir to a folder called testassembly in your data directory

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data

	$ mkdir testassembly


	$ mv djb_trinity_out/Trinity.fasta /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/testassembly

### 5b- set up a sbatch script to:
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data	

	$ nano KP_rm_dirs.sh

	#!/bin/bash -l

	#SBATCH -o KP_rm_dirs.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KP_rm_dirs

	rm -r /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs/Trinity/trinity_out_dir
	rm -r /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/originalfastqs
	rm -r /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/filteringstats

	$ salloc 
	salloc: Pending job allocation 9272892
	salloc: job 9272892 queued and waiting for resources
	salloc: job 9272892 has been allocated resources
	salloc: Granted job allocation 9272892

	$ sbatch KP_rm_dirs.sh
	Submitted batch job 9272893
	

### 6- submit a blast against sprot from your testassembly folder using the following command
	 pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/testassembly

	$ nano KP_blastx2sprot.sh

	#!/bin/bash -l

	#SBATCH -o blastx2sprot.txt
	#SBATCH -n 6         
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=kpblastx2sprot

	enable_lmod
	module load container_env blast
	blastx -query Trinity.fasta -db /cm/shared/apps/blast/databases/uniprot_sprot_Sep2018 -out kpblastx.outfmt6 \
	        -evalue 1e-20 -num_threads 6 -max_target_seqs 1 -outfmt 6 


 	$ sbatch KP_blastx2sprot.sh
	Submitted batch job 9272894

### Exploring our SAM files, check out http://bowtie-bio.sourceforge.net/bowtie2/manual.shtml#sam-output for bowtie2 specific output and http://bio-bwa.sourceforge.net/bwa.shtml#4 for general SAM output

### 7- head one of your .sam files to look at the header
	
	$ pwd
	
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs
	
	$ head RI_B_03_14_clippedtrimmed.fastq.sam
	@HD     VN:1.0  SO:unsorted
	@SQ     SN:TR78|c0_g1_i1_coral  LN:1109
	@SQ     SN:TR78|c0_g2_i1_coral  LN:1109
	@SQ     SN:TR79|c0_g1_i1_coral  LN:610
	@SQ     SN:TR79|c0_g2_i1_coral  LN:1549
	@SQ     SN:TR87|c0_g1_i1_coral  LN:732
	@SQ     SN:TR93|c0_g1_i1_coral  LN:550
	@SQ     SN:TR101|c0_g1_i1_coral LN:673
	@SQ     SN:TR104|c0_g1_i1_coral LN:607
	@SQ     SN:TR105|c0_g1_i1_coral LN:587


### 8- grep -v '@' your.sam | head to look at the sequence read lines, why does this work to exclude the header lines?  

	$ grep -v "@" RI_B_03_14_clippedtrimmed.fastq.sam | head
	K00188:59:HMTFHBBXX:4:1101:2138:1683    0       TR66073|c0_g2_i1_coral  143     255     51M     *       0       0       ATGAACAACAAGATGCCGGTTGCAGTGCAATCGTATGCCGAAAGATTTGCA    A-AAFJJJJJJFFJF7JJJJJJJJFJ<FJJ7FJ-<FFJ-AF<7FFJ-<-<<     AS:i:0  XN:i:0  XM:i:0  XO:i:0  XG:i:0
	NM:i:0  MD:Z:51 YT:Z:UU RG:Z:RI_B_03_14
	K00188:59:HMTFHBBXX:4:1101:3214:1683    0       TR65725|c0_g1_i1_coral  388     255     51M     *       0       0       CCCAAACAAGAAGAGAAACATCACTCCTAACTTTGTCTAGTCCAGCTGCCA    AAAFFFJJJJJJ-F<JJ<JJJJJJF<F7JJJJF-FJFFFJJJJJJJAFFAJ     AS:i:0  XN:i:0  XM:i:0  XO:i:0  XG:i:0
	NM:i:0  MD:Z:51 YT:Z:UU RG:Z:RI_B_03_14
	K00188:59:HMTFHBBXX:4:1101:15168:1683   0       TR41309|c0_g1_i1_coral  317     255     51M     *       0       0       GGAAGGTATAAATTCACAACAGAAACTATTTTGAAGAAATTCATCTTATCG    AA<AAF<FJJJJJJJJJJJJFFJJJJFJF-FJJJJFJJ<<<JJAJJJJJJF     AS:i:0  XN:i:0  XM:i:0  XO:i:0  XG:i:0
	NM:i:0  MD:Z:51 YT:Z:UU RG:Z:RI_B_03_14

### 9- in an interactive session run /cm/shared/courses/dbarshis/21AdvGenomics/scripts/get_explain_sam_flags_advbioinf.py on 2-3 of your .sam files using * to select 2-3 at the same time.

	$ /cm/shared/courses/dbarshis/21AdvGenomics/scripts/get_explain_sam_flags_advbioinf.py RI_B_03_14_clippedtrimmed.fastq.sam RI_B_03_18_clippedtrimmed.fastq.sam RI_B_03_22_clippedtrimmed.fastq.sam
	
	['0', '272', '256', '16']
	0 :
	272 :
	        read reverse strand
	        not primary alignment
	256 :
	        not primary alignment
	16 :
	        read reverse strand
	RI_B_03_18_clippedtrimmed.fastq.sam
	['0', '272', '256', '16']
	0 :
	272 :
	        read reverse strand
	        not primary alignment
	256 :
	        not primary alignment
	16 :
	        read reverse strand
	RI_B_03_22_clippedtrimmed.fastq.sam
	['0', '272', '256', '16']
	0 :
	272 :
	        read reverse strand
	        not primary alignment
	256 :
	        not primary alignment
	16 :
	        read reverse strand


### 10- we need to run the read sorting step required for SNP calling, so if you have time, set up and run the following script on your .sam files to finish before Wednesday:

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs

	$ nano SNP_sort.sh 
	#!/bin/bash -l
	
	#SBATCH -o KP_SNP_Sort.txt
	#SBATCH -n 1         
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=KP_SNP_Sort
	
	enable_lmod
	module load samtools/1
	for i in *.sam; do `samtools view -bS $i > ${i%.sam}_UNSORTED.bam`; done
	
	for i in *UNSORTED.bam; do samtools sort $i > ${i%_UNSORTED.bam}.bam
	samtools index ${i%_UNSORTED.bam}.bam
	done

	$ sbatch SNP_sort.sh
	Submitted batch job 9272898

## Day 07 Homework 2021-Feb-10  

### Day07-assess the quality of your assembly, cleanup data, start genotyping:
### Make sure to add all this to your logfile as you go, including the output from the various scripts/greps/etc.

### 1- Run the following command on your sprot output file to process into the contig length/match format that trinity examines

	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/testassembly
	
	$ nano KP_blastparsing.sh

	#!/bin/bash -l

	#SBATCH -o KP_blastparsing.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=blastparsing

	/cm/shared/apps/trinity/2.0.6/util/analyze_blastPlus_topHit_coverage.pl kpblastx.outfmt6 Trinity.fasta /cm/shared/apps/blast/databases/uniprot_sprot_Sep2018.fasta

	$ salloc 
	salloc: Pending job allocation 9276479
	salloc: job 9276479 queued and waiting for resources
	salloc: job 9276479 has been allocated resources
	salloc: Granted job allocation 9276479
	
	$ sbatch KP_blastparsing.sh
	Submitted batch job 9276481
	
	$ cat KP_blastparsing.txt
		#hit_pct_cov_bin        count_in_bin    >bin_below
	100     208     208
	90      104     312
	80      109     421
	70      142     563
	60      175     738
	50      274     1012
	40      418     1430
	30      817     2247
	20      1393    3640
	10      1049    4689
	
### 2- Rm UNSORTED.bam

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs

	$ salloc 
	salloc: Pending job allocation 9276492
	salloc: job 9276492 queued and waiting for resources
	salloc: job 9276492 has been allocated resources
	salloc: Granted job allocation 9276492
	
	$ nano rm_unsort_bam.sh
	
	#!/bin/bash -l

	#SBATCH -o rm_unsort_bam.txt
	#SBATCH -n 1
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=rm_unsort_bam
		
	rm *UNSORTED.bam
	
	$ sbatch rm_unsort_bam.sh
	Submitted batch job 9276497

### 3- Run the following to start genotyping your SNPs for filtering next class

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs
	
	$ nano mergedfastq.sh

	#!/bin/bash -l

	#SBATCH -o mergedfastq.txt
	#SBATCH -n 1         
	#SBATCH --mail-user=kpark049@odu.edu
	#SBATCH --mail-type=END
	#SBATCH --job-name=mergedfastq-

	enable_lmod
	module load dDocent
	freebayes --genotype-qualities -f /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/refassembly/15079_Apoc_hostsym.fasta *.bam > KPmergedfastqs.vcf

	$ salloc 
	salloc: Pending job allocation 9276572
	salloc: job 9276572 queued and waiting for resources
	salloc: job 9276572 has been allocated resources
	salloc: Granted job allocation 9276572
	
	$  sbatch mergedfastq.sh
	Submitted batch job 9276574


## Day 08 Homework 2021-Feb-12
### Make sure to add all this to your logfile as you go, including the output from the various scripts/greps/etc.
### 1- Clean up your data directory by:
	-Making a SAMS folder and mv all your .sam files into that directory
	-Make a BAMS folder and mv all your .bam files and .bam.bai files into that directory
	-rm your _unfiltered.vcf files if you have any
	-rm your .fastq files
	-Make a VCF folder in your data directory and mv your YOURNAMEmergedfastqs.vcf into this directory (if your freebayes job didn't complete then skip this step)


	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/
	
	$ mkdir SAMS
	$ mkdir BAMS 
	
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs
	
	$ mv *.bam *.bam.bai ../../SAMS/
	$ mv *.bam *.bam.bai ../../BAMS/
	
	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/
	
	$ mkdir VCF 
	
	
### 2- Start an interactive session via salloc
### 3- cp the /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/VCF/mergedfastq_HEAAstrangiaAssembly.vcf to your VCF folder
	
	$pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF
	
	$ salloc
	salloc: Pending job allocation 9278248
	salloc: job 9278248 queued and waiting for resources
	salloc: job 9278248 has been allocated resources
	salloc: Granted job allocation 9278248

	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/VCF/mergedfastq_HEAAstrangiaAssembly.vcf ./
	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/fastq/QCFastqs/KPmergedfastqs.vcf ./

### 4- Determine the number of individuals and variant sites in the class vcf file (and yours if it worked) using:
/cm/shared/apps/vcftools/0.1.12b/bin/vcftools --vcf mergedfastq_HEAAstrangiaAssembly.vcf

	$ enable_lmod
	$ module load dDocent
	$ vcftools

	VCFtools (0.1.14)
	© Adam Auton and Anthony Marcketta 2009

	Process Variant Call Format files

	For a list of options, please go to:
			https://vcftools.github.io/man_latest.html

	Alternatively, a man page is available, type:
			man vcftools

	Questions, comments, and suggestions should be emailed to:
			vcftools-help@lists.sourceforge.net
			
	$ vcftools --vcf mergedfastq_HEAAstrangiaAssembly.vcf

	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf mergedfastq_HEAAstrangiaAssembly.vcf

	After filtering, kept 40 out of 40 Individuals
	After filtering, kept 1214003 out of a possible 1214003 Sites


### 5- cp the /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/VCF/GoodCoralGenelistForVCFSubsetter.txt into your directory with your .vcf files

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF
	
	$ cp /cm/shared/courses/dbarshis/21AdvGenomics/classdata/Astrangia_poculata/VCF/GoodCoralGenelistForVCFSubsetter.txt ./

### 6- Run our host vcf extractor on your merged vcf file using the following syntax:

/cm/shared/courses/dbarshis/21AdvGenomics/scripts/21Sp_vcfsubsetter_advbioinf.py GoodCoralGenelistForVCFSubsetter.txt mergedfastq_HEAAstrangiaAssembly.vcf

	$ pwd
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF
	
	$salloc
	salloc: Pending job allocation 9278269
	salloc: job 9278269 queued and waiting for resources
	salloc: job 9278269 has been allocated resources
	salloc: Granted job allocation 9278269

	$ /cm/shared/courses/dbarshis/21AdvGenomics/scripts/21Sp_vcfsubsetter_advbioinf.py GoodCoralGenelistForVCFSubsetter.txt mergedfastq_HEAAstrangiaAssembly.vcf

### 7- Compare the number of variant sites in your three files (YOURNAMEmergedfastqs.vcf,  mergedfastq_HEAAstrangiaAssembly.vcf, and  mergedfastq_HEAAstrangiaAssembly_subset.vcf) using:
/cm/shared/apps/vcftools/0.1.12b/bin/vcftools --vcf 

	$ vcftools --vcf KPmergedfastqs.vcf

	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf KPmergedfastqs.vcf

	After filtering, kept 16 out of 16 Individuals
	After filtering, kept 156555 out of a possible 156555 Sites
	Run Time = 1.00 seconds
	
	$ vcftools --vcf mergedfastq_HEAAstrangiaAssembly.vcf

	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf mergedfastq_HEAAstrangiaAssembly.vcf

	After filtering, kept 40 out of 40 Individuals
	After filtering, kept 1214003 out of a possible 1214003 Sites
	Run Time = 8.00 seconds
	
	$ vcftools --vcf mergedfastq_HEAAstrangiaAssembly_subset.vcf
	
	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf mergedfastq_HEAAstrangiaAssembly_subset.vcf

	After filtering, kept 40 out of 40 Individuals
	After filtering, kept 432676 out of a possible 432676 Sites
	Run Time = 10.00 seconds
	
### 8- Work through the VCF filtering tutorial until the following step: Now that we have a list of individuals to remove, we can feed that directly into VCFtools for filtering. vcftools --vcf raw.g5mac3dp3.recode.vcf --remove lowDP.indv --recode --recode-INFO-all --out raw.g5mac3dplm

	$ vcftools --gzvcf raw.vcf.gz --max-missing 0.5 --mac 3 --minQ 30 --recode --recode-INFO-all --out raw.g5mac3

	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--gzvcf raw.vcf.gz
			--recode-INFO-all
			--mac 3
			--minQ 30
			--max-missing 0.5
			--out raw.g5mac3
			--recode

	stat error: No such file or directory
	Error: Can't determine file type of raw.vcf.gz
	
	$ vcftools --vcf raw.g5mac3.recode.vcf --minDP 3 --recode --recode-INFO-all --out raw.g5mac3dp3

	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf raw.g5mac3.recode.vcf
			--recode-INFO-all
			--minDP 3
			--out raw.g5mac3dp3
			--recode

	After filtering, kept 40 out of 40 Individuals
	Outputting VCF file...
	After filtering, kept 220678 out of a possible 220678 Sites
	Run Time = 64.00 seconds
	
	$ vcftools --vcf raw.g5mac3dp3.recode.vcf --missing-indv

	VCFtools - 0.1.14
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf raw.g5mac3dp3.recode.vcf
			--missing-indv

	After filtering, kept 40 out of 40 Individuals
	Outputting Individual Missingness
	After filtering, kept 220678 out of a possible 220678 Sites
	Run Time = 6.00 seconds
		
	$ cat out.imiss
	INDV    N_DATA  N_GENOTYPES_FILTERED    N_MISS  F_MISS
	RI_W_06_merged  220678  0       151465  0.686362
	RI_W_07_merged  220678  0       145497  0.659318
	VA_B_03_merged  220678  0       131829  0.597382
	RI_W_02_merged  220678  0       163659  0.741619
	RI_W_04_merged  220678  0       155927  0.706582
	VA_W_09_SNP_clipped     220678  0       55284   0.250519
	RI_B_08_SNP_clipped     220678  0       193465  0.876685
	VA_W_08_SNP_clipped     220678  0       185040  0.838507
	VA_B_08_SNP_clipped     220678  0       208032  0.942695
	VA_W_02_merged  220678  0       162675  0.73716
	VA_B_07_merged  220678  0       141377  0.640648
	RI_B_05_merged  220678  0       96252   0.436165
	VA_W_06_merged  220678  0       149048  0.675409
	VA_W_04_merged  220678  0       118231  0.535763
	VA_W_01_merged  220678  0       154807  0.701506
	VA_B_10_SNP_clipped     220678  0       184129  0.834379
	VA_B_06_merged  220678  0       134740  0.610573
	VA_W_05_merged  220678  0       149210  0.676144
	RI_B_09_SNP_clipped     220678  0       184248  0.834918
	VA_W_10_SNP_clipped     220678  0       184172  0.834573
	RI_W_08_SNP_clipped     220678  0       173229  0.784985
	RI_B_06_merged  220678  0       178049  0.806827
	RI_W_10_SNP_clipped     220678  0       197774  0.896211
	RI_B_04_merged  220678  0       106679  0.483415
	VA_W_03_merged  220678  0       141899  0.643014
	RI_B_07_merged  220678  0       156527  0.7093
	RI_W_05_merged  220678  0       129818  0.588269
	RI_W_09_SNP_clipped     220678  0       195857  0.887524
	VA_B_01_merged  220678  0       95061   0.430768
	VA_B_09_SNP_clipped     220678  0       176471  0.799676
	RI_B_10_SNP_clipped     220678  0       182335  0.826249
	RI_W_01_merged  220678  0       160443  0.727046
	RI_B_01_merged  220678  0       154152  0.698538
	VA_B_04_merged  220678  0       126840  0.574774
	RI_B_02_merged  220678  0       190042  0.861173
	RI_W_03_merged  220678  0       93822   0.425153
	VA_B_02_merged  220678  0       173371  0.785629
	VA_W_07_merged  220678  0       148956  0.674993
	VA_B_05_merged  220678  0       122967  0.557224
	RI_B_03_merged  220678  0       174067  0.788783
	
Day09-VCF to Genepop to PCAs
### 1-  Run one of the following sets of prescribed filters on your mergedfastq_HEAAstrangiaAssembly_subset.vcf, note these are fairly conservative filters

### Half the class run the following
/cm/shared/apps/vcftools/0.1.12b/bin/vcftools --vcf mergedfastq_HEAAstrangiaAssembly_subset.vcf --maf 0.015 --max-alleles 2 --max-missing 0.5 --minQ 30 --minGQ 20 --minDP 3 --remove-indels --hwe 0.01 --recode --recode-INFO-all --out 18718_mergedfastq_HEAAstrangiaAssembly_subset_ClassFilters

### the other half run the filters we used from the paper
/cm/shared/apps/vcftools/0.1.12b/bin/vcftools --vcf mergedfastq_HEAAstrangiaAssembly_subset.vcf --max-missing 0.5 --mac 3 --minQ 30 --minDP 10 --max-alleles 2 --maf 0.015 --remove-indels --recode --recode-INFO-all --out 1578_mergedfastq_HEAAstrangiaAssembly_subset_HEAFilters
	
	$ pwd 
	$ /cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF

	$ /cm/shared/apps/vcftools/0.1.12b/bin/vcftools --vcf mergedfastq_HEAAstrangiaAssembly_subset.vcf --max-missing 0.5 --mac 3 --minQ 30 --minDP 10 --max-alleles 2 --maf 0.015 --remove-indels --recode --recode-INFO-all --out 1578_mergedfastq_HEAAstrangiaAssembly_subset_HEAFilters

	VCFtools - v0.1.12b
	(C) Adam Auton and Anthony Marcketta 2009

	Parameters as interpreted:
			--vcf mergedfastq_HEAAstrangiaAssembly_subset.vcf
			--recode-INFO-all
			--mac 3
			--maf 0.015
			--max-alleles 2
			--minDP 10
			--minQ 30
			--max-missing 0.5
			--out 1578_mergedfastq_HEAAstrangiaAssembly_subset_HEAFilters
			--recode
			--remove-indels

	After filtering, kept 40 out of 40 Individuals
	Outputting VCF file...
	After filtering, kept 1578 out of a possible 432676 Sites
	Run Time = 12.00 seconds

### 2- Make a population file containing two columns with no header, tab delimited text the first column should be the individual name and the second column the population to which that individual belongs
	
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF
	
	$ cut -f 1 out.imiss | tail -n+2
	* copy pasted into excel and edited using formulas =LEFT(A2,4) and =MID(A1,6,2) *
	
	$ nano popfile.txt 
	* paste in from Excel File *
	
### 3- Convert your filtered .vcf file to genepop format using the following command:
/cm/shared/courses/dbarshis/21AdvGenomics/scripts/vcftogenepop_advbioinf.py YOURFILTERED.vcf YOUR_PopFile.txt

	$ salloc
	salloc: Pending job allocation 9280305
	salloc: job 9280305 queued and waiting for resources
	salloc: job 9280305 has been allocated resources
	salloc: Granted job allocation 9280305
	
	$ /cm/shared/courses/dbarshis/21AdvGenomics/scripts/vcftogenepop_advbioinf.py 1578_mergedfastq_HEAAstrangiaAssembly_subset_HEAFilters.recode.vcf popfile.txt


### 4- SCP your YOURFILE_allfilters.recode_subset_genepop.gen file to your laptop
	
	$ pwd 
	/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF
	
	$ scp kpark049@turing.hpc.odu.edu:/cm/shared/courses/dbarshis/21AdvGenomics/sandboxes/kparker/data/VCF/1578_mergedfastq_HEAAstrangiaAssembly_subset_HEAFilters.1578_mergedfastq_HEAAstrangiaAssembly_subset_HEAFilters.recode_genepop.gen ./
	
### 5- Switch to the adegenet_PCAs.R script and follow through the steps to produce some of the figures.

![](PCAS.png)
  
___  

![](Figures/pop_elip.png)  
___  
  

![](Figures/mydata.png)  
___  

![](Figures/snapclust.png)  
___  

![](Figures/compoplot.png)

	
	