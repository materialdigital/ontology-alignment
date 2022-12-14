# Ontology-Alignment
A module for alignment of MSE-related ontologies.

Materials Science and Engineering (MSE) combines engineering, physics and chemistry principles to solve real-world problems associated with nanotechnology, biotechnology, information technology, energy, manufacturing and other major engineering disciplines. 

For the digitization of MSE-relevant processes, objects involved (e.g. material), scientific findings and existing knowledge many differnt ontologies are used to represent the data. Each ontology has been created under different design principles and focus even if they actually are created for the same or similar purpose. This leads to a high degree of diversity of the MSE-related ontolgies which practically prevents interoperability.

To overcome this issue, this repository provides an attempt to align different MSE-related ontolgies, namely: PMDco(Prov-O included), BFO, EMMO, CCO.

With this alignment a partial conversion between data encoded with these ontology should be possible. 

## Content
This repo contains: 

- a directory with example data encoded with different MSE-related ontologies
- a RDF file which contains the alignment statements
- a jupyter notebook containing an example on how to bring the alignment to action

## Example
[Colab Notebook demonstration](https://colab.research.google.com/github/materialdigital/ontology-alignment/blob/main/pmdco_mapping_dev.ipynb)
