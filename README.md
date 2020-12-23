scNOVA
====================================

scNOVA : Single-Cell Nucleosome Occupancy and genetic Variation Analysis - summarized in a single [Snakemake](https://bitbucket.org/snakemake/snakemake) pipeline.


## Overview of this workflow
PART0. Pre-requirement step - preparation of single-cell genetic information:
Mosaicatcher: https://github.com/friendsofstrandseq/mosaicatcher-pipeline
<br/><br/>
PART1. Read preprocessing
<br/><br/>
PART2. Read counting to generate single-cell genebody NO
<br/><br/>
PART3. Infer expressed genes of subclones
<br/><br/>
PART4. DE analysis of subclones
<br/><br/>
Main output (GM20509 example data)
1. Single-cell level NO table : result/GM20509_sort_geneid.txt (20201223 updated)
2. Infer expression probability for each clones : result_CNN/DNN_train80_output_ypred_clone1_annot.txt, result_CNN/DNN_train80_output_ypred_clone2_annot.txt
3. Infer differential expression table : result/Result_scNOVA_infer_expression_table.txt
4. Heatmap and UMAP visualization of significant hits : result_plots/Result_scNOVA_plots_GM20509.pdf
<br/><br/> 
## System requirements
This workflow is mean to be run in a Unix-based operating system.


## Installation
1. unix based tools : SAMtools/1.3.1-foss-2016b, biobambam2/2.0.76-foss-2016b, deeptools/2.5.1-foss-2016b-Python-2.7.12
2. python packages : cuDNN, CUDA, TensorFlow, scikit-learn, matplotlib
3. R packages : DESeq2, matrixStats, pheatmap, gplots, umap, Rtsne, factoextra, pracma 


## Setup
1. Download this pipeline
2. Add your single-cell data (input_bam folder)
3. Add the subclonality information (input_user folder)
4. Change the project name in the Snakefile
5. Launch the run_pipeline.sh script

## References

For information on scTRIP see

> Sanderes *et al.*, 2019 (doi: https://doi.org/10.1038/s41587-019-0366-x)





