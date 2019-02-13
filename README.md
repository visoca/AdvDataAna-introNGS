*APS Advanced Stats Delivery*
# Introduction to NGS data
#### Nicola Nadeau, Alison Wright, Victor Soria-Carrasco

The aim of this course is to give an introduction to handelling NGS sequence data on the HPC (sharc) and to some of the analyses you might want to do including investigating gene expression and nucleotide variation (SNPs).

### Before you start
Here are some websites that it is useful to have on hand (you might want to bookmark these so you can easily go back to them)

Linux and Shell cheatsheet (it's not cheating!): http://rcg.group.shef.ac.uk/courses/linux/shell-cheatsheet.html

CiCS page on using the ShARC cluster: https://www.sheffield.ac.uk/cics/research/hpc/sharc

CiCS page on interactive useage of the cluster: https://www.sheffield.ac.uk/cics/research/hpc/using/interactive

CiCS page on submitting jobs to the cluster (more on his later): https://www.sheffield.ac.uk/cics/research/hpc/sharc/batch

The genomics software repository: http://soria-carrasco.staff.shef.ac.uk/softrepo/

## Schedule
Content | Session | Venue | Lead
------- | ------- | ----- | -----
[HPC/bash/NGSdata/awk/QC](https://github.com/visoca/MolEcolStats-introNGSdata/blob/master/test.md) | Wed 20/02/2019 9-12 :: 2-5 | ADB - A04 (Perak) | Nicola Nadeau
QC/Alignment/Visualisation/Diff Expression | Thi 21/02/2019 9-12 :: 2-5 | ADB - A04 (Perak) :: Diamond 2 | Alison Wright
[SNP and genotype calling](https://github.com/visoca/variant_calling) | Wed 20/02/2019 9-12 | ADB - A04 (Perak) | Victor Soria-Carrasco

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
