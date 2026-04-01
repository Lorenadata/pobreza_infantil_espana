# Pobreza y exclusión social en la infancia española

Análisis de la tasa AROPE infantil en España a partir de microdatos de la **Encuesta de Condiciones de Vida (ECV) 2024** del INE.

---

## Objetivo

Explorar la situación de la población infantil española (menores de 16 años) en términos de pobreza y exclusión social, identificando los perfiles de hogar más vulnerables y contrastando el dato español con el contexto europeo.

---

## Dimensiones analizadas

- **Tasa AROPE infantil en España** y comparación con el máximo europeo (Bulgaria, 34,3%)
- **Régimen de tenencia de la vivienda** — arrendatarios vs. no arrendatarios
- **Composición del hogar** — hogares monoparentales y numerosos como factores de riesgo
- **Privación alimentaria** — incapacidad de costear proteína animal cada dos días
- **Pobreza energética** — incapacidad de mantener la vivienda a temperatura adecuada

---

## Estructura del proyecto

```
pobreza-infantil-espana/
│
├── pobreza_infantil_españa.qmd    # Análisis principal (Quarto)
├── pobreza_infantil_españa.html   # Informe renderizado (GitHub Pages)
├── ECVpersona.RData               # Microdatos ECV 2024 — no incluidos en el repo*
└── README.md
```


---

## Fuente de datos

| Campo | Detalle |
|---|---|
| Encuesta | Encuesta de Condiciones de Vida (ECV) |
| Edición | 2024 |
| Organismo | Instituto Nacional de Estadística (INE) |
| Nivel | Microdatos de persona |
| Ponderación | Factor de elevación `RB050` |

---

## Variables clave

| Variable | Descripción |
|---|---|
| `RB081` | Edad de la persona |
| `RB050` | Factor de ponderación muestral |
| `vrEU2030_nuevo` | Indicador AROPE (At Risk Of Poverty or Social Exclusion) |
| `ARRENDATARIO` | Régimen de tenencia: arrendatario / no arrendatario |
| `TIPHOGAR` | Tipo de hogar según composición |
| `HS050` | Privación alimentaria (comida proteica cada 2 días) |
| `HS040` | Pobreza energética (temperatura adecuada en el hogar) |

---

## Requisitos

```r
install.packages(c("tidyverse", "dplyr", "Hmisc"))
```

R versión ≥ 4.0 y Quarto ≥ 1.3 recomendados.

---

## Cómo ejecutar

1. Descarga los microdatos ECV 2024 del INE y guarda el archivo como `ECVpersona.RData` en la raíz del proyecto
2. Abre `pobreza_infantil_españa.qmd` en RStudio
3. Haz clic en **Render** para generar el informe HTML

---

## Principales hallazgos

- La tasa AROPE infantil en España **supera el máximo europeo** registrado por Bulgaria (34,3%), situándola entre las más elevadas de la UE
- Los niños en **hogares arrendatarios** presentan tasas de AROPE y privación alimentaria notablemente superiores
- Los **hogares monoparentales** (Tipo 3) y los **hogares numerosos con 3+ hijos** (Tipo 6) concentran el mayor riesgo de pobreza infantil
- La **pobreza energética** sigue una lógica distinta: afecta más a hogares en propiedad, condicionada por la antigüedad y eficiencia del parque residencial español

---

*Parte de mi portfolio de análisis de datos sociales con microdatos oficiales.*
