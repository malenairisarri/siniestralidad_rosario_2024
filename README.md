# Índices y Mapas Georreferenciados de Siniestralidad Vial en Rosario — 2024

> **Tesina de Licenciatura en Estadística**  
> Universidad Nacional de Rosario — Facultad de Ciencias Económicas y Estadística  
> Autora: **Malena Irisarri** | Directora: **Cristina Cuesta** | Año: **2026**

---

## 📋 Descripción

Este repositorio contiene la documentación y los recursos correspondientes a la tesina de licenciatura titulada *"Índices y Mapas Georreferenciados de Siniestralidad Vial en Rosario en el Año 2024"*.

El trabajo tiene como objetivo **identificar y jerarquizar las intersecciones con mayor nivel de siniestralidad vial en la ciudad de Rosario** mediante la integración de múltiples fuentes de datos y la construcción de indicadores comparativos de peligrosidad.

> ⚠️ **Nota:** Los datos utilizados fueron provistos por organismos municipales y provinciales bajo acuerdo de uso académico y no se encuentran disponibles en este repositorio por razones de confidencialidad institucional.

---

## 📁 Contenido del Repositorio

```
siniestralidad-vial-rosario-2024/
│
├── tesina/
│   └── Irisarri_Malena_Tesina_2026.pdf
│
├── presentacion/
│   └── Blue_White_Minimalist_Modern_Geometric_Thesis_Defense_Presentation.pdf
│
└── README.md
```

