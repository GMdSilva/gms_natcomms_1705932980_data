Sample raw data for results discussed in Predicting Relative Populations of Protein Conformations without a Physics Engine Using AlphaFold2

# Preface:

The approach we describe in the manuscript does not require any specialized software besides the ones generally used to make predictions with AlphaFold 2. Namely, it requires a Multiple Sequence Alignment (MSA) that can be generated through a variety of methods (such as MMSEQS2 [https://github.com/soedinglab/MMseqs2] or jackhmmr [https://github.com/EddyRivasLab/hmmer/tree/master]) and the AlphaFold2 https://github.com/lipan6461188/AlphaFold-StepByStep executable itself.

In our manuscript, we use jackhmmr to generate the MSAs, and run AlphaFold2 via the colabfold_batch wrapper https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/batch/AlphaFold2_batch.ipynb. The following content will pertain to that specific implementation.

# System Requirements:

RAM: at least 32 GB (16 GB with --db_preset=reduced_dbs).

CPU: A modern multicore Intel/AMD CPU.

GPU: nVidia (e.g. A100), the more GPU RAM it has the longer proteins you can fold.

Disk: 3 TB of disk space, ideally an SSD for faster MSA search (1 TB with reduced_dbs) if querying local databases. If using the Google Collab Notebook , the space requirements are much lower (about 10 GBs should be sufficient).

# Installation Guide:

Installation instructions for jackhmmr and/or collabfold_batch can be found at the following repositories:

### jackhmmr
https://github.com/EddyRivasLab/hmmer/tree/master

### collabfold_batch
https://github.com/lipan6461188/AlphaFold-StepBySte

We strongly recommend the use of our Google Collab notebook for generating MSAs. Installation for its usage can be found on the notebook itself.

### Collab

https://colab.research.google.com/drive/1BhOsy9UL41mE0UN5eYiMxwpFXkQAA8iE

or

https://github.com/GMdSilva/rel_state_pop_af2_raw_data/blob/main/rel_state_populations_af2_msa_generation.ipynb


# Demo:

1. Run the Google Collab notebook with default parameters, exporting the MSA to Google Drive as instructed in the notebook itself.
2. Run collabfold_batch or another implementation of AF2 using the MSA generated on 1 as an input, following the instructions on the Google Collab for setting the AF2 prediction parameters.
3. Analyze predictions using a software of choice (PyMol 2.0 or above recommended).

# Instructions for Reproduction:

1. Run the Google Collab notebook with default parameters using the sequences shared in [sequences](https://github.com/GMdSilva/rel_state_pop_af2_raw_data/tree/main/sequences), exporting the MSA to Google Drive as instructed in the notebook itself.
2. Run collabfold_batch or another implementation of AF2 using the MSA generated on 1 as an input, following the command described in [here](https://github.com/GMdSilva/rel_state_pop_af2_raw_data/blob/main/scripts/colabfold_batch_command.sh)https://github.com/GMdSilva/rel_state_pop_af2_raw_data/blob/main/scripts/colabfold_batch_command.sh. Adjust input and output names as needed.
