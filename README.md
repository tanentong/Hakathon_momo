**Data Source: **
We use the World Bank's World Development Indicators (WDI, Wide Format) as the main dataset, plus EM-DAT disaster records and industry sources (Swiss Re, Munich Re, OECD, World Bank).

**Folder Structure**
.
├── README.md                          ← You are here
├── Code/
│   ├── WS1_Code.ipynb                 ← Data cleaning & EDA
│   ├── WS2_Code.ipynb                 ← Prediction model
│   ├── WS3_Code.ipynb                 ← Thailand vs Philippines
│   ├── WS4_Code.ipynb                 ← 2030 stress test
│   ├── WS5_Code.ipynb                 ← Dashboard
│   └── Team_momo_Full_Code.ipynb      ← Full code (run this one)
├── Data/
│   ├── WB_WDI_WIDEF.csv.zip           ← Zipped (file too big)
│   └── EMDAT_THA_PHL.csv
└── Output/
    ├── Output_WS1/                    ← Charts from WS1
    ├── Output_WS2/                    ← Charts from WS2
    ├── Output_WS3/                    ← Charts from WS3
    ├── Output_WS4/                    ← Charts from WS4
    └── Output_WS5/                    ← Interactive dashboard

**How to Run**
1. Click the GitHub link and download the repo.
2. Go into the Data/ folder and unzip WB_WDI_WIDEF.csv.zip (keep it inside the Data/ folder).
3. Open Code/Team_momo_Full_Code.ipynb.
4. Change the file path at the top of the notebook to match where you saved the folder on your computer.
5. Run all cells.
