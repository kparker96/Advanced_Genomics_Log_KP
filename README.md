# Katie's Advanced Genomics Notebook   

### Day 02 Exercise 2021-Jan-22 

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
	(• ◡•) 

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
	