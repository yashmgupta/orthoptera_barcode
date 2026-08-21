# Orthoptera 16S rRNA DNA Barcoding — sequencing and assembly dataset

This repository uses provenance-preserving filenames derived from the original sequencing file names.

## Naming rule

The original sequencing provenance is retained:

`TSN20260519-0852-00054_<SAMPLE>_20260521-BAN6_<WELL>_<WELL>_i78`

Only the technical read suffix is standardized for GitHub:

- Forward read: `<PROVENANCE_BASE>_R1.fastq.gz`
- Reverse read: `<PROVENANCE_BASE>_R2.fastq.gz`
- MEGAHIT assembly: `<PROVENANCE_BASE>_MEGAHIT_min500_contigs.fasta`
- BLAST output: `<PROVENANCE_BASE>_BLASTN_MegaBLAST_core_nt.tsv`

The browser/download duplicate suffix such as `.fq(2).gz` should **not** be retained because `(2)` is a local duplicate-download marker rather than biological metadata.

## Sample provenance

| Sample | Provenance base |
|---|---|
| B1 | `TSN20260519-0852-00054_B1_20260521-BAN6_B10_B10_i78` |
| B2 | `TSN20260519-0852-00054_B2_20260521-BAN6_C10_C10_i78` |
| C9-2 | `TSN20260519-0852-00054_C9-2_20260521-BAN6_A11_A11_i78` |
| Cricket-Unknown | `TSN20260519-0852-00054_Cricket-Unknown_20260521-BAN6_E10_E10_i78` |
| GH1 | `TSN20260519-0852-00054_GH1_20260521-BAN6_F10_F10_i78` |
| GH2 | `TSN20260519-0852-00054_GH2_20260521-BAN6_G10_G10_i78` |
| MC1-1 | `TSN20260519-0852-00054_MC1-1_20260521-BAN6_H10_H10_i78` |
| MKM10 | `TSN20260519-0852-00054_MKM10_20260521-BAN6_A10_A10_i78` |
| T2 | `TSN20260519-0852-00054_T2_20260521-BAN6_D10_D10_i78` |

## Analysis

Nine paired-end datasets were assembled separately in Galaxy using MEGAHIT with default parameters except minimum contig length = 500 bp. Informative contigs were searched with NCBI BLASTN using MegaBLAST against `core_nt`.

## Repository structure

```text
.
├── README.md
├── metadata/
│   ├── rename_map.tsv
│   └── sample_metadata.tsv
└── data/
    ├── raw_fastq/
    ├── assemblies/
    └── blast_results/
```
