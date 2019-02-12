*APS Advanced Stats Delivery*
# Introduction to NGS data
#### Nicola Nadeau, Alison Wright, Victor Soria-Carrasco

[day 1](https://github.com/visoca/MolEcolStats-introNGSdata/blob/master/test.md)

The aim of this practical is to get you started using the HPC and looking at some NGS data

### Before you start
Here are some websites that it is useful to have on hand (you might want to bookmark these so you can easily go back to them)

Linux and Shell cheatsheet (it's not cheating!): http://rcg.group.shef.ac.uk/courses/linux/shell-cheatsheet.html

CiCS page on using the ShARC cluster: https://www.sheffield.ac.uk/cics/research/hpc/sharc

CiCS page on interactive useage of the cluster: https://www.sheffield.ac.uk/cics/research/hpc/using/interactive

CiCS page on submitting jobs to the cluster (more on his later): https://www.sheffield.ac.uk/cics/research/hpc/sharc/batch

## 1. Logging in and getting started
We will be working on windows machines, which means that you need to use a program (ssh client) to access the cluster. We will be using MobXterm. Start by opening the program, if you have used it before to connect to sharc you may find "sharc.sheff.ac.uk" under "User sessions", in which case you can just double click on this to launch an ssh session on sharc. If not, click on "Session">"SSH" and enter
```bash
sharc.sheffield.ac.uk
```
in the "Remote host" box and specify your username (port should always be 22).

Request an interactive session:
```bash
qrsh
```
You should always start by doing this. No work should ever be done on the head node! If you are on a head node you will see someting like this in your cammand line prompt:
```bash
[bo1nn@sharc-login1 ~]$
```
This node is just a gateway to the worker nodes. If you are on a worker noe you will see the name of the node, eg.
```bash
[bo1nn@sharc-node004 ~]$
```

We are going to create a working directory in a dedicated space in the HPC cluster (/data/$USER) and copy the necessary scripts and data files to run this practical.

Connect to Iceberg HPC cluster (change *myuser* by your username):
```bash
ssh myuser@iceberg.sheffield.ac.uk


#### Important note
***
This tutorial relies on having access to a number of programs. The easiest way is to have your account configured to use the Genomics Software Repository. If that is the case you should see the following message when you get an interactive session with ```qrsh```:
```
  Your account is set up to use the Genomics Software Repository
     More info: http://soria-carrasco.staff.shef.ac.uk/softrepo
```
If you don't get that message, follow the instructions [here](http://soria-carrasco.staff.shef.ac.uk/softrepo/) to set up your account.

In addition, if you want to configure the ```nano``` text editor to have syntax highlighting and line numbering, you can configure it this way:
```bash
cat /usr/local/extras/Genomics/workshops/January2018/.nanorc >> /home/$USER/.nanorc
```
***

#### Note on transferring output files to your local computer for visualization
***
You probably will want to transfer files to your own computer for visualization (especially the images). In Linux and Mac, you can do that using rsync on the terminal. For example, to transfer one of the pdf files or all the results that are generated in this practical, the command would be: 
```bash
# transfer pdf file
rsync myuser@iceberg.sheffield.ac.uk:/data/myuser/gwas_gemma/output/hyperparameters.pdf ./
# transfer all results
rsync -av myuser@iceberg.sheffield.ac.uk:/data/myuser/gwas_gemma/output ./
```
Another possibility is to email the files, for example:
```bash
echo "Text body" | mail -s "Subject: gemma - hyperparameter plot" -a /data/myuser/gwas_gemma/output/hyperparameters.pdf your@email
```
Graphical alternatives are [WinSCP](http://dsavas.staff.shef.ac.uk/software/xconnect/winscp.html) or [Cyberduck](http://www.macupdate.com/app/mac/8392/cyberduck). You can find more detailed information [here](https://www.sheffield.ac.uk/wrgrid/using/access).

***

## 2. Fastq format
Visualising fastq files with “less” (zless), counting lines with “wc -l”, (searching with grep and awk?), piping

## 3. Assessing quality of fastq files [Fastqc]

## 4. Quality trimming fastq files [Trimmomatic]

## 5. Demultiplexing Illumina data