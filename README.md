# Generating Coarse-Grained Model Files for Molecular Dynamics Simulations

## Description
This project helps to prepare coarse-grained (CG) model topology/coordinate files for MD simulations.
File format is in gromacs style.

## Dependencies

### python packages
- numpy
- MDAnalysis

### other
- [3dna](http://x3dna.org/)

## Usage

### CG Protein (the [AICG2+](https://doi.org/10.1073/pnas.1402768111) model)

Given the native structure of a protein (or complex of proteins), the script
can generate the topology and parameter files: 
```
/path_to_gen_input_cg_gro/PRO_AICG2P/pdb2gro_aicg2p.py -s 1 xxx.pdb
```

Output:
- A topology file `xxx.itp`
- A coordinate file `xxx.gro`

![Protein AICG2+ file preparation.](/img/pro_aicg2p.gif)

### CG DNA (the [3SPN.2C](https://doi.org/10.1063/1.4897649) model)

First of all, the reference structure of B-type DNA is base on the software
[3dna](http://x3dna.org/), we have to use it to create a DNA structure.

Prepare a sequence file in the `fasta` format:
```
> DNA sequence
ATGCATGCATGC...ATGC
```

Run the following:
```bash
/path_to_gen_input_cg_gro/DNA_3SPN2C/bdna_3spn2c_gen.sh xxx.fasta
```

What we get:
- An atomistic PDB file generated by [3dna](http://x3dna.org/)
- A `.gro` file with coarse-grained particles
- Two `.itp` topology files for the two strands of dsDNA

![DNA 3SPN.2C file preparation.](/img/dna_3spn2c.gif)
