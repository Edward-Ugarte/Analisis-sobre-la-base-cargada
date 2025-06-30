# 🏠 Simulación de Hogares con Análisis Econométrico – Edward Ugarte

Este proyecto implementa una simulación realista de 500 hogares utilizando **Gretl 2025b**, generando ingresos, consumo, educación, estructura familiar, deuda, ahorro y formalidad laboral. A partir de esta base, se estiman modelos econométricos interpretables que explican el consumo, miden elasticidades e identifican diferencias entre hogares formales e informales.

---

## 📦 Archivos incluidos

| Archivo                                                 | Descripción                                                  |
|-----------------------------                            |--------------------------------------------------------------|
| `simulacion_hogares.inp`                                | Script Gretl completo con simulación, regresiones e informes |
| `simulacion con base de datos se puede cambiar          | Base de datos sintética generada con 500 hogares             |
| `tasas_ahorro_resumen.csv`                              | Tasa de ahorro promedio por nivel educativo (exportada)      |
| `README.md`                                             | Este documento explicativo integral                          |

---

## 🧠 Variables simuladas

- `ingresos`: ingreso bruto ajustado por educación
- `consumo`: proporción del ingreso con heterogeneidad
- `deuda`: magnitudes log-normales
- `nmiembros`: número de miembros del hogar
- `educacion`: primaria (0), secundaria (1), superior (2)
- `formalidad`: dummy laboral binaria generada aleatoriamente
- `ahorro`, `tasa_ahorro`: derivados del ingreso y consumo

---

## 📊 Modelos estimados

1. **Modelo 1 – Niveles:**  
   `consumo = β₀ + β₁*ingreso + β₂*deuda + β₃*nmiembros + β₄*formalidad + ε`

2. **Modelo 2 – Log-log:**  
   `log(consumo) = β₀ + β₁*log(ingreso) + β₂*deuda + ...`

3. **Modelo 3 – Hogares formales:**  
   Regresión restringida a `formalidad == 1`

4. **Modelo 4 – Hogares informales:**  
   Regresión restringida a `formalidad == 0`

Cada modelo imprime:
- Coeficientes con **p-valores calculados manualmente**
- Interpretaciones económicas automatizadas por variable
- Diagnóstico por grupo y segmentación robusta

---

## 📈 Resultados destacados

