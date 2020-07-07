# Epigenome_analysis_infer_transcriptome

Goal of the pipeline
<br/><br/>
Analysis pipeline (workflow management using Snakemake)
  - Preprocessing to remove duplicate and supplementary reads (samtools, biobambam)
  - Input for the inference: pre-processed bam files (bam)
<br/><br/>
PART0. Extract single-cell and subclonal copy-number variations
<br/><br/>
PART1. Infer transcriptome with pseudo-bulk population
  - Feature1 : samtools merge for pseudo-bulk NO, Strand_seq_deeptool_Genes_for_CNN.pl
    - Make_ML_Features_BCLL01 (processing and normalization to make Feature1)
    - For normalization total mapped read needs to be calculated (Strand_seq_deeptool_chr_length.pl)
  - Feature2 : single-cell variance : Deeptool_matrix_CNN_C0.R
  - Combine five layers of feature sets
<br/><br/>
PART2. Infer transcriptome at the single-cell level
  - Strand_seq_deeptool_Genes_for_CNN.pl
  - R_ML_Features_sc.R (This is for normalization)
  - Combine four layers of feature sets
<br/><br/>  
PART3. Infer transcriptome using CNN
  - Deeplearning_Nucleosome_with_mono_var_GC_CpG_RT_leave_Chr1_out_BCLL01_CNnorm_sc_wovar_ypred.py
