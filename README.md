# Análisis salarial del sector IT argentino — Sysarmy 2026

> **EN:** Exploratory and inferential analysis of the 2026 Sysarmy IT salary survey (Argentina): data cleaning, salary-by-technology EDA, and a study of the gender wage gap (Welch test + log-linear regression). Code in Python; notebooks in Spanish.

Análisis de la encuesta abierta de sueldos IT de Sysarmy (2026), en dos partes complementarias:

- **01_analisis_exploratorio.ipynb** — Curación de datos y análisis exploratorio: qué lenguajes se asocian a los mejores salarios, y relaciones entre salario, edad, seniority, modalidad y nivel de estudios.
- **02_brecha_salarial.ipynb** — Estudio inferencial de la brecha salarial de género: estimación, intervalo de confianza, test de Welch, potencia y descomposición de la brecha (cruda → por seniority → ajustada por regresión).

## Datos
Encuesta abierta y voluntaria de Sysarmy (2026), ~4.900 respuestas del sector IT argentino.

## Metodología destacada
- Detección de outliers con vallas de Tukey (1,5·IQR) sobre log(salario), por la fuerte asimetría de la distribución salarial.
- Inferencia con test de Welch y verificación no paramétrica.
- Brecha ajustada vía regresión log-lineal, controlando seniority, edad y modalidad de forma simultánea.

## Hallazgos principales
**Lenguajes (Parte 1):** Java es el lenguaje asociado a los salarios más altos, seguido por TypeScript y Bash/Shell, y luego Python.

**Brecha de género (Parte 2):**
- Brecha de medias cruda: ~18 % a favor de los varones (p ≈ 1,6·10⁻²²).
- A igual seniority la brecha persiste y crece: casi nula en Junior, ~13 % en Senior.
- Brecha ajustada (neta de seniority, edad y modalidad): −11,6 % (IC 95 %: −14,7 % a −8,4 %).

## Stack
Python · pandas · NumPy · SciPy · statsmodels · seaborn · matplotlib

## Reproducir
```bash
pip install -r requirements.txt
jupyter notebook
```

## Limitaciones
Muestra auto-seleccionada, comparación cis-binaria, análisis asociativo (no causal).
