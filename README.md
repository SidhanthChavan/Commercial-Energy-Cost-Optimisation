# Commercial Energy Cost Optimisation & Predictive Analysis

**Author:** Sidhanth V Chavan — MSc Data Science, Manchester Metropolitan University  
**Date:** May 2026  
**Domain:** UK Electricity Market / Commercial Energy Procurement

---

## The Question

I was looking at a commercial electricity bill and noticed something that did not immediately make sense. Two businesses paying the same energy rate per unit — but one was paying significantly more per kilowatt-hour overall. The difference was not in the energy itself. It was in everything sitting on top of it.

In the UK, roughly 40–60% of a commercial electricity bill is made up of regulated charges that exist independently of energy source or supplier. These are called **Non-Commodity Costs (NCCs)**. The question I wanted to answer was simple: do these charges scale proportionally with how much energy a business uses, or is something more complicated going on?

---

## Key Findings

| Finding | Result |
|---------|--------|
| Correlation (NCC vs Volume) | Pearson r = 0.97 |
| Linear model fit | R² = 0.944 |
| Polynomial model fit | R² = 0.978 |
| NCC rate — small consumers | ~7.8p per kWh |
| NCC rate — large consumers | ~11.0p per kWh |
| Per-unit premium for large consumers | ~40% more |
| NCC share of total bill | ~47% |

The relationship is **not linear**. Costs accelerate at higher consumption levels — driven primarily by Triad-based transmission charging in TNUoS.

---

## NCC Components Analysed

| Charge | Full Name | What It Funds |
|--------|-----------|---------------|
| DUoS | Distribution Use of System | Local cables and substations |
| TNUoS | Transmission Network Use of System | National grid infrastructure + Triad charging |
| BSUoS | Balancing Services Use of System | Real-time grid balancing |
| Capacity Market | — | Backup power plant availability |
| RO / FiT | Renewables Obligation / Feed-in Tariff | Renewable energy subsidies |
| CCL | Climate Change Levy | Carbon reduction policy (waived with REGO) |
| VAT | — | 20% on commercial supplies |

---

## Dataset

**File:** `uk_ncc_data.csv`  
**Records:** 80 UK commercial electricity consumers  
**Sectors:** Retail, Manufacturing, Office, Hospitality, Healthcare, Logistics  

NCC components are modelled on published 2025/26 UK regulatory rates:
- DUoS rates based on Western Power Distribution tariff structures
- TNUoS includes stepped unit rates and Triad exposure by sector profile
- CCL set to zero for the 30% of consumers holding REGO certificates
- VAT at 20% commercial rate throughout

| Column | Description |
|--------|-------------|
| Consumer_ID | Unique identifier |
| Sector | Industry sector |
| Annual_kWh | Annual electricity consumption |
| DUoS_GBP | Distribution charge |
| TNUoS_GBP | Transmission charge including Triad |
| BSUoS_GBP | Balancing charge |
| Capacity_Mkt_GBP | Capacity Market levy |
| RO_FIT_GBP | Renewables Obligation + FiT |
| CCL_GBP | Climate Change Levy |
| VAT_GBP | VAT at 20% |
| Total_NCC_GBP | Total non-commodity cost |
| Commodity_GBP | Energy commodity cost |
| Renewable_Cert | REGO certificate holder (True/False) |
| NCC_per_kWh_p | NCC rate in pence per kWh |

---

## Files

| File | Description |
|------|-------------|
| `NCC_vs_Volume_Analysis.ipynb` | Full analysis notebook — open in Google Colab |
| `Technical_Report_NCC_vs_Volume.docx` | Detailed technical report |
| `uk_ncc_data.csv` | Dataset — 80 commercial consumers |

---

## Run in Google Colab

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

All dependencies are standard — no installation required beyond a default Colab environment:
