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
  "3G6D": {                           <- name of the raw structure
    "structure": "_pbee_3G6D",        <- name of the processed structure
    "partner1": "str",                <- chain ids that belongs to the receptor or ligand (p1)
    "partner2": "str",                <- chain ids that belongs to the receptor or ligand (p2)
    "atoms":    "int",                <- number of atoms in the processed structure 
    "ions":     "int",                <- number of ions detected in the processed structure
    "int_ss_p1": {                    <- secondary structure content of the interface of p1 that interacts with p2
      "helix": "int",                 <- alpha-helix percentage
      "sheet": "int",                 <- beta-sheet percentage
      "loop":  int                    <- loop percentage
    },
    "int_ss_p2": {                    <- secondary structure content of the interface of p2 that interacts with p1
      "helix": "int",                 <- same as int_ss_p1
      "sheet": "int",
      "loop":  "int"
    },
    "int_restp_p1": {                 <- residue type content of the interface of p1 that interacts with p2
      "aromatic":  "int",             <- percentage of aromatic residues
      "neutral":   "int",             <- percentage of neutral residues
      "apolar":    "int",             <- percentage of apolar residues
      "polar_pos": "int",             <- percentage of polar positive residues
      "polar_neg": "int"              <- percentage of polar negative residues
    },
    "int_restp_p2": {                 <- residue type content of the interface of p2 that interacts with p1
      "aromatic":  "int",             <- same as int_restp_p1
      "neutral":   "int",
      "apolar":    "int",
      "polar_pos": "int",
      "polar_neg": int
    },
    "int_aa_comp_p1": {               <- amino acid composition (%) of the interface of p1 that interacts with p2
      "A": "int",                     <- total ALA
      "C": "int",                     <- "     CYS
      "D": "int",                     <- "     ASP
      "E": "int",                     <- "     GLU
      "F": "int",                     <- "     PHE
      "G": "int",                     <- "     GLY
      "H": "int",                     <- "     HIS
      "I": "int",                     <- "     ILE
      "K": "int",                     <- "     LYS
      "L": "int",                     <- "     LEU
      "M": "int",                     <- "     MET
      "N": "int",                     <- "     ASN
      "P": "int",                     <- "     PRO
      "Q": "int",                     <- "     GLN
      "R": "int",                     <- "     ARG
      "S": "int",                     <- "     SER
      "T": "int",                     <- "     THR
      "V": "int",                     <- "     VAL
      "W": "int",                     <- "     TRP
      "Y": "int"                      <- "     TYR
    },
    "int_aa_comp_p2": {               <- amino acid composition (%) of the interface of p2 that interacts with p1
      "A": "int",
      "C": "int",
      "D": "int",
      "E": "int",
      "F": "int",
      "G": "int",
      "H": "int",
      "I": "int",
      "K": "int",
      "L": "int",
      "M": "int",
      "N": "int",
      "P": "int",
      "Q": "int",
      "R": "int",
      "S": "int",
      "T": "int",
      "V": "int",
      "W": "int",
      "Y": int
    },
    "int_seq_p1": {},                 <- primary structure content (per chain) of the interface of p1 that interacts with p2
    "int_seq_p2": {},                 <- primary structure content (per chain) of the interface of p2 that interacts with p1
    "seq_p1": {},                     <- primary structure content (per chain) of the p1
    "seq_p2": {},                     <- primary structure content (per chain) of the p2
    "time": {                         <- time elapsed to complete the stages of the PBE pipeline
      "pre_processing": "float",
      "post_processing": null
    },
    "dG_exp":                       "float"     <- experimental binding affinity of the complex (p1:p2)
    "rosetta_int_descriptors": {                <- scores and interface descriptors obtained with Rosetta
      "dslf_fa13":                  "float",
      "fa_atr":                     "float",
      "fa_dun_dev":                 "float",
      "fa_dun_rot":                 "float",
      "fa_dun_semi":                "float",
      "fa_elec":                    "float",
      "fa_intra_atr_xover4":        "float",
      "fa_intra_elec":              "float",
      "fa_intra_rep_xover4":        "float",
      "fa_intra_sol_xover4":        "float",
      "fa_rep":                     "float",
      "fa_sol":                     "float",
      "lk_ball":                    "float",
      "lk_ball_bridge":             "float",
      "lk_ball_bridge_uncpl":       "float",
      "lk_ball_iso":                "float",
      "hbond_bb_sc":                "float",
      "hbond_lr_bb":                "float",
      "hbond_sc":                   "float",
      "hbond_sr_bb":                "float",
      "hxl_tors":                   "float",
      "omega":                      "float",
      "p_aa_pp":                    "float",
      "rama_prepro":                "float",
      "ref":                        "float",
      "total_score":                "float",
      "cms":                        "float",
      "ifa_complex_normalized":     "float",
      "ifa_dG_cross":               "float",
      "ifa_dG_separated":           "float",
      "ifa_dSASA_hphobic":          "float",
      "ifa_dSASA_int":              "float",
      "ifa_dSASA_polar":            "float",
      "ifa_delta_unsatHbonds":      "float",
      "ifa_hbond_E_fraction":       "float",
      "ifa_hbonds_int":             "float",
      "ifa_nres_all":               "float",
      "ifa_nres_int":               "float",
      "ifa_packstat":               "float",
      "ifa_per_residue_energy_int": "float",
      "ifa_sc_value":               "float",
      "ifa_side1_normalized":       "float",
      "ifa_side1_score":            "float",
      "ifa_side2_normalized":       "float",
      "ifa_side2_score":            "float"
    },
  }
```
