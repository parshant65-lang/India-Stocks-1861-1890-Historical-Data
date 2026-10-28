# India-Stocks-1861-1890-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1861 to 1890)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1861-1890-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1861 to 1890)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1861 | `PARNAXLAB` | Parnax Lab Limited | `PARNAXLAB.NS` |
| 1862 | `PARSVNATH` | Parsvnath Developers Limited | `PARSVNATH.NS` |
| 1863 | `PASHUPATI` | Pashupati Cotspin Limited | `PASHUPATI.NS` |
| 1864 | `PASUPTAC` | Pasupati Acrylon Limited | `PASUPTAC.NS` |
| 1865 | `PATELENG` | Patel Engineering Limited | `PATELENG.NS` |
| 1866 | `PATELRMART` | Patel Retail Limited | `PATELRMART.NS` |
| 1867 | `PATINTLOG` | Patel Integrated Logistics Limited | `PATINTLOG.NS` |
| 1868 | `PAUSHAKLTD` | Paushak Limited | `PAUSHAKLTD.NS` |
| 1869 | `PAVNAIND` | Pavna Industries Limited | `PAVNAIND.NS` |
| 1870 | `PBMPOLY` | PBM Polytex Limited | `PBMPOLY.NS` |
| 1871 | `PCJEWELLER` | PC Jeweller Limited | `PCJEWELLER.NS` |
| 1872 | `PDMJEPAPER` | Pudumjee Paper Products Limited | `PDMJEPAPER.NS` |
| 1873 | `PDSL` | PDS Limited | `PDSL.NS` |
| 1874 | `PEARLPOLY` | Pearl Polymers Limited | `PEARLPOLY.NS` |
| 1875 | `PENIND` | Pennar Industries Limited | `PENIND.NS` |
| 1876 | `PENINLAND` | Peninsula Land Limited | `PENINLAND.NS` |
| 1877 | `PERMAGN` | Permanent Magnets Limited | `PERMAGN.NS` |
| 1878 | `PERNIASPOP` | Purple Style Labs Limited | `PERNIASPOP.NS` |
| 1879 | `PFIZER` | Pfizer Limited | `PFIZER.NS` |
| 1880 | `PFS` | PTC India Financial Services Limited | `PFS.NS` |
| 1881 | `PGHH` | Procter & Gamble Hygiene and Health Care Limited | `PGHH.NS` |
| 1882 | `PGHL` | Procter & Gamble Health Limited | `PGHL.NS` |
| 1883 | `PGIL` | Pearl Global Industries Limited | `PGIL.NS` |
| 1884 | `PHOENXINTL` | Phoenix International Limited | `PHOENXINTL.NS` |
| 1885 | `PICCADIL` | Piccadily Agro Industries Limited | `PICCADIL.NS` |
| 1886 | `PIGL` | Power & Instrumentation (Gujarat) Limited | `PIGL.NS` |
| 1887 | `PILANIINVS` | Pilani Investment and Industries Corporation Limited | `PILANIINVS.NS` |
| 1888 | `PILITA` | PIL ITALICA LIFESTYLE LIMITED | `PILITA.NS` |
| 1889 | `PIONEEREMB` | Pioneer Embroideries Limited | `PIONEEREMB.NS` |
| 1890 | `PIONRINV` | Pioneer Investcorp Limited | `PIONRINV.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream PARNAXLAB 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1861-1890-Historical-Data/main/PARNAXLAB/1m/2026/10/PARNAXLAB_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
