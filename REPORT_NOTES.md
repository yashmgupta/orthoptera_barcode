# Report evidence and audit notes

## Inspected repository contents

- `README.md`
- `data/raw_fastq/`: 18 `.fq.gz` files, representing nine forward/reverse read pairs by filename and the README's sample description
- `data/assemblies/`: nine `.fasta` files
- `data/blast_results/Orthoptera_BLAST_Screenshot_Compilation.docx`
- Root directory and repository status, to identify additional files and existing citation, license, package, and test metadata

The inspected repository contained only the README and the `data/` tree before the report source files were added. No existing `CITATION.cff` or license file was identified.

## Verified facts used in the report

- The README describes a mitochondrial 16S rRNA DNA-barcoding study of Orthopteran samples and names nine samples: B1, B2, C9-2, Cricket-Unknown, GH1, GH2, MC1-1, MKM10, and T2.
- The raw-read directory contains 18 gzipped FASTQ files; names occur in R1/R2 pairs for the nine README sample labels.
- The assembly directory contains nine FASTA files. An example is `data/assemblies/Galaxy29-[Assembly with MEGAHIT on dataset 11 and 12].fasta`.
- The README says samples were assembled independently with MEGAHIT on Galaxy, using default settings and a minimum contig length of 500 bp.
- The README says informative assembled contigs were queried with BLASTN/MegaBLAST against NCBI `core_nt`.
- `data/blast_results/Orthoptera_BLAST_Screenshot_Compilation.docx` contains the compiled screenshot evidence described by the README.
- The README characterizes per-sample taxonomic interpretations as working interpretations and cautions against treating them automatically as formal identifications.
- No source code, package metadata, test suite, or license file was identified in the inspected repository contents.
- No PDF renderer (`pandoc`, `quarto`, `xelatex`, `pdflatex`, or `wkhtmltopdf`) was available in the execution environment; therefore no PDF artifact was generated.

## Limitations and missing metadata

- Author name, ORCID, affiliation, report identifier, publication date, repository release/version, license, DOI, Zenodo record, and publication page URL are not specified in the inspected repository. Explicit placeholders are retained for these values.
- The public repository URL is supplied in the landing-page source as the repository's GitHub address, but no canonical URL is documented inside the repository; report metadata retains `[PUBLIC_REPOSITORY_URL]`.
- No software version is documented because the repository is a research data archive rather than an identified software release.
- Software versions, complete Galaxy workflow/history, full analysis parameters, the `core_nt` snapshot, checksums, and raw-read-to-assembly mappings are not present in the inspected files.
- The Word document uses screenshot evidence rather than an included machine-readable BLAST result table.

## Claims intentionally excluded

- No author, affiliation, funding, acknowledgements, license, release version, DOI, or publication date was invented.
- The report does not claim that repository code runs a pipeline, or that any software has been installed, tested, validated, benchmarked, or released.
- It does not infer mappings between individual read pairs and assembly exports where the README does not explicitly provide them.
- Working BLAST interpretations are not elevated into definitive taxonomic identifications or independent scientific findings.
- No external bibliographic references were fabricated. No protocol section is included because no protocol document or protocol citation was identified.
- No PDF artifact or assertion of successful PDF rendering was fabricated.
