# PBEE dataset
Dataset used to train and validate the PBEE pipeline. See publication [here](https://pubs.acs.org/doi/10.1021/acs.jcim.4c01641).


## Download dataset and unzip files

### Step 1:

```
wget https://github.com/chavesejf/PBEE_datasets/releases/download/v1.1.0/PBEE_v1.1.0_dataset.tar.xz
```

### Step 2:

```
tar -xvJf PBEE_v1.1.0_dataset.tar.xz
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
    "partner1": str,                <- chain ids that belongs to the receptor or ligand (p1)
    "partner2": str,                <- chain ids that belongs to the receptor or ligand (p2)
    "atoms":    int,                <- number of atoms in the processed structure 
    "ions":     int,                <- number of ions detected in the processed structure
    "int_ss_p1": {                  <- secondary structure content of the interface of p1 that interacts with p2
      "helix": int,                 <- alpha-helix percentage
      "sheet": int,                 <- beta-sheet percentage
      "loop":  int                  <- loop percentage
    },
    "int_ss_p2": {                  <- same as int_ss_p1
      "helix": int,
      "sheet": int,
      "loop":  int
    },
    "int_restp_p1": {               <- residue type content of the interface of p1 that interacts with p2
      "aromatic":  int,             <- percentage of aromatic residues
      "neutral":   int,             <- percentage of neutral residues
      "apolar":    int,             <- percentage of apolar residues
      "polar_pos": int,             <- percentage of polar positive residues
      "polar_neg": int              <- percentage of polar negative residues
    },
    "int_restp_p2": {               <- same as int_restp_p1
      "aromatic":  int,
      "neutral":   int,
      "apolar":    int,
      "polar_pos": int,
      "polar_neg": int
    },
    "int_aa_comp_p1": {             <- amino acid composition of the interface of p1 that interacts with p2
      "A": int,                     <- total ALA
      "C": int,                     <- "     CYS
      "D": int,                     <- "     ASP
      "E": int,                     <- "     GLU
      "F": int,                     <- "     PHE
      "G": int,                     <- "     GLY
      "H": int,                     <- "     HIS
      "I": int,                     <- "     ILE
      "K": int,                     <- "     LYS
      "L": int,                     <- "     LEU
      "M": int,                     <- "     MET
      "N": int,                     <- "     ASN
      "P": int,                     <- "     PRO
      "Q": int,                     <- "     GLN
      "R": int,                     <- "     ARG
      "S": int,                     <- "     SER
      "T": int,                     <- "     THR
      "V": int,                     <- "     VAL
      "W": int,                     <- "     TRP
      "Y": int                      <- "     TYR
    },
    "int_aa_comp_p2": {             <- same as int_aa_comp_p1
      "A": int,
      "C": int,
      "D": int,
      "E": int,
      "F": int,
      "G": int,
      "H": int,
      "I": int,
      "K": int,
      "L": int,
      "M": int,
      "N": int,
      "P": int,
      "Q": int,
      "R": int,
      "S": int,
      "T": int,
      "V": int,
      "W": int,
      "Y": int
    },
    "int_seq_p1": {
      "G": str
    },
    "int_seq_p2": {
      "R": str
    },
    "seq_p1": {                     <- primary structure content (per chain) of the p1
      "H": str
    },
    "seq_p2": {                     <- primary structure content (per chain) of the p2
      "A": str
    },
    "time": {                       <- time elapsed to complete the stages of the PBE pipeline
      "pre_processing": float,
      "post_processing": null
    },
    "dG_exp": float                 <- experimental binding affinity of the complex (p1:p2)
    "rosetta_int_descriptors": {    <- scores and interface descriptors obtained with Rosetta
      "dslf_fa13":  float,
      "fa_atr":     float,
      "fa_dun_dev": float,
      "fa_dun_rot": 263.016,
      "fa_dun_semi": 411.509,
      "fa_elec":             float,
      "fa_intra_atr_xover4": float,
      "fa_intra_elec":       float,
      "fa_intra_rep_xover4": float,
      "fa_intra_sol_xover4": float,
      "fa_rep":              float,
      "fa_sol":              float,
      "lk_ball":             float,
      "lk_ball_bridge":      float,
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
  }
```
