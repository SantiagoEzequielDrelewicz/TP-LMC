# AGENTS.md

## Proyecto

Trabajo Práctico de Análisis de Datos y Modelado Estadístico.

El repositorio contiene:

* la consigna oficial del trabajo;
* el notebook con el análisis completo;
* el informe académico en LaTeX;
* las figuras exportadas desde el notebook.

---

# Jerarquía de fuentes

En caso de conflicto entre archivos:

1. Notebook (`*.ipynb`)
2. Consigna (`*.pdf`)
3. Informe existente (`*.tex`)

El notebook es siempre la fuente de verdad.

---

# Objetivo general

El objetivo del informe es comunicar de manera rigurosa:

* la pregunta de investigación;
* los datos utilizados;
* la metodología aplicada;
* los resultados obtenidos;
* las limitaciones del análisis;
* las conclusiones alcanzadas.

El informe no debe ser una descripción del código sino una narrativa analítica.

---

# Principios obligatorios

## Veracidad

No inventar:

* resultados;
* métricas;
* coeficientes;
* valores numéricos;
* interpretaciones;
* conclusiones.

Toda afirmación cuantitativa debe surgir del notebook.

---

## Calidad académica

Utilizar:

* español académico;
* tercera persona o voz impersonal;
* redacción formal;
* interpretación basada en evidencia.

Evitar:

* lenguaje coloquial;
* afirmaciones vagas;
* texto redundante;
* descripciones superficiales de gráficos.

---

## Interpretación

Priorizar siempre:

1. qué muestra el resultado;
2. qué significa;
3. por qué es relevante;
4. cómo responde la pregunta de investigación.

No limitarse a describir gráficos.

---

# Figuras

La carpeta `figuras/` debe inspeccionarse completamente.

Todas las imágenes deben:

* aparecer en el informe;
* tener caption;
* tener label;
* estar citadas desde el texto.

---

## Agrupación de figuras

Si dos o más imágenes representan el mismo análisis:

* agruparlas mediante subfiguras;
* utilizar `subcaption`;
* mantener consistencia visual.

No crear figuras redundantes.

---

# Tablas

Utilizar tablas únicamente cuando aporten información imposible de comunicar razonablemente mediante texto o gráficos.

En caso contrario, preferir:

* explicación textual;
* figuras;
* síntesis narrativa.

---

# Referencias cruzadas

Utilizar siempre:

\ref{...}

Evitar referencias manuales del tipo:

* "Figura 1"
* "Tabla 2"

---

# Validación final

Antes de finalizar cualquier tarea:

* verificar consistencia entre notebook e informe;
* verificar referencias cruzadas;
* verificar figuras;
* verificar compilación LaTeX;
* verificar cumplimiento de la consigna.

---

# Entregables

Toda modificación debe producir archivos listos para compilar y entregar.
