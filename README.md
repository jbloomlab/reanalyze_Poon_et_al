# Re-analysis of Poon et al data
Re-analysis of the data from the [Poon et al, Nature Genetics](https://www.nature.com/articles/ng.3479) study.
It focuses on characterizing abnormal read-pairing across samples in the raw deep sequencing data.

This analysis is performed by [Jesse Bloom](https://research.fhcrc.org/bloom/en.html), and is a fully independent version of the analysis implemented by Katherine Xue.
The rationale for having Jesse and Katherine independently perform similar analyses is to protect against some sort of bug or problem in one of the analyses.

The analysis is performed by the [Jupyter notebook](www.jupyter.org) [analysis_notebook.ipynb](analysis_notebook.ipynb).
This notebook documents each step, so just [click here to read it](analysis_notebook.ipynb) to understand the steps and results.

You can run the entire analysis just by running [analysis_notebook.ipynb](analysis_notebook.ipynb) provided that you install the required Python packages listed in the first cell of the notebook, and enter a valid Synapse user name and password for the data download.

All files created by [analysis_notebook.ipynb](analysis_notebook.ipynb) are placed in a subdirectory called `./results/`.
The large downloaded data files are not tracked in this repository, but the following results are tracked:

  - [./results/read_stats/shared_readpairs.csv](./results/read_stats/shared_readpairs.csv) gives the number of reads that are paired with another read in each other sample. The diagonal elements are reads that are paired within the same sample. So for each read pair that is shared within the sample, there is an increment of 2 on the diagonal. For each read pair that is shared with another sample, there is an increment of 1 on **both** of the off-diagonal elements corresponding to that read pair.

  - [./results/read_stats/unpaired_reads.csv](./results/read_stats/unpaired_reads.csv) gives the number of reads for each sample that are **not** paired with a read in any other sample.

  - [./results/plots/](./results/plots/) has image files for the plots shown in [analysis_notebook.ipynb](analysis_notebook.ipynb).
