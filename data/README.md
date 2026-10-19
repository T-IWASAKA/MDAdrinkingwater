# Data guide

## Choose your data

- **Analysis inputs:** `raw/` contains the domain-specific tables read by the main notebook.
- **New analyses:** `processed/` provides English-documented metadata and expression copies. See [processed/README.md](processed/README.md).
- **Reference gene sets:** `references/` contains the GO data used by GAGE.

The raw directory contains analysis input tables, including assembled or normalized measurements. The processed directory provides integrated sample metadata and a descriptively named expression matrix.

## Original file locations

| File | Location relative to data/ |
| --- | --- |
| 230528_DrinkingWaterModel_rawdata_v2.csv | raw/rnaseq/230528_DrinkingWaterModel_rawdata_v2.csv |
| 230605_data_blood_facs.csv | raw/facs/230605_data_blood_facs.csv |
| 231020_dw_day14_fib_2309sample_v2 -  Quantification Cq Results.csv | raw/qpcr/231020_dw_day14_fib_2309sample_v2 -  Quantification Cq Results.csv |
| 231023_dw_day28_fib_2309sample -  Quantification Cq Results.csv | raw/qpcr/231023_dw_day28_fib_2309sample -  Quantification Cq Results.csv |
| 240111_DrinkingWaterModel_rawdata_v6.csv | raw/biochemistry/240111_DrinkingWaterModel_rawdata_v6.csv |
| 2610_all_data.csv | raw/integrated/2610_all_data.csv |
| drink_TAA_MDA_chronic.csv | raw/biochemistry/drink_TAA_MDA_chronic.csv |
| go_mouse_msigdb.pickle | references/go_mouse_msigdb.pickle |
| res_annotation.csv | raw/rnaseq/res_annotation.csv |
| waterdata.csv | raw/drinking_water/waterdata.csv |

## Reuse-ready files

| File | Source and transformation |
| --- | --- |
| processed/sample_metadata.csv | raw/integrated/2610_all_data.csv; column names converted to English snake_case only; values and row order unchanged |
| processed/gene_expression_scaled_tpm.csv | Byte-identical copy of raw/rnaseq/res_annotation.csv with a descriptive filename |

[manifest.csv](manifest.csv) lists file sizes, dimensions, checksums and source relationships. [raw/README.md](raw/README.md) describes the analysis inputs. Sample BW, ALT and AST values in the metadata tables are aligned by ID with raw/integrated/2610_all_data.csv.

