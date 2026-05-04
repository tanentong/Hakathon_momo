This repository contains the analytical pipeline, models, and supporting files for our submission to the MASA (Malaysian Actuarial Student Association) Hackathon 2026. We assess how climate-related risks may impact a multinational reinsurance firm's long-term financial resilience, with a regional focus on Southeast Asia.

**Repository:** [REPO URL]

---

## Project Summary

We use the World Bank's **World Development Indicators (WDI, Wide Format)** as the primary data source, supplemented by **EM-DAT** disaster records and industry sources (Swiss Re, Munich Re, OECD, World Bank).


## Repository Structure

```
.
├── README.md                          ← You are here
├── Code/
│   ├── 01_WS1_Code.ipynb              ← Data loading, cleaning, EDA, indicator selection
│   ├── 02_WS2_Code.ipynb              ← Fixed-effects panel regression + XGBoost comparison
│   ├── 03_WS3_Code.ipynb              ← Thailand vs Philippines disaster claims analysis
│   └── 04_WS4_Code.ipynb              ← BAU vs NDC mitigation scenario, 2030 projection
│   └── 05_WS5_Code.ipynb              ← Dashboard
├── Data/
│   ├── WB_WDI_WIDEF.csv.zip           ← .zip file because too large to upload
│   └── EMDAT_THA_PHL.csv              
├── Output/
│   ├── Output_WS1/                    ← Charts exported from notebooks
│   ├── Output_WS2/                    ← Charts exported from notebooks
│   ├── Output_WS3/                    ← Charts exported from notebooks
│   ├── Output_WS4/                    ← Charts exported from notebooks
└───├── Output_WS5/                    ← Interactive Plotly dashboard 

```

> **Note on the zipped file.** `data/WB_WDI_WIDEF.csv.zip` exceeds GitHub's recommended file size when uncompressed. **Unzip it into the `data/` folder before running notebook 01.** No data is downloaded over the network at runtime — everything is local.

---

## How to Run

### 1. Clone and install dependencies

```bash
git clone [REPO URL]
cd [REPO DIRECTORY]
pip install -r requirements.txt
```

### 2. Unzip the raw data

```bash
cd data
unzip WB_WDI_WIDEF.csv.zip
cd ..
```

### 3. Update the working directory in each notebook

> **Important.** Each notebook's first code cell sets the working directory using an absolute path that matches our local machine. Before running, **edit the `Drive_Path = ...` line at the top of every notebook** to point to the location where you cloned this repo. Look for a cell that looks like:
>
> ```python
> import path
> Drive_Path = Path.home() / "<PATH_TO_REPO>"   # ← change this to your local repo path
> ```

### 4. Run the notebooks in order

Open Jupyter and run the notebooks sequentially:

1. `Output_WS1.ipynb` — produces the cleaned panel `data/wdi_panel.csv`
2. `Output_WS2.ipynb` — fits FE regression and XGBoost, exports validation metrics
3. `Output_WS3.ipynb` — Thailand vs Philippines comparison with EM-DAT
4. `Output_WS4.ipynb` — BAU and mitigation projections to 2030
5. `Output_WS5.ipynb` — Interactive Dashboard

Each notebook is self-contained after running notebook 01 (which generates the cleaned panel used downstream).

---

## Data Source

- **World Bank** for open-access WDI data
- **CRED / EM-DAT** for disaster event records
