# PBEE dataset
Dataset used to train and validate the PBEE pipeline. See publication [here](https://pubs.acs.org/doi/10.1021/acs.jcim.4c01641).


## Download dataset and unzip files

### Step 1:

```
wget https://github.com/chavesejf/PBEE_datasets/releases/download/v1.1.0/PBEE_v1.1.0_dataset.tar.xz
```

### Step 2:

```
tar -xvJf PBEE_v1.1_dataset.tar.xz
```

### Step 3:

The following directory tree will be created:

```bash
PBEE_datasets/
├── v1.1/
│   ├── 0_input_structures/
│   │   ├── test/
│   │   └── train/
│   │
│   ├── 1_processed_structures/
│   │   ├── test/
│   │   └── train/
│   │
│   └── 3_data/
│       ├── test/
│       └── train/
```

## Data description

### 0_input_structures/

This directory contains the raw structures used in the training and testing stages, all from specific databases (PDBbind, SKEMPI, AffinityBenchmark, and PRODIGY) previously published.

### 1_processed_structures/

This directory contains structures that have been processed by the PBEE pipeline.

### 3_data/

This directory contains .json files with structural information about the processed structures. Below is a description of the file contents:

```json
{
  "3G6D": {                         <- name of the raw structure
    "structure": "_pbee_3G6D",      <- name of the processed structure
    "partner1": "HL",               <- chain ids that belongs to the receptor or ligand (p1)
    "partner2": "A",                <- chain ids that belongs to the receptor or ligand (p2)
    "atoms": 4054,                  <- number of atoms in the processed structure 
    "ions": 0,                      <- number of ions detected in the processed structure
    "int_ss_p1": {                  <- secondary structure content of the interface of p1 that interacts with p2
      "helix": 2,                   <- alpha-helix percentage
      "sheet": 26,                  <- beta-sheet percentage
      "loop": 39                    <- loop percentage
    },
    "int_ss_p2": {                  <- same as int_ss_p1
      "helix": 28,
      "sheet": 0,
      "loop": 5
    },
    "int_restp_p1": {               <- residue type content of the interface of p1 that interacts with p2
      "aromatic": 13,               <- percentage of aromatic residues
      "neutral": 11,                <- percentage of neutral residues
      "apolar": 15,                 <- percentage of apolar residues
      "polar_pos": 2,               <- percentage of polar positive residues
      "polar_neg": 9                <- percentage of polar negative residues
    },
    "int_restp_p2": {               <- same as int_restp_p1
      "aromatic": 2,
      "neutral": 13,
      "apolar": 16,
      "polar_pos": 13,
      "polar_neg": 5
    },
    "int_aa_comp_p1": {             <- amino acid composition of the interface of p1 that interacts with p2
      "A": 1,                       <- total ALA
      "C": 0,                       <- "     CYS
      "D": 5,                       <- "     ASP
      "E": 0,                       <- "     GLU
      "F": 2,                       <- "     PHE
      "G": 3,                       <- "     GLY
      "H": 1,                       <- "     HIS
      "I": 1,                       <- "     ILE
      "K": 0,                       <- "     LYS
      "L": 1,                       <- "     LEU
      "M": 1,                       <- "     MET
      "N": 2,                       <- "     ASN
      "P": 0,                       <- "     PRO
      "Q": 1,                       <- "     GLN
      "R": 0,                       <- "     ARG
      "S": 1,                       <- "     SER
      "T": 2,                       <- "     THR
      "V": 1,                       <- "     VAL
      "W": 2,                       <- "     TRP
      "Y": 3                        <- "     TYR
    },
    "int_aa_comp_p2": {             <- same as int_aa_comp_p1
      "A": 0,
      "C": 0,
      "D": 0,
      "E": 2,
      "F": 1,
      "G": 0,
      "H": 0,
      "I": 1,
      "K": 3,
      "L": 2,
      "M": 0,
      "N": 2,
      "P": 2,
      "Q": 2,
      "R": 2,
      "S": 0,
      "T": 1,
      "V": 1,
      "W": 0,
      "Y": 0
    },
    "seq_p1": {                     <- primary structure content (per chain) of the p1
      "H": "VNVDKKVEPK",               
      "L": "SHRSYSCAPT"
    },
    "seq_p2": {                     <- primary structure content (per chain) of the p2
      "A": "LLHLKKLFRE"
    },
    "time": {                       <- time elapsed to complete the stages of the PBE pipeline
      "pre_processing": 1.834,
      "post_processing": null
    },
    "rosetta_int_descriptors": {    <- scores and interface descriptors obtained with Rosetta
      "dslf_fa13": -4.455,
      "fa_atr": -2821.082,
      "fa_dun_dev": 79.366,
      "fa_dun_rot": 263.016,
      "fa_dun_semi": 411.509,
      "fa_elec": -861.902,
      "fa_intra_atr_xover4": -153.22,
      "fa_intra_elec": -131.503,
      "fa_intra_rep_xover4": 50.461,
      "fa_intra_sol_xover4": 100.222,
      "fa_rep": 303.659,
      "fa_sol": 1873.337,
      "lk_ball": 1037.579,
      "lk_ball_bridge": -4.595,
      "lk_ball_bridge_uncpl": -30.544,
      "lk_ball_iso": -1079.741,
      "hbond_bb_sc": -73.379,
      "hbond_lr_bb": -234.516,
      "hbond_sc": -64.936,
      "hbond_sr_bb": -108.057,
      "hxl_tors": 167.805,
      "omega": 45.571,
      "p_aa_pp": -131.677,
      "rama_prepro": 92.469,
      "ref": -104.045,
      "total_score": -1370.059,
      "cms": 488.145,
      "ifa_complex_normalized": -2.542,
      "ifa_dG_cross": 0.0,
      "ifa_dG_separated": -59.296,
      "ifa_dSASA_hphobic": 1015.057,
      "ifa_dSASA_int": 1844.103,
      "ifa_dSASA_polar": 829.046,
      "ifa_delta_unsatHbonds": 5,
      "ifa_hbond_E_fraction": 0.248,
      "ifa_hbonds_int": 11,
      "ifa_nres_all": 539,
      "ifa_nres_int": 63,
      "ifa_packstat": 0.616,
      "ifa_per_residue_energy_int": -2.089,
      "ifa_sc_value": 0.611,
      "ifa_side1_normalized": -2.275,
      "ifa_side1_score": -75.059,
      "ifa_side2_normalized": -1.886,
      "ifa_side2_score": -56.57
    },
    "dG_exp": -14.638               <- experimental binding affinity of the complex (p1:p2)
  }
```
