# Mapping Commons for Phenotype Ontology Mappings

One of the primary goals of model organism research is to "enlighten" human disease research, that is to help understanding the underpinnings of human disease. There are various ways model and human data are typically connected, the most common of which are orthologue genes. Recently, large efforts have been made to connect the data on the level of phenotypes - which opens up a whole new world of possibilities connecting laboratory studies with phenotypic profiles of patients in Electronic Health Records. The idea behind `phenologs` is that a set of genes related to a phenotype in one organism may correspond to an orthologous set of genes in another organism. As we are beginning to understand more and more about the precise molecular underpinnings of model organism phenotypes, it makes sense to explore how much we could learn if we could connect well understood model phenotypes with their human phenologs. 

The purpose of our work here is to uncover phenolog _candidates_ by using ontology matching. It is important to set the expectations right from the start - similar phenotypes between organisms _do not imply_ a phenlog relationship. However, we hope to uncover _parameters_ by which we can increase the likelihood of an ontology match corresponding to a phenolog - our current hypotheses revolve around taxonmic distance in combination with anatomical homology. Roughly: the more "macroscopic" the phenotype (head, eye, limb), the closer taxonomically we have to be to identify reasonable phenologs, and the more "microscopic" we are (cellular components) the more taxonomic distance is acceptable. At this stage, this is just an hypothesis - its possible this is completely wrong.

This research is jump-started by a collaboration of [XenBase](http://www.xenbase.org/entry/) and the [Monarch Initiative](https://monarchinitiative.org/), but we invite anyone interested in participating to get in touch on the [issue tracker](https://github.com/mapping-commons/phenotype/issues). 

## Methodology

To uncover sets of _phenolog candidates_ between the above ontologies, we:

1. We collect and maintain "overestimation" mappings which are generated using automated tools, such as lexical matchers. This reduces the search space of potential mappings drastically from N2 to maximum 2N. Note that even this highly permissive approach is bound to miss potential phenolog candidates, due to high terminological discrepency (different labels, definitions etc).
2. We maintain the official Unified Phenotype Ontology (uPheno) mappings, which define phenologs over EQ statements. This produces a set of "anchor" mappings - mappings that are highly likely to be true. To emphasise what we mean by true here: true in the sense of "true ontology mappings". So they _are not phenologs_, merely phenolog candidates. Note that this will catch some cases that lexical matchers wont catch, so it will increase the space of potential candidates as well.
3. We work with Model Organism Databases such as Xenbase and ZFIN to review mappings manually and correct them were necessary.
4. We use Machine Learning based approaches to look for additional links previously missed.

In the first round, we focus here on collecting phenotype mappings between the following phenotype ontologies:

| Ontology | Description |
| --- | --- |
| Human Phenotype Ontology | An ontology of phenotypic abnormalities in Homo Sapiens |
| Mammalian Phenotype Ontology | An ontology of Mammalian phenotypes |
| Xenopus Phenotype Ontology | An ontology of phenotypic abnormalities in Xenopus |
| Zebrafish Phenotype Ontology | An ontology of phenotypic abnormalities in Zebrafish |


## Analysis

TBD. Ideas:
- Phenotypic profile matching between human disease profiles from HPOA with Xenopus phenotypic profiles
- We could see how much phenolog candidates can be confirmed by known genetic profiles (compare set of genes implicated by a phenotype in one organism to the set of phenotypes in another in terms of genetic orthology)
- Compare whether we can somehow confirm when an organism is a "known" model for a disease
