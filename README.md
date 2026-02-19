# PBEE dataset

## Download dataset and unzip files

### Step 1:

```
wget https://github.com/chavesejf/PBEE_datasets/releases/download/v1.1.0/PBEE_v1.1_dataset.tar.xz
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
  "3G6D": {                     <- name of the raw structure
    "structure": "_pbee_3G6D",  <- name of the processed structure
    "partner1": "HL",           <- chain ids that belongs to the receptor or ligand 
    "partner2": "A",            <- chain ids that belongs to the receptor or ligand
    "atoms": 4054,              <- number of atoms in the processed structure 
    "ions": 0,                  <- number of ions detected in the processed structure
    "int_ss_p1": {              <- secondary structure content of partner1 interface that contacts partner2
      "helix": 2,               <- alpha helix percentage
      "sheet": 26,
      "loop": 39
    },
    "int_ss_p2": {
      "helix": 28,
      "sheet": 0,
      "loop": 5
    },
    "int_restp_p1": {
      "aromatic": 13,
      "neutral": 11,
      "apolar": 15,
      "polar_pos": 2,
      "polar_neg": 9
    },
    "int_restp_p2": {
      "aromatic": 2,
      "neutral": 13,
      "apolar": 16,
      "polar_pos": 13,
      "polar_neg": 5
    },
    "int_aa_comp_p1": {
      "A": 1,
      "C": 0,
      "D": 5,
      "E": 0,
      "F": 2,
      "G": 3,
      "H": 1,
      "I": 1,
      "K": 0,
      "L": 1,
      "M": 1,
      "N": 2,
      "P": 0,
      "Q": 1,
      "R": 0,
      "S": 1,
      "T": 2,
      "V": 1,
      "W": 2,
      "Y": 3
    },
    "int_aa_comp_p2": {
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
    "seq_p1": {
      "H": "QVQLVESGGGLVQPGGSLRLSCAASGFTFNSYWINWVRQAPGKGLEWVSGIAYDSSNTLYADSVKGRFTISRDNSKNTLYLQMNSLRAEDTAVYYCARGLGAFHWDMQPDYWGQGTLVTVSSASTKGPSVFPLAPSSKSTSGGTAALGCLVKDYFPEPVTVSWNSGALTSGVHTFPAVLQSSGLYSLSSVVTVPSSSLGTQTYICNVNHKPSNTKVDKKVEPK",
      "L": "SYELTQPPSVSVAPGQTARISCSGDNIGGTFVSWYQQKPGQAPVLVIYDDNDRPSGIPERFSGSNSGNTATLTISGTQAEDEADYYCGTWDMVTNNVFGGGTKLTVLGQPKAAPSVTLFPPSSEELQANKATLVCLISDFYPGAVTVAWKADSSPVKAGVETTTPSKQSNNKYAASSYLSLTPEQWKSHRSYSCQVTHEGSTVEKTVAPT"
    },
    "seq_p2": {
      "A": "VPPSTALRELIEELVNITQNQKAPLCNGSMVWSINLTAGMYCAALESLINVSGCSAIEKTQRMLSGFCPHKVSAGQFSSLHVRDTKIEVAQFVKDLLLHLKKLFRE"
    },
    "time": {
      "pre_processing": 1.834,
      "post_processing": null
    },
    "rosetta_int_descriptors": {
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
    "dG_exp": -14.638
  }
```
