Gene family DB table files
--------------------------

The files within this directory contain data found in the gene family
associated tables within our database and are in a comma separated value
format. Each value is quoted within double quotes and all have a header line
denoting the column titles.

Tables
------

family.csv
    Main table containing family data.

    Contains the following columns:
        id: gene family primary key.

        abbreviation: abbreviation name of the family usually a common root
symbol of the genes within.
        
        name: family name.
        
        external_note: HGNC note about the family.
        
        pubmed_ids: Associated pubmed IDs
        
        desc_comment: Description of the family.
        
        desc_label: Label for the description.
        
        desc_source: Where the description came from.
        
        desc_go: The GO term connected to the description.
        
        typical_gene: Typical member gene of the family.


hierarchy.csv
    Relationships between families, step by step.

    Contains the following columns:
        parent_fam_id: The family ID of the family above the child (sub)
family. Foreign key for family.id

        child_fam_id: The family ID of the family below the parent (super)
family. Foreign key for family.id


hierarchy_closure.csv
    Relationships between families showing the full hierarchical ascyclic
graph from a family down and the distance from the super family.

    Contains the following columns:
        parent_fam_id: The family ID of the super family. Foreign key for
family.id

        child_fam_id: The family ID of the family below the super family.
Foreign key for family.id

        distance: How far the child/sub family is from the super family.


external_resource.csv:
    External resources linked to the gene family.

    Contains the following columns:
        id: The primary ID for the external resource.

        name: Name of the resource.

        url: The URL of the resource.

        description: A description of the resource.
        
        approved: Resources uses approved gene symbols and or IDs.


family_has_external_resource.csv
    A linking many to many table to join family to external resource.

    Contains the following columns:
        family_id: Foreign key for the family table

        ext_id: Foreign key for the external_resource table

gene_has_family.csv
    A linking many to many table to join family to HGNC gene data.

    Contains the following columns:
        hgnc_id: The HGNC ID for the gene. Foreign key to link to gene tables
etc.

        family_id: The family ID. Foreign key for the family table.
