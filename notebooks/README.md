# Analysis notebooks

| Notebook | Analysis | Output directory |
| --- | --- | --- |
| main_fig.ipynb | Biochemistry, qPCR, flow cytometry, RNA-seq, drinking-water intake and abnormal patch ratios | results/main_fig/ |
| fig_submisson_HEandAD.ipynb | Histopathology anomaly detection, feature PCA, spatial maps and patch extraction | results/histopathology/ |

## Inputs and environment

Both notebooks use the repository root as the kernel working directory. The main notebook uses `data/raw/`, `data/references/` and the modules in `notebooks/utils/`. Package versions are listed in `environment/env.txt`.

The histopathology notebook requires feature and coordinate files under `workspace/result_v5/`, TIF images under `workspace/HE_240205_iwasaka/`, and the external `data_handler` module imported from `/workspace`. These image-analysis inputs and the module are not bundled with this repository. Paths are relative to the repository root unless absolute.

## Figure inventory

[figure_inventory.csv](figure_inventory.csv) lists the 34 figure-save targets in main_fig.ipynb. Notebook paths are relative to the repository root. `cell_index_0based` is the cell position starting at zero, rather than the execution count.
