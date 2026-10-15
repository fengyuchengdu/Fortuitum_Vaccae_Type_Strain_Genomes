# Data dictionary

## Source metadata

[`metadata/type_strain_metadata.tsv`](metadata/type_strain_metadata.tsv) is the authoritative, machine-readable source table. Scientific names remain unformatted in this TSV so downstream software can parse them without Markdown syntax. The companion [`metadata/type_strain_metadata.md`](metadata/type_strain_metadata.md) presents those names in italics on GitHub.

| Field | Definition |
| --- | --- |
| `record_id` | Stable repository identifier assigned in the original curated order (`FVC001` to `FVC124`) |
| `species_name` | Abbreviated species name used in the curated metadata |
| `species_name_gupta_2018` | Name recorded in the metadata column referring to Gupta et al. (2018) |
| `previous_species_name` | Previous name recorded in the curated metadata |
| `type_or_reference_strain` | Type or reference strain designation; Unicode superscript `ᵀ` marks the type strain |
| `nucleotide_accession` | Nucleotide accession recorded in the curated metadata |
| `assembly_or_run_accession` | NCBI Assembly accession (`GCA_`/`GCF_`) or sequence-read run accession (`DRR`/`ERR`/`SRR`) used to identify the genome source |
| `original_proposer_and_year` | Original proposer and year text retained from the curated metadata |
| `is_type_strain` | Type-strain flag; all current records are `Y` |
| `file_name` | Name of the corresponding gzip-compressed FASTA file |

The field is named `assembly_or_run_accession` because one current record uses SRA run accession `DRR273467` rather than an Assembly accession.

## Genome manifest fields

[`metadata/genome_manifest.tsv`](metadata/genome_manifest.tsv) contains all source fields plus the following derived fields.

| Field | Definition |
| --- | --- |
| `source_database` | NCBI database inferred from the accession prefix (`NCBI Assembly` or `NCBI SRA`) |
| `source_url` | Direct source-record URL constructed from `assembly_or_run_accession` |
| `file_path` | Repository-relative path to the FASTA file |
| `file_size_bytes` | Size of the compressed file in bytes |
| `sequence_count` | Number of FASTA records, counted from header lines beginning with `>` |
| `assembly_length_bp` | Total number of nucleotide symbols across all FASTA records |
| `gc_percent` | `(G + C) / assembly_length_bp × 100`, including ambiguous bases in the denominator; reported to four decimal places |
| `n50_bp` | Sequence length at which sequences of that length or longer account for at least 50% of `assembly_length_bp` |

All derived values describe the FASTA files included in this repository version.

