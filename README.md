# pcos-granulosa-transcriptomics

## Background
Polycystic Ovary Syndrome (PCOS) affects a large share of women of reproductive age and sits at the intersection of hormonal, metabolic, and reproductive dysfunction — yet the molecular mechanisms driving it are still not fully understood. Granulosa cells, which surround and support the developing oocyte, are directly exposed to the hormonal and metabolic environment of PCOS, making them a natural tissue to study.

This project independently reanalyzes public RNA-seq data (GSE293353: 9 PCOS patients vs. 9 matched controls, granulosa cells collected during IVF oocyte retrieval) to ask what's transcriptionally different in PCOS granulosa cells, and whether an independent analysis recovers the same signals reported in the original published study.

## The question
What genes and pathways are dysregulated in PCOS granulosa cells, and does an independent reanalysis — using a different toolchain and pathway framework than the original study — recover the same key findings (specifically, oxidative-stress-related dysregulation and GPX3 upregulation)?

## Method
1. QC and low-expression filtering, gene ID mapping (Ensembl -> gene symbol)
2. Differential expression: PyDESeq2, PCOS vs. matched controls
3. Pathway enrichment (ORA): Hallmark + KEGG gene sets
4. Targeted pathway scoring: MitoCarta3.0 mitochondrial pathway sub-scores, to directly test the oxidative-stress/mitochondrial mechanism the original study proposed
   
Given the small cohort (n=9 vs. 9), results are interpreted with that limitation explicitly in mind throughout -- pathway-level scores tested across many gene sets simultaneously are underpowered at this sample size, so individual, targeted gene-level findings are weighted more heavily than broad pathway screens.

