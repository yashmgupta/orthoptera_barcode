# Orthoptera 16S rRNA Barcoding Dataset

This repository contains the sequence data and analysis outputs generated from a mitochondrial 16S rRNA DNA-barcoding study of Orthopteran samples.

Only the `data/` directory is included in this repository. The dataset contains paired-end sequencing reads, MEGAHIT assemblies, and NCBI BLAST results for nine samples.

## Dataset structure

```text
data/
├── raw_fastq/
│   ├── *_R1.fastq.gz
│   └── *_R2.fastq.gz
├── assemblies/
│   └── *_MEGAHIT_min500_contigs.fasta
└── blast_results/
    └── *_BLASTN_MegaBLAST_core_nt.tsv
```

## Samples

The dataset contains nine paired-end samples:

- B1
- B2
- C9-2
- Cricket-Unknown
- GH1
- GH2
- MC1-1
- MKM10
- T2

Full sequencing-provenance names are retained in the filenames.

Example:

- `TSN20260519-0852-00054_B1_20260521-BAN6_B10_B10_i78_R1.fastq.gz`
- `TSN20260519-0852-00054_B1_20260521-BAN6_B10_B10_i78_R2.fastq.gz`

The same provenance base is used for the corresponding assembly and BLAST result files.

Example:

- `TSN20260519-0852-00054_B1_20260521-BAN6_B10_B10_i78_MEGAHIT_min500_contigs.fasta`
- `TSN20260519-0852-00054_B1_20260521-BAN6_B10_B10_i78_BLASTN_MegaBLAST_core_nt.tsv`

## Experimental background

A mitochondrial PCR marker was used to amplify Orthopteran DNA prior to sequencing.

Primer sequences:

- Forward: `5'-ATGCTACCTTTGCACGGTCA-3'`
- Reverse: `5'-TGTGTACATATCGCCCGTCG-3'`

PCR products selected for sequencing were subjected to paired-end sequencing, producing the nine paired FASTQ datasets included here.

## Sequence assembly

Each paired-end sample was assembled separately using MEGAHIT on the Galaxy platform.

Assembly settings:

- Input: paired-end FASTQ reads
- Assembler: MEGAHIT
- Samples assembled independently
- MEGAHIT parameters: default settings
- Minimum contig length: 500 bp

Assembly outputs are stored in `data/assemblies/`.

Files are named using the sequencing provenance followed by:

- `_MEGAHIT_min500_contigs.fasta`

## NCBI BLAST analysis

Informative assembled contigs were queried against the NCBI nucleotide database using:

- Program: BLASTN
- Algorithm: MegaBLAST
- Database: core_nt

BLAST result files are stored in `data/blast_results/`.

Files are named using:

- `_BLASTN_MegaBLAST_core_nt.tsv`

## Best BLAST evidence and working molecular interpretations

The table below summarizes the strongest retained BLAST evidence for each sample and the corresponding working molecular interpretation.

| Sample | Best MegaBLAST evidence | Working molecular interpretation |
|---|---|---|
| B1 | `k141_0` (1,012 bp); *Gryllus bimaculatus* mitochondrion, OZ281583.1; coverage 91%; identity 99.78% | *Gryllus bimaculatus* |
| B2 | `k141_0` (1,031 bp); *Gryllus bimaculatus* mitochondrion, OZ281583.1; coverage 89%; identity 99.78% | *Gryllus bimaculatus* |
| GH1 | `k141_0` (1,034 bp); *Spathosternum prasiniferum prasiniferum* mitochondrion, NC_046532.1; coverage 99%; identity 98.96% | *Spathosternum prasiniferum prasiniferum* |
| GH2 | `k141_0` (1,027 bp); *Spathosternum prasiniferum prasiniferum* mitochondrion, NC_046532.1; coverage 100%; identity 99.04% | *Spathosternum prasiniferum prasiniferum* |
| MC1-1 | `k141_1` (718 bp), 100% coverage / 92.62% identity; and `k141_2` (942 bp), 94% coverage / 95.39% identity. Both best match *Gryllotalpa orientalis*, ON210982.1. | Closest BLAST match to *Gryllotalpa orientalis*; species-level identification uncertain |
| MKM10 | `k141_4` (922 bp); *Velarifictorus hemelytrus* mitochondrion, NC_030762.1; coverage 99%; identity 82.62% | Closest BLAST match to *Velarifictorus hemelytrus*; species-level identification uncertain |
| T2 | `k141_1` (973 bp); *Teleogryllus mitratus* mitochondrion, PP297527.1; coverage 94%; identity 99.67% | *Teleogryllus mitratus* |
| C9-2 | `k141_6` (1,095 bp); *Rhaphidophoridae* sp. mitochondrion, OR865114.1; coverage 100%; identity 99.83% | *Rhaphidophoridae* sp.; species unresolved |
| Cricket-Unknown | `k141_0` (898 bp); *Teleogryllus mitratus* mitochondrion, PX591113.1; coverage 97%; identity 88.47% | Closest BLAST match to *Teleogryllus mitratus*; species-level identification uncertain |

These are working molecular interpretations based on the retained BLAST results. They should not automatically be treated as formal taxonomic identifications without consideration of sequence identity, query coverage, reference quality, morphology, and additional phylogenetic evidence.

## File naming convention

Raw reads:

- `<PROVENANCE_BASE>_R1.fastq.gz`
- `<PROVENANCE_BASE>_R2.fastq.gz`

Assemblies:

- `<PROVENANCE_BASE>_MEGAHIT_min500_contigs.fasta`

BLAST results:

- `<PROVENANCE_BASE>_BLASTN_MegaBLAST_core_nt.tsv`

The original browser/download suffix such as `.fq(2).gz` was not retained because `(2)` represents a local duplicate-download filename and is not biological or sequencing metadata.

## Data use

Users of this dataset should preserve the provenance-based sample names when linking raw reads, assemblies, and BLAST results.

For reproducibility, it is recommended that checksum values be generated for all FASTQ and FASTA files after final upload.

## Citation

If these data are used in a publication, presentation, thesis, or downstream analysis, please cite the associated research output or dataset record when available.

## Contact

For questions about sample provenance, laboratory procedures, or interpretation of the data, please contact the corresponding research group.
