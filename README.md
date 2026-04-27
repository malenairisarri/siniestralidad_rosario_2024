# Índices y Mapas Georreferenciados de Siniestralidad Vial en Rosario — 2024

Tesina de Licenciatura en Estadística  
Universidad Nacional de Rosario — Facultad de Ciencias Económicas y Estadística  
**Autora:** Malena Irisarri  
**Directora:** Cristina Cuesta  
**Año:** 2026  

---

## 📋 Descripción

Este proyecto desarrolla un enfoque integral para analizar la siniestralidad vial en Rosario durante 2024, integrando múltiples fuentes de datos y técnicas de análisis espacial.  
Se construyen indicadores que permiten identificar y jerarquizar intersecciones críticas, aportando evidencia para la toma de decisiones en seguridad vial.

---

## 🎯 Objetivos

**Objetivo general:**  
- Identificar y jerarquizar las intersecciones más peligrosas de Rosario en función de la siniestralidad vial en 2024.  

**Objetivos específicos:**  
- Georreferenciar los siniestros viales.  
- Detectar zonas de alta concentración.  
- Evaluar el nivel de peligrosidad de intersecciones.  

---

## ⚙️ Metodología

El análisis se basa en la integración de múltiples fuentes de datos:  
- Siniestros con lesionados (SIES 2024).  
- Denuncias sin lesionados (SIDEAT).  
- Víctimas fatales (APSV).  
- Datos de flujo vehicular (espiras y censos).  

Procesos principales:  
- Limpieza y normalización de direcciones.  
- Georreferenciación y validación espacial.  
- Asignación de siniestros a intersecciones.  
- Estimación del flujo vehicular mediante interpolación espacial (IDW).  

---

---

## 🌐 Aplicación interactiva

Explorá los datos en tiempo real:  
🔗 [Aplicación Shiny](https://malenairisarri.shinyapps.io/siniestralidad_vial_rosario2024/)

La app permite:  
- Visualizar siniestros en mapas interactivos.  
- Analizar patrones espaciales (mapas de puntos y densidad).  
- Explorar patrones temporales (hora, día, mes).  
- Filtrar por zonas y barrios.  

---

## 📊 Índices de siniestralidad

Se construyeron tres indicadores para evaluar la peligrosidad de cada intersección:

- **IVAX (Valor absoluto):**  
  

\[
  IVAX = N_X
  \]

  
  donde \(N_X\) es la cantidad total de siniestros en la intersección \(X\).

- **TX (Tasa):**  
  

\[
  TX = \frac{N_D + (N_L \times 5) + (N_{VF} \times 10)}{\text{Flujo}} \times 10^6
  \]

  
  donde \(N_D\) son siniestros con daños materiales, \(N_L\) con lesionados y \(N_{VF}\) con víctimas fatales.

- **INIX (Índice integrado):**  
  

\[
  INIX = 0.3 \cdot A_X + 0.7 \cdot T'_X
  \]

  
  combinación normalizada de los dos indicadores anteriores.


---

## 📈 Resultados clave

### 🏆 Top 5 — Índice Normalizado Integrado (INIX)

1. Av. Pellegrini y Bv. Oroño — 1,00  
2. Bv. Seguí y Bv. Oroño — 0,79  
3. Av. Newbery y Colectora José María Rosa — 0,75  
4. Bv. Oroño y Av. Battle y Ordóñez — 0,73  
5. Av. Pellegrini y Av. Belgrano — 0,72  

### 📌 Hallazgos

- Las intersecciones más críticas se concentran en arterias principales.  
- El análisis por tasa revela puntos de alto riesgo relativo que no destacan en valores absolutos.  
- El distrito Centro concentra gran parte de los siniestros.  
- La Av. Circunvalación presenta mayor incidencia de siniestros fatales.  
- En 2024 se registraron **7.790 siniestros con lesionados y 46 víctimas fatales**.  

---

## 🏛️ Aplicación práctica

Los resultados pueden utilizarse como insumo para políticas de seguridad vial:  
- Priorización de controles electrónicos.  
- Mejora de señalización vial.  
- Optimización de semaforización.  
- Planificación de operativos de control.

---

## 📬 Contacto

**Malena Irisarri**  
Licenciada en Estadística — Universidad Nacional de Rosario  

📧 maleirisarri@hotmail.com  
🔗 [LinkedIn](https://www.linkedin.com/)  