La aplicación interactiva se encuentra desplegada en shinyapps.io — ver sección [Aplicación Interactiva](#-aplicación-interactiva).

---

## 🎯 Objetivos

**Objetivo General:**  
Identificar y jerarquizar las intersecciones más peligrosas de la ciudad de Rosario en función de la siniestralidad vial en el año 2024.

**Objetivos Específicos:**
- Georreferenciar las ubicaciones de los siniestros viales ocurridos en la ciudad de Rosario
- Detectar zonas de alta concentración de siniestros
- Evaluar y jerarquizar las intersecciones según su nivel de peligrosidad

---

## 🗂️ Fuentes de Datos

| Fuente | Descripción | Período |
|--------|-------------|---------|
| **SIES** | Sistema Integrado de Emergencias Sanitarias — siniestros con lesionados | 2024 |
| **SIDEAT** | Sistema Integrado de Denuncias de Accidentes de Tránsito — siniestros sin lesionados | 2018 |
| **APSV** | Registro provincial de víctimas fatales (Agencia Provincial de Seguridad Vial) | 2024 |
| **DSL / Espiras** | Capa de espiras semafóricas de la Dirección de Señalización Luminosa — flujo vehicular | 2024 |
| **EMR / Censos** | Censos manuales de tránsito del Ente de la Movilidad de Rosario | 2025 |

---

## ⚙️ Metodología

### 1. Preprocesamiento y Georreferenciación
- Construcción de la red vial desde **OpenStreetMap** y extracción de intersecciones urbanas
- Normalización y estandarización de nombres de calles mediante diccionario de equivalencias
- Geocodificación automática con el paquete `geoAr` y verificación manual en Infomapa Rosario
- Asignación de siniestros a intersecciones mediante **algoritmo de vecino más próximo**

### 2. Estimación del Flujo Vehicular
- Depuración e imputación de series de espiras magnéticas
- Expansión estructural según ramas teóricas de cada intersección
- **Interpolación por Distancia Inversa (IDW)** para intersecciones sin medición directa
- Calibración empírica por tipología de intersección a partir de censos manuales

### 3. Índices de Siniestralidad

| Método | Descripción | Fórmula |
|--------|-------------|---------|
| **Valor Absoluto (IVAX)** | Número total de siniestros por intersección | `IVAX = N_X` |
| **Tasa de Ocurrencia (TX)** | Siniestros ponderados por gravedad y ajustados por flujo vehicular | `TX = (N_D + N_L×5 + N_VF×10) / Flujo × 10⁶` |
| **Número Índice (INIX)** | Índice sintético normalizado que combina ambos indicadores | `INIX = 0.3 × A_X + 0.7 × T'_X` |

### 4. Visualización Interactiva
Aplicación web desarrollada con **Shiny (R)** que permite explorar la distribución espacial y temporal de los siniestros mediante mapas de puntos, mapas de calor (KDE) y filtros dinámicos por zona, barrio, fecha y horario.

---

## 📊 Principales Resultados

### 🏆 Top 5 — Índice Normalizado Integrado (INIX)

| Ranking | Intersección | INIX |
|---------|-------------|------|
| 1 | Avenida Carlos Pellegrini y Bulevar Nicasio Oroño | 1,00 |
| 2 | Bulevar Juan Francisco Seguí y Bulevar Nicasio Oroño | 0,79 |
| 3 | Avenida Jorge Newbery y Colectora José María Rosa | 0,75 |
| 4 | Bulevar Nicasio Oroño y Avenida Battle y Ordoñez | 0,73 |
| 5 | Avenida Pellegrini y Avenida Manuel Belgrano | 0,72 |

### 📌 Hallazgos Clave
- Las intersecciones más críticas se concentran en **arterias principales** y zonas de alta circulación vehicular
- Intersecciones del **área central** presentan elevado riesgo relativo cuando se ajusta por exposición al tránsito (ej.: Pueyrredón y Santa Fe, ranking 55 en valor absoluto → ranking 2 en tasa)
- El **distrito Centro** concentra el 32% de los siniestros con lesionados y el 46,3% de las denuncias
- La **Avenida Circunvalación** concentra una proporción notable de siniestros fatales, asociada a mayores velocidades de circulación
- En 2024 se registraron **7.790 siniestros con lesionados** y **46 víctimas fatales** en la ciudad

---

## 🖥️ Aplicación Interactiva

La aplicación Shiny permite explorar la siniestralidad vial de Rosario de forma dinámica:

🔗 **[https://malenairisarri.shinyapps.io/siniestralidad_vial_rosario2024/](https://malenairisarri.shinyapps.io/siniestralidad_vial_rosario2024/)**

La app incluye cuatro pestañas:
- **Resumen** — Indicadores descriptivos generales
- **Denuncias** — Distribución espacial de denuncias SIDEAT 2018
- **Siniestros SIES** — Siniestros con lesionados 2024 con análisis temporal
- **Siniestros con fallecidos** — Distribución espacial y temporal de víctimas fatales 2024

---

## 🏛️ Aplicación Práctica

Los rankings de intersecciones críticas construidos en este trabajo pueden utilizarse como insumo directo para la toma de decisiones en seguridad vial, entre ellas:

- **Rotación de cámaras de Control Electrónico** — priorizar la fiscalización en los puntos con mayor índice de siniestralidad
- Instalación o modificación de **señalización vertical y horizontal**
- Implementación o ajuste de **semáforos** en cruces de alto riesgo relativo
- Refuerzo de **controles de alcoholemia** en zonas de mayor incidencia

---

## 🔍 Contexto

A nivel global, los siniestros viales causan la muerte de aproximadamente **1,19 millones de personas por año** (OMS, 2023). En Argentina, durante 2024 se registraron **4.027 víctimas fatales**, la cifra más baja de la última década (ANSV, 2025). En la provincia de Santa Fe se contabilizaron **341 víctimas fatales** en el mismo período.

Este trabajo surge de la necesidad de contar con herramientas analíticas que permitan **focalizar la prevención y optimizar los recursos disponibles** a nivel local, aportando evidencia cuantitativa para el diseño de políticas públicas orientadas a la reducción de la siniestralidad vial.

---

## 📬 Contacto

**Malena Irisarri**  
Licenciada en Estadística — Universidad Nacional de Rosario  
📧 [maleirisarri@hotmail.com]  
🔗 [Malena Irisarri](https://www.linkedin.com/in/malena-irisarri-a54766260/)

---

*Tesina desarrollada con datos provistos por el Ente de la Movilidad de Rosario, la Dirección de Señalización Luminosa de la Municipalidad de Rosario y la Agencia Provincial de Seguridad Vial de Santa Fe.*
