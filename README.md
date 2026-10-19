# MDAdrinkingwater

Data and analysis notebooks for the TAA and MDA drinking-water models, including blood biochemistry, qPCR, flow cytometry, RNA-seq and histopathology analyses.

## Contents

| Directory | Contents |
| --- | --- |
| [notebooks/](notebooks/README.md) | Figure-generation and histopathology notebooks |
| [data/](data/README.md) | Analysis inputs, integrated tables and reference gene sets |
| environment/ | Python package versions in env.txt |

## Analysis

Use the repository root as the Python kernel's working directory. `notebooks/main_fig.ipynb` reads the tables under `data/raw/` and the GO reference under `data/references/`. Figures are saved to `results/main_fig/`, and statistical tables to `results/tables/`.

`notebooks/fig_submisson_HEandAD.ipynb` contains image-feature analysis and patch extraction. Its image and feature inputs are described in [notebooks/README.md](notebooks/README.md). Figures and extracted patches are saved to `results/histopathology/`.

The notebooks include saved outputs. [notebooks/figure_inventory.csv](notebooks/figure_inventory.csv) maps the main notebook's output filenames to analyses and cells.

## Authors

- [Takumi Iwasaka](https://github.com/T-IWASAKA): main contributor
- [Tadahaya Mizuno](https://github.com/tadahayamiz): corresponding author

## Contact

This repository is a research resource of the [Mizuno group](https://github.com/mizuno-group). Please contact tadahaya[at]gmail.com before publishing your paper using its contents.

For questions, open an issue or contact:

- iwasaka14[at]g.ecc.u-tokyo.ac.jp
- tadahaya[at]gmail.com
