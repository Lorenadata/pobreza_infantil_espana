# Child Poverty and Social Exclusion in Spain

[![Report](https://img.shields.io/badge/report-live-2ea44f)](https://lorenadata.github.io/pobreza_infantil_espana/)
![R](https://img.shields.io/badge/R-276DC3?logo=r&logoColor=white)
![Quarto](https://img.shields.io/badge/Quarto-75AADB?logo=quarto&logoColor=white)

Survey-weighted analysis of the **AROPE** indicator (*At Risk Of Poverty or Social Exclusion*) for children under 16 in Spain, using official microdata from the INE **Survey on Income and Living Conditions (ECV 2024)**.

**📄 Full report (Spanish):** https://lorenadata.github.io/pobreza_infantil_espana/

---

## Question

Is it true that child poverty in Spain is among the highest in the EU — and which households carry most of that risk?

## Key findings

| | AROPE rate |
|---|---|
| Children under 16 | **34.7%** |
| Rest of the population | 24.3% |

- The child AROPE rate is **10 points higher** than for the rest of the population, and above the 34.3% registered by Bulgaria, the highest in the EU among countries with available data.
- Renting concentrates every form of deprivation analysed: among children in **rented homes**, 12.9% live in a household that can't afford a protein meal every second day (vs 4.2%), and 29.3% in a home that can't be kept adequately warm (vs 12.7%).
- **Single-parent households** and **large families (3+ children)** concentrate the highest risk.

> **Correction (October 2026).** The first version of this report coded two deprivation indicators wrongly (`HS050 == 1` and `HS040` instead of `HS050 == 2` and `HH050`), which reversed the energy-poverty finding. The report and this README are corrected; AROPE rates are unaffected.

## Methodology

- Unit of analysis: individuals, weighted with the population expansion factor `RB050`, so every rate is a population estimate rather than a raw sample proportion.
- Children defined as under 16 (`RB081`), following the Eurostat AROPE definition.
- Dimensions: housing tenure, household type, food deprivation and energy poverty.

| Variable | Meaning |
|---|---|
| `RB081` | Age |
| `RB050` | Population weight |
| `vrEU2030_nuevo` | AROPE indicator (EU 2030 definition) |
| `ARRENDATARIO` | Housing tenure: tenant / non-tenant |
| `TIPHOGAR` | Household type |
| `HS050` | Can afford a protein meal every second day (2 = no) |
| `HH050` | Can keep the home adequately warm (2 = no) |

## Repository structure

```
.
├── pobreza_infantil_espana.qmd   # Analysis source (Quarto)
├── index.html                    # Rendered report, served by GitHub Pages
└── ECVpersona.RData              # ECV 2024 person-level microdata (INE)
```

## Reproduce

```r
install.packages(c("tidyverse", "Hmisc"))
```

Open `pobreza_infantil_espana.qmd` in RStudio and click **Render** (R ≥ 4.0, Quarto ≥ 1.3). The microdata file is included; it can also be downloaded from the [INE microdata portal](https://www.ine.es/dyngs/INEbase/es/operacion.htm?c=Estadistica_C&cid=1254736176807&menu=resultados&idp=1254735976608).

## Data source

Instituto Nacional de Estadística (INE), *Encuesta de Condiciones de Vida 2024*, person-level microdata. Data © INE, reused under its open-data terms.

---

**Lorena Marcos** · Applied Data Science, Universidad Complutense de Madrid · [LinkedIn](https://www.linkedin.com/in/lorena-marcos-6516272b5/) · [GitHub](https://github.com/Lorenadata)
