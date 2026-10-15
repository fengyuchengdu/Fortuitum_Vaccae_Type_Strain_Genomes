# *Fortuitum–Vaccae* clade type-strain genomes

This repository provides a curated collection of 124 compressed FASTA files for type strains in the *Fortuitum–Vaccae* clade, together with the metadata used in the accompanying manuscript.

## Repository contents

| Path | Description |
| --- | --- |
| [`fasta/`](fasta/) | 124 genome assemblies in gzip-compressed FASTA format (`*.fasta.gz`) |
| [`metadata/type_strain_metadata.tsv`](metadata/type_strain_metadata.tsv) | Curated, machine-readable source metadata |
| [`metadata/type_strain_metadata.md`](metadata/type_strain_metadata.md) | Human-readable metadata table with scientific typography and source links |
| [`metadata/genome_manifest.tsv`](metadata/genome_manifest.tsv) | Source metadata plus database links, file paths, and FASTA-derived statistics |
| [`DATA_DICTIONARY.md`](DATA_DICTIONARY.md) | Definitions for metadata and derived fields |

The collection currently contains 124 metadata records and 124 matching FASTA files. Every source metadata row is marked as a type strain. Most genome sources use NCBI Assembly accessions; the *M. mucogenicum* record uses the SRA run accession `DRR273467`, which is identified separately in the manifest.

## Download

Clone the complete collection:

```bash
git clone --depth 1 https://github.com/fengyuchengdu/Fortuitum_Vaccae_Type_Strain_Genomes.git
cd Fortuitum_Vaccae_Type_Strain_Genomes
```

For a single genome, open [`fasta/`](fasta/) and select the file whose name contains the required assembly or run accession. The `file_path` and `source_url` columns in [`metadata/genome_manifest.tsv`](metadata/genome_manifest.tsv) provide a programmatic index.

## Data notes

- Taxonomic names and type-strain designations reflect the curated dataset used for the accompanying study; the repository does not independently establish nomenclatural standing.
- `assembly_length_bp`, `gc_percent`, and `n50_bp` are calculated directly from the decompressed sequences. See [`DATA_DICTIONARY.md`](DATA_DICTIONARY.md) for definitions.
- Source database records may be updated after this dataset was assembled. The manifest links each included file to its accession record.

## Citation

Before the accompanying manuscript is published, please cite this repository: [*Fortuitum–Vaccae* clade type-strain genomes](https://github.com/fengyuchengdu/Fortuitum_Vaccae_Type_Strain_Genomes). After publication, cite the manuscript and the repository version used.

## License and reuse

The genome sequences were obtained from public sequence databases and remain subject to the terms and attribution expectations of their source records.

## Reporting an issue

Please open a data issue and include the `record_id`, accession or file name, a description of the proposed correction, and a stable supporting source.

