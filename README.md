# TimesVector 1.5
README FILE

TimesVector v1.5

This is a README file for quick installation and running TimesVector. The full manual with description and examples of input/output file formats are available under the 'docs' directory or the website http://biohealth.snu.ac.kr/software/TimesVector/.

TimesVector is written in Python3
Several pre-requisites required by TimesVector as listed below:

	Required python modules:
	1) Scipy
	2) Numpy

	Required R libraries:
	1) skmeans
	2) ggplot2


TimesVector is currently only available for Linux platforms.
To install TimesVector execute the following commands. 
$ tar -xzvf TimesVector_v1.5.tar.gz
$ export TIMESVECTOR=/<path to TimesVector>/bin
$ export PATH=$PATH:$TIMESVECTOR


Usage of TimesVector:
$ TimesVector
usage: bin/TimesVector [ h | gctdko ]

This script runs TimesVector.

Paramters(all mandatory):
   -g      The path to the gene expression file
   -c      Number of classes (INT)
   -t      Number of time points per class (INT)
   -d      Type of data ['m': Microarray, 'n': NGS]
   -k      K numer of clusters (INT)
   -o      Output directory for results
   -h      Shows this message


All parameters are mandatory.

	-c is the number of sample conditions (or phenotypes) in the gene expression file (INTEGER)
	-t is the number of time points in each sample condition (INTEGER)
	-d is the type of the data. If gene expression data is from microarray data ‘m’. If data is from high throughput sequencing data (i.e., RNA-seq) ‘n’ (CHARACTER).
	-k is the number of clusters desired to detect (INTEGER). We recommend to choose a K close to the following equation.
		K = −85.71 + 28.57x, where x is the product of C (# of conditions) and T (# of time points).
	-o is the output directory for the clustering results

An example:
The gene expression file of GSE11651 is included in the ‘example’ directory, “GSE11651_data.txt”.
It consists of 5 conditions, each with 3 time points.
The command line for executing TimesVector using the example data will be as follows,
$ TimesVector -g example/GSE11651_data.txt -c 5 -t 3 -d m -k 300 -o results

With large K's (>200) TimesVector takes several minutes to run, so please be patient.
