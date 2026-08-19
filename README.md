# Bioinformatics & Pharmacology Utility Suite

A functional collection of self-directed Python scripts, relational data models, and computational simulations designed to process biological data structures, automate sequence parsing via web APIs, and model kinetic populations.

## Project Frameworks

### 1. Bioinformatics Parsers & Sequence Utilities (`/bioinformatics_parsers`)
* **molecular_sequence_utilities.ipynb**: Streams raw genomic data strings directly from the UniProt web database API using structured query parameters (`?format=fasta`) and virtual memory buffers (`io.StringIO`). Features a memory-efficient sequence conversion utility that handles human edge-case typos (normalizing casing, stripping accidental spacing, and parsing continuous or dash-separated text). Computes sequence Hamming distances and maps peptide arrays against isotopic tables to sum overall monoisotopic mass allocations.
* **dna_profile_matrix.ipynb**: Generates nucleotide frequency count matrices and evaluates vertical text arrays to output target consensus strings via custom tie-breaker routines.
* **combinatorics_engines.ipynb**: Generates lists of all possible permutations given a list of n size. Features a simple combinatorics engine, and an engine with signed permutations.
* **sequence_parsers.ipynb**: Included are a FASTA parser to that separates headers and sequences into a dictionary, a calculator to calculate the GC content percent of a given DNA sequence, and an open reading frame extractor. The open reading frame extractor tracks the position of all possible start codon positions and retrieves the sequence from each start codon. Covers both the template and coding strands, as well as any potential overlaps and only gives unique sequences.

### 2. Automated Laboratory Data Cleaning & Batch Pipelines (`/data_cleaning_pipeline`)
* **automated_data_cleaner.ipynb**: Audits raw text layout geometries prior to analytical loading to isolate structural array anomalies on explicit 1-indexed rows. Implements a custom callable callback pipeline within Pandas (`on_bad_lines`) to dynamically truncate over-extended inputs or pad incomplete records with empty strings, preventing critical data loss during ingestion. Features a `pathlib` automation wrapper to walk local directory trees and execute multi-file batch transformations concurrently.

### 3. Algorithmic Population Modeling (`/population_models`)
* **population_growth_matrices.ipynb**: Combines deterministic 2x2 state vector transformation models and age-structured Leslie Matrix simulations. Uses linear algebra and matrix multiplication to project generational demographic growth paths over fixed evaluation intervals, completely bypassing recursive execution memory overloads.

## Technical Toolsets Used
* **Languages & Database:** Python 3, SQL Syntax (PostgreSQL)
* **Libraries Used:** NumPy, Pandas, CSV, SQLAlchemy, psycopg2, math, io, urllib.request, re
