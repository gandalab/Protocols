# 16S Processing with dada2

## Theory
This is a basic protocol for 16S sequencing processing from raw files to ASV tables. This is for beginning/new lab members to familiarize with the 16S bioinformatics pipeline. This pipeline is only applicable to 16S sequencing data. This protocol includes mostly code and is designed as a reference and not a stand-alone tutorial.

## Before Start

1. Register for a ROAR account under Erika's allocation: https://www.icds.psu.edu/computing-services/account-setup/
2. Login to ROAR and set up your terminal environment with the BioStar Handbook Instructions: 
3. Set up a conda environment for R following instructions in /gpfs/group/evk5387/default/scripts/r-in-conda.txt  
*this script will start an R session and download R packages that are necessary in this pipeline*

❗**As you work through this pipeline, copy each script into your own directory. DO NOT CHANGE THE ORIGINAL SCRIPTS.❗

## Procedure

### Inspect the raw fastq files

1. Activate the bioinfo conda environment  

``` conda activate bioinfo ```  

2. Open a fastq file and inspect the first 20 lines - Each read should have a header that starts with "@," a sequencer identifier, and the sequence on the next line. The third line starts with a "+" and the same sequence identifier, and the fourth line has quality information (different letters and symbols).  

``` head FILE.fastq ```  

3. Inspect number and distribution of raw reads  

``` seqkit stat *.fastq -T -j 4 > rawstats.txt ```  

*Quality Check - Does each sample have roughly the same average length and number of reads? Are there very short or very long reads? Does the number of samples match your experimental design + controls?*

4. Run FastQC on each sample and visualize the results with multiQC.

``` # make a new directory to store fastQC output files
mkdir quality
fastq *.fastq -o quality
# multiqc is a software that needs to be installed
conda install multiqc
# then multiqc runs on all fastQC output files and creates a report
multiqc quality/* -o .
```

***ROAR cannot open html files, so this needs to be copied over to a local machine so you can open it***

```# on your local terminal
scp YOURUSERNAME@submit.aci.ics.psu.edu:/pathway/to/multiqcreport/report.html YOURLOCALMACHINE/directory/
```

*Quality Check - What does the quality of reads look like? Is there adapter content or other problematic artifacts present? What kind of filtering will you need to do based on this report?*

### Optional: Remove adapter contamination

1. Adapter contamination is common and can introduce spurious ASVs, so it is a good idea to do this extra step. 
2. Use either cutadapt or Trimmomatic depending on filter parameters and type of adapter you want to remove. 
3. The parameters will vary based on the adapters and data. One example script is located at /gpfs/group/evk5387/default/scripts/cutadapt.sh

### Perform Filtering

1. Similar to adapter contamination, this step will depend on your data and software of choice. Popular filtering softwares include cutadapt, Trimmomatic, and data2's filterAndtrim().
2. Make a directory to store your filtered reads:

``` mkdir filtered ```

3. Filtering parameters will depend on the data and your personal choice. Consider:
- [ ] Are there poor quality bases at the beginning or end of the reads? If so, consider cutting off a number of bases.
- [ ] Are there poor quality bases in only some reads? If so, consider setting a quality threshold and truncating reads below.
- [ ] Are there short reads? If so, consider setting a minimum read length (this is necessary if you removed adapters in Step 2).
- [ ] Are there ambiguous bases? If so, consider removing/truncating (dada2 does not accept ambiguous bases so this step is necessary before continuing).

4. After filtering, redo fastqc to determine if the read quality is appropriate to move forward.

### Dada2 Pipeline
1. Dada2 is an R script that goes through a series of steps. When you first begin, it is helpful to copy 1-2 files to your local machine and go through the dada2 pipeline step by step with the online tutorial: https://benjjneb.github.io/dada2/tutorial_1_8.html
2. The scripts on ROAR have been optimized to run in a batch file in several steps. Due to difficulty with NovaSeq data, we have broken down the pipeline to two steps: error learning and dada, and then merging, chimera removal, ASV clustering, and taxonomic assignment. Scripts are located at: /gpfs/group/evk5387/default/scripts/dada2-Rscripts. To submit a PBS job to ACI-B for an R script, use the "submit-dada2.sh" bash file.
3. First, run error learning and dada dereplication. Inspect the error plots. *For NovaSeq or other difficult data, there are several ways to manipulate the error learning algorithm to force the model to fit different types of data. See https://github.com/benjjneb/dada2/issues/791 for more information.* This may take a few iterations to determine the best error learning model for your data. 
4. Next, run “post-dada.R” to perform merging, chimera removal, ASV clutering, and taxonomic assignment. This automatically uses the Silva v138 database located in /gpfs/group/evk5387/default/databases

*Quality Check - This script outputs a text file called “track-reads” that lists the number of reads retained through each step of the dada process. Take some time to inspect the number of reads that were lost in filtering, adapter removal, and the dada2 steps. If there is a step where the majority of the reads are lost, go back and tweak the parameters. 16S processing is an art and a science: there is a tradeoff between strict quality filtering and read retention. There are many online resources to help troubleshoot.*

### Finish and Move to Local Machine for Downstream Analysis
1. Take one last look through the steps you performed above and note the following: 
- [ ] Are all quality checks recorded?
- [ ] Have you written down the steps that you took (including all parameters for each piece of code) or saved the scripts to your own directory?
- [ ] Have you noted the version of each software you're using?
2. Clean up your scripts and directories.
3. Copy over the final products to your local machine to complete downstream analses in R (Recommended to work with the .RData files since they are built to go straight into phyloseq).

For further information, refer to R for Microbial Ecology
https://mibwurrepo.github.io/R_for_Microbial_Ecology/
