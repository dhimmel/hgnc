# Extracting human gene families from HGNC

This repository processes the [gene family data](https://doi.org/10.1186/s40246-016-0062-6 "Gray et al (2016) A review of the new HGNC gene family resource. Human Genomics") from HGNC. In the future, the repository may expand its scope to process other types of HGNC data.

## Notebooks

+ [`1.download.ipynb`](1.download.ipynb) downloads HGNC data. Check this notebook to see the last modified dates of downloaded files.
+ [`2.families.ipynb`](2.families.ipynb) constructs the gene family ontology in `networkx`. Annotates gene families with their corresponding Entrez Gene IDs. Gene membership in a family is propagated, e.g. genes belonging to the "[Glutamate metabotropic receptors](http://www.genenames.org/cgi-bin/genefamilies/set/281)" family also belong to the "Glutamate receptors" family.

## Files & Directories

+ [`download`](download) contains unmodified downloads from the EBI FTP site.
+ [`data`](data) contains generated datasets. [`families.graphml`](data/families.graphml) contains a GraphML-formatted network of the HGNC gene family ontology. [`gene-families.tsv`](data/gene-families.tsv) contains the mapping between gene families and Entrez genes.

## Questions

Have a question? Submit all feedback or questions via [GitHub issues](https://github.com/dhimmel/hgnc/issues)!
