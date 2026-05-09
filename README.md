# Russia-sanctions-trade-reallocation - replication code
Paper: Beyond Trade Decline: Sanctions Intensity and Russia’s Trade Reallocation

This repository contains the replication code (single Jupyter Notebook) for the empirical analysis of Russia’s trade reallocation and its relationship with sanctions intensity at the partner–year level.

CONTENTS
- RU trade.ipynb — main replication notebook (data preparation, descriptive figures/tables, and econometric models).
- RU_trade.csv — input trade dataset (downloaded from IMF data and then processed in the notebook).
(Sanctions data are not included — see “Sanctions data (GSDB)” below.)

RESEARCH DESIGN (HIGH-LEVEL)
1. Unit of analysis: Russia–partner–year panel (dyad-year).
2. Trade outcomes: exports and imports of goods by partner (IMF trade data).
3. Sanctions treatment: partner-year sanctions intensity index (constructed from GSDB Release 4; capped to 0–6; coalition episodes expanded to countries).
4. Methods:
 - Panel OLS with partner and year fixed effects using trade shares (exports/imports share).
 - PPML gravity on trade levels (exports/imports values) as robustness.
  
HOW TO RUN
1. Clone or download this repository.
2. Create a clean environment and install dependencies:

Option A (pip):

pip install -r requirements.txt

Option B (conda):

conda create -n ru_trade python=3.11
conda activate ru_trade
pip install -r requirements.txt

3. Open and run the notebook:

jupyter notebook

Then open RU trade.ipynb and run all cells from top to bottom.

The notebook is organized to run sequentially. If any paths are hard-coded, update them near the top of the notebook (e.g., out_path / out_folder).

DATA SOURCES & AVAILABILITY
Trade data (included)
- The file RU_trade.csv is derived from IMF trade data (exports/imports of goods by partner).
- The notebook documents all transformations used to produce the final analysis datasets and figures.

Sanctions data (GSDB) — not included
- This project uses the Global Sanctions Data Base (GSDB) Release 4.
- GSDB is not redistributed in this repository due to third-party access restrictions/licensing.
- To replicate sanctions construction and run the full pipeline, users must obtain GSDB directly from the authors/maintainers and place it locally following the notebook instructions (see the “Sanctions data input” section inside the notebook).

Data availability statement (suggested wording):
The trade data used in this study are derived from publicly available IMF data and are included in this repository in processed form. The sanctions data are based on the Global Sanctions Data Base (GSDB) Release 4, which is available from the GSDB authors subject to their access conditions and is therefore not redistributed here. All code required to reproduce the results from the raw sources is provided.

OUTPUTS

Running the notebook produces:
- Descriptive figures on trade-share dynamics (sanctioning vs non-sanctioning; pre/post reallocation; composition).
- Appendix-ready tables (pre vs post shares; partner classification; econometric result tables).
- OLS FE and PPML estimates (baseline + robustness excluding Ukraine).

Notes on reproducibility
- Results may vary slightly across environments due to package versions.
- If you update any dependencies, record them in requirements.txt.

Citation
If you use or adapt this code, please cite the related paper (working paper / manuscript details to be added).

Contact
For questions regarding replication or data setup, please contact: (paulina.kasetiene@ktu.lt).
