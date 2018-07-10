# PCRPrimerOperators
## PCRPrimerVerifier
### Basic
Shows the enclosed transcripts by user-provided primer pairs. To run to program

> java -jar PrimersToTranscripts.jar 

This package requires four parameters.
Usage: java -jar PrimersToTranscripts genome.fa anno.gtf primer_5F primer_3R

### Examples
Find which transcripts will be amplified by 
5F: GTTCCCTGATGATCAGACTCAG
3R: CAGTCTGCAACTTATCTGTGGGCC

The genome fasta file is from Ensembl website and the gtf file is obtained from 
ftp://ftp.ensembl.org/pub/release-92/fasta/
ftp://ftp.ensembl.org/pub/release-92/gtf/

or here are two files for human. Both of them are needed.
ftp://ftp.ensembl.org/pub/release-92/fasta/homo_sapiens/dna/Homo_sapiens.GRCh38.dna.primary_assembly.fa.gz
ftp://ftp.ensembl.org/pub/release-92/gtf/homo_sapiens/Homo_sapiens.GRCh38.92.gtf.gz

We only tested on GRCh38 and haven't tried on GRCh37.

> java -Xmx10g -jar PrimersToTranscripts.jar data/Homo_sapiens.GRCh38.82.dna.primary_assembly.fa.gz data/Homo_sapiens.GRCh38.82.gtf.gz GTTCCCTGATGATCAGACTCAG CAGTCTGCAACTTATCTGTGGGCC

\>ENST00000361924        GOLGA4-001      37355133-37366240(279)
GTTCCCTGATGATCAGACTCAGAAAATTTTGGAAAGAGAAGATGCTCGGCTGATGTTTACTTCACCTCGCAGTGGTATCTTCTGAGTAAACCATCAGTCTGTGCTTAGTTAACATGTGTCATGGCTCCGATCTTCATCTTGAAGAAGAGTGACATTGGGTGACTGCTGCTTGGAAAACTGTCCACACTTGCTACTCTTTGAGAATGAAGTTGTCATTCAGGGCCCCTCATGTAGCCAAAAGACCAAGAAAAATCTGGCCCACAGATAAGTTGCAGACTG

\>ENST00000437131        GOLGA4-005      37355133-37366240(216)
GTTCCCTGATGATCAGACTCAGAAAATTTTGGAAAGAGAAGATGCTCGGCTGATGTCATGGCTCCGATCTTCATCTTGAAGAAGAGTGACATTGGGTGACTGCTGCTTGGAAAACTGTCCACACTTGCTACTCTTTGAGAATGAAGTTGTCATTCAGGGCCCCTCATGTAGCCAAAAGACCAAGAAAAATCTGGCCCACAGATAAGTTGCAGACTG

\>ENST00000356847        GOLGA4-006      37355133-37366240(216)
GTTCCCTGATGATCAGACTCAGAAAATTTTGGAAAGAGAAGATGCTCGGCTGATGTCATGGCTCCGATCTTCATCTTGAAGAAGAGTGACATTGGGTGACTGCTGCTTGGAAAACTGTCCACACTTGCTACTCTTTGAGAATGAAGTTGTCATTCAGGGCCCCTCATGTAGCCAAAAGACCAAGAAAAATCTGGCCCACAGATAAGTTGCAGACTG

The results are in the fasta format that with the overlapped isoforms and the enclosed sequences including both sides of primers.

## PCRPrimerSearcher
