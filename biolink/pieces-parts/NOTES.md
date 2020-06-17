# Queries

- mediKanren has connected lots of DB
  - with a single query, I am hitting giant DBs to get back answers
  - one giant query to get all the mk data!
  - graph: you have to think of it a certain way
  - vs tables
  
- druggable genome
  - kinease very druggable
  - protease druggable
  - transcription factors not so druggable
  - chemical reaction things are often more druggable
  - can start with druggable genome
  - experiment: knock out each gene in a list to see which with the virus survives
  - allows to add genes "just in case" because we know they are druggable
  - sophisticated intersection:
    - these are genes involved in the pathways of the virus
    - set of genes in each functional pathways
    - complete the set with druggable genes
    - can use GO ontology
    - can use algorithms for 'gene enrichment' (the gene list sharpener)
      - https://indigo.ncats.io/
- gene interaction
- tell me the genes associated with a phenotype for a type of disease or disorder
- drug prioritzation:
  - here are all the drugs that would buge the genes that would be pro and anti viral.
  - lower the priority for testing if it exacerbates the disease.
- bridge are the drugs:
  - here's a list of drugs. without knowing the gene list, use counter indication information.
  - this drug is bad for this disease, however it's related.
- how do you find the drug/genes?
  - we know the pathways it hijacks in the cell.
  - virus need to escape detection.

- What repeated queries would be useful?
  - batch 2-hop query: drug - gene2 - gene1
    set of gene1s
  - predicates for upregulates
  - predicates for downregulates
  - another way to sort:
    - strong relationship vs weaker/ambiguous relationship
  - direction + strength (some tools use that, is it confidence, probability?)
  - bio example:
    - all the 1-hops have already been done, because a journal says this uprelates that. relationship is not novel.
    - with 2-hops, we can know thing that have not been known before. nobody can do that in a way that we can look at 2-hops at the same time, and do the filtering.
    - here is all the DFA approved drugs from 2-hop from these gene list.
    - UI: build a gene list, and do things with it.
    - if ..., filter it out
    - 2-hop: many thousands of this
- Understand what do we lose from a drug list that is FDA approved
  - Resveratrol? FDA-approved
  - FDA will put a "generally recognized as safe"
  - e.g. tag GRAS: generally recognized as safe
  - we can put filters, but doctors want to understand the filters
  - maybe RX norm?
  - diabetics are in trouble via glucose. in one gene, see evidence that sugar would be bad.

- more exploratory data mining?
  - as opposed to excel sheet

- when doing up/down regulation, the information comes from semmed db
  - check against other databases like GO
- broad has hightroughput experiments
  - cancer cells + thousands of drugs figuring out gene expression levels
  - you get quantitive information, an entire profile
  - can be 2 TB of data
  - noisy data
  - across tissue types
- drug gene budger website
  - use broad data
  - to predict whether a drug up or down regulate this gene, with quantitative score

- finding a 'safe' drug to regulate a gene
  - this drug might have an effect on many genes
  - look at 2-hop queries: drug -> gene -> gene, -> regulates.
  - 2-hop queries are a tricky ranking problem
  - you want to know the off target effects

- at least two notions of ranking
  - because data is incomplete, or contradictory, or wrong (because of bad NLP)
  - one notion of ranking: what's the confidence you have this is true
  - other notion: assuming it's true, how well does it work?
  - how can you display a query where you express preferences
  - trade-offs

- goal: improving the ranking for 1- & 2-hop queries for gene budging

- also: how to visualize it?

- or better ways to determine whether a drug is safe