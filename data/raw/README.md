# Analysis inputs

The input tables are organized by measurement type. The directory includes assembled and normalized tables as well as qPCR exports.

| Directory | Contents |
| --- | --- |
| biochemistry/ | Model-construction and cohort biochemistry tables |
| qpcr/ | Day 14 and day 28 quantification exports |
| facs/ | Immune-cell fractions and sample metadata |
| rnaseq/ | Gene expression matrix and sample metadata |
| drinking_water/ | Drinking-water measurements by group and day |
| integrated/ | Consolidated sample information and RNA-seq identifiers |

## RNA-seq expression

`rnaseq/res_annotation.csv` contains 54,154 genes in rows and 72 RNA-seq samples in columns. The first column, gene, contains gene names; the sample columns are DRR identifiers.

The processing workflow imports Salmon quantifications with tximport and obtains counts using `summarizeToGene(..., countsFromAbundance = "scaledTPM")`. Per-sample tables are combined into an expression matrix. Gene IDs are mapped to gene names using a BioMart correspondence table after removing ID version suffixes. Unmapped genes are removed, and rows sharing a gene name are aggregated by their per-sample median. Columns containing good_out are excluded.

The resulting values are scaledTPM-derived counts, without log transformation or Z-score standardization. RNA-seq sample identifiers correspond to rnaseq_file in the integrated metadata.

## Integrated sample metadata

`integrated/2610_all_data.csv` contains 82 samples: 18 Control, 32 TAA and 32 MDA. Sampling-day categories are 1, 2, 3, 4 and 8.

| Column | Description |
| --- | --- |
| No. | Record number |
| ID | Sample identifier |
| group | Control, TAA or MDA |
| day | Sampling-day category |
| BW | Body weight |
| ALT / AST | Alanine / aspartate aminotransferase |
| TBIL | Total bilirubin |
| TCHO | Total cholesterol |
| HDL | HDL cholesterol |
| TG | Triglycerides |
| ALP | Alkaline phosphatase |
| GGT | Gamma-glutamyltransferase |
| GGT_at | @ denotes the lower quantification limit |
| water batch | Drinking-water preparation batch |
| rnaseq_file | DRR identifier; No File indicates no corresponding RNA-seq data |

Blank cells represent missing measurements. Seventy-two samples have RNA-seq identifiers. Their order matches the columns of res_annotation.csv after excluding No File rows.

The domain-specific metadata tables retain their individual column layouts and additional information, such as FACS fractions, RNA quality and RNA-seq selection flags. Their BW, ALT and AST values are aligned to the integrated table by sample ID.

## qPCR and reference data

The qPCR files contain well-level Cq and starting-quantity results, including Sample and Target identifiers. The model-construction biochemistry table contains repeated measurement columns for successive time points.

The GO gene sets used by the RNA-seq analysis are stored separately in `../references/go_mouse_msigdb.pickle`.
