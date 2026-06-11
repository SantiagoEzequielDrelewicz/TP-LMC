# Propuesta de presentación — Defensa oral del TP

**Tema:** Estimación del consumo energético a partir de variables climáticas HDD y CDD  
**Duración objetivo:** 5 a 7 minutos  
**Formato sugerido:** 9 diapositivas, con predominio visual y poco texto  
**Criterio general:** cada diapositiva debe sostener una idea central y apoyarse en una figura o métrica del informe.

---

## Diapositiva 1 — Problema de investigación

**Título:** ¿Cuánto explican HDD y CDD del consumo energético?

**Texto para la diapositiva:**

- Objetivo: explicar y estimar el consumo mensual de clientes T1.
- Variables clave: desvíos térmicos respecto de una temperatura de confort.
- Pregunta guía: ¿HDD y CDD alcanzan para predecir consumos futuros?

**Visual sugerido:**

- Usar un esquema simple: Temperatura → HDD/CDD → Consumo energético.
- No incluir todavía gráficos técnicos; reservarlos para las diapositivas siguientes.

**Guion oral sugerido:**

> El trabajo analiza si las condiciones climáticas permiten explicar el consumo eléctrico mensual. La hipótesis de partida es que, cuando la temperatura se aleja de un umbral de confort, aumenta el uso de calefacción o refrigeración y, por lo tanto, el consumo energético. La defensa se organiza mostrando datos, metodología, modelos y validación fuera de muestra.

**Tiempo estimado:** 35-45 segundos.

---

## Diapositiva 2 — Dataset utilizado

**Título:** Datos integrados para construir la base mensual

**Texto para la diapositiva:**

- Consumos históricos 2025 de clientes T1.
- Temperaturas horarias 2025-2026.
- Demanda diaria consolidada.
- Base inicial 2025: 711.829 filas y 26 columnas.
- Agregación final: consumo mensual en GWh.

**Visual sugerido:**

- Diagrama de flujo de datos:
  1. Consumos 2025
  2. Temperaturas horarias
  3. Demanda diaria
  4. Limpieza y agregación
  5. Dataset mensual modelable

**Guion oral sugerido:**

> La base combina información comercial y climática. Primero se filtraron clientes activos, se normalizaron variables numéricas y se evitó la duplicación mensual por cliente conservando la última lectura de cada combinación cliente-mes. Luego el consumo se agregó a escala mensual y se expresó en GWh, lo que permite compararlo directamente con los indicadores térmicos mensuales.

**Tiempo estimado:** 40-50 segundos.

---

## Diapositiva 3 — Metodología de análisis

**Título:** De temperaturas horarias a modelos mensuales

**Texto para la diapositiva:**

- Temperatura de confort: 20 °C.
- Cálculo horario de HDD y CDD.
- Promedio diario y mensual.
- Ajuste de modelos por mínimos cuadrados ordinarios.
- Validación con enero-abril 2026.

**Visual sugerido:**

- Línea metodológica horizontal:
  Temperatura horaria → HDD/CDD → Agregación mensual → Regresión → Validación 2026.

**Guion oral sugerido:**

> La metodología transforma observaciones horarias de temperatura en indicadores térmicos comparables con el consumo mensual. Se usa una temperatura de confort de 20 °C. Por debajo de ese umbral se acumula HDD, asociado a necesidad de calefacción; por encima se acumula CDD, asociado a refrigeración. Luego se ajustan modelos de regresión y se evalúa si el buen ajuste de 2025 se mantiene en 2026.

**Tiempo estimado:** 40-50 segundos.

---

## Diapositiva 4 — HDD y CDD: comportamiento térmico 2025

**Título:** La demanda acompaña la estacionalidad térmica

**Texto para la diapositiva:**

- HDD domina en meses fríos.
- CDD domina en meses cálidos.
- El consumo máximo se concentró en invierno.
- Pico observado: julio 2025, 30,65 GWh.

**Figura del informe:**

- `evolucion_hdd_cdd_2025.png`
- `consumo_total_final_vs_cdd_hdd.png`

**Diseño sugerido:**

- Dos gráficos en paralelo:
  - Izquierda: evolución mensual HDD/CDD.
  - Derecha: consumo total final vs. indicadores térmicos.
- Debajo, una caja con el mensaje clave: **“Los desvíos térmicos explican una parte importante de la variación mensual del consumo.”**

**Guion oral sugerido:**

> La primera evidencia es visual. Los indicadores HDD y CDD muestran una estacionalidad clara. El consumo mensual también se incrementa cuando las temperaturas se alejan del umbral de confort. En 2025 el máximo se observa en julio, con 30,65 GWh, lo que respalda la existencia de una relación térmica relevante, especialmente en invierno.

**Tiempo estimado:** 45-55 segundos.

---

## Diapositiva 5 — Modelos evaluados

**Título:** Tres formas de representar el efecto térmico

**Texto para la diapositiva:**

| Modelo | Idea central | Resultado |
|---|---|---:|
| Modelo 1 | HDD y CDD separados | R² = 0,8572 |
| Modelo 2 | HDD + CDD agregado | R² = 0,8390 |
| Modelo 3 | Variable térmica estacional | R² = 0,7736 |

**Fórmula destacada:**

\[
\widehat{C}(t)=15{,}3351+1{,}5264\,HDD(t)+1{,}7062\,CDD(t)
\]

**Visual sugerido:**

- Usar una tarjeta por modelo.
- Destacar el Modelo 1 con color o borde más fuerte.

**Guion oral sugerido:**

> Se evaluaron tres especificaciones. El Modelo 1 estima efectos separados para frío y calor y obtiene el mayor R². El Modelo 2 resume la desviación térmica total en una sola variable y pierde muy poca capacidad explicativa. El Modelo 3 incorpora una transformación estacional, pero no mejora el ajuste. Por ese motivo, el Modelo 1 se toma como modelo seleccionado para la validación.

**Tiempo estimado:** 50-60 segundos.

---

## Diapositiva 6 — Resultados principales sobre 2025

**Título:** Buen ajuste in-sample del modelo térmico

**Texto para la diapositiva:**

- Modelo seleccionado: regresión lineal múltiple.
- R² = 0,8572; R² ajustado = 0,825.
- Coeficientes positivos y significativos.
- Interpretación: frío y calor aumentan el consumo esperado.

**Figura del informe:**

- `modelo_1_real_vs_predicho_2025.png`
- `modelo_1_real_vs_predicho_scatter.png`
- Opcional complementaria: `sensibilidad_termica_consumo.png`

**Diseño sugerido:**

- Gráfico real vs. predicho como visual principal.
- Scatter real vs. predicho como visual secundario.
- Métrica R² en grande, como número central.

**Guion oral sugerido:**

> El modelo reproduce razonablemente la evolución mensual de 2025. El R² de 0,8572 indica que más del 85 % de la variabilidad mensual del consumo queda explicada dentro de la muestra por HDD y CDD. Además, los coeficientes son positivos, lo cual es consistente con la interpretación física: mayores necesidades de calefacción o refrigeración se asocian con mayor consumo.

**Tiempo estimado:** 50-60 segundos.

---

## Diapositiva 7 — Validación 2026

**Título:** Buen ajuste histórico no garantiza mejor predicción futura

**Texto para la diapositiva:**

- Periodo validado: enero-abril 2026.
- Predicción Modelo 1: 89,41 GWh acumulados.
- MAPE Modelo 1: 8,51 %.
- MAPE empresa: 4,91 %.
- RMSE Modelo 1: ~2 GWh; RMSE empresa: ~1 GWh.

**Figura del informe:**

- `comparacion_modelo_1_empresa_consumo_total_final_2026.png`
- `error_porcentual_vs_hdd.png`
- `error_porcentual_vs_cdd.png`

**Diseño sugerido:**

- Arriba: gráfico comparativo de consumo real, Modelo 1 y empresa.
- Abajo: dos tarjetas de métricas:
  - **Modelo 1:** MAPE 8,51 %, RMSE ~2 GWh.
  - **Empresa:** MAPE 4,91 %, RMSE ~1 GWh.

**Guion oral sugerido:**

> La validación cambia la lectura del resultado. Aunque el Modelo 1 ajusta bien 2025, en enero-abril de 2026 la estimación de la empresa presenta menor error. Esto muestra que HDD y CDD son variables explicativas importantes, pero no suficientes por sí solas para superar una estimación operativa que probablemente captura otros patrones de demanda, calendario o comportamiento histórico.

**Tiempo estimado:** 55-65 segundos.

---

## Diapositiva 8 — Conclusiones y limitaciones

**Título:** HDD y CDD explican, pero no alcanzan solos para predecir

**Texto para la diapositiva:**

**Conclusiones**

- HDD y CDD explican una proporción sustantiva del consumo mensual 2025.
- El Modelo 1 es el mejor ajuste entre las alternativas evaluadas.
- La validación 2026 muestra menor precisión que el método de la empresa.

**Limitaciones**

- Agregación mensual: se pierden dinámicas diarias u horarias.
- Solo clientes T1.
- Validación corta: cuatro meses.
- No se incorporan calendario, rezagos, variables socioeconómicas ni eventos extraordinarios.

**Visual sugerido:**

- Dos columnas: “Lo que el modelo sí logra” vs. “Lo que todavía no captura”.
- Íconos simples: termómetro, calendario, reloj, usuarios.

**Guion oral sugerido:**

> La conclusión principal es equilibrada. Las variables térmicas son útiles y explican gran parte de la variación mensual, pero el desempeño fuera de muestra evidencia límites predictivos. La principal restricción es que el modelo usa solo clima y trabaja con una muestra mensual agregada. Por eso puede captar el patrón general, pero no todos los factores que afectan el consumo real.

**Tiempo estimado:** 45-55 segundos.

---

## Diapositiva 9 — Próximos pasos y cierre

**Título:** Hacia un modelo predictivo operativo más robusto

**Texto para la diapositiva:**

**Próximos pasos**

1. Incorporar variables calendario y rezagos de consumo.
2. Combinar HDD/CDD con demanda histórica y factor estacional.
3. Validar sobre más meses de 2026.
4. Probar modelos por segmento o subconjunto de clientes.
5. Evaluar efectos no lineales y errores heterocedásticos.

**Mensaje final:**

> HDD y CDD son una base explicativa sólida, pero la predicción operativa requiere integrar información térmica con variables de demanda y comportamiento temporal.

**Visual sugerido:**

- Roadmap breve de tres etapas:
  1. Modelo térmico actual.
  2. Modelo híbrido con calendario/demanda.
  3. Validación extendida y uso operativo.

**Guion oral sugerido:**

> Como cierre, el aporte del trabajo es mostrar que HDD y CDD tienen valor explicativo claro, pero que la precisión predictiva mejora cuando se complementan con información adicional. La línea natural de continuidad es construir un modelo híbrido que conserve la interpretación térmica y agregue variables temporales y operativas.

**Tiempo estimado:** 35-45 segundos.

---

# Distribución sugerida del tiempo

| Bloque | Diapositivas | Tiempo aproximado |
|---|---:|---:|
| Introducción y datos | 1-3 | 2:00 min |
| Evidencia y modelos | 4-6 | 2:30 min |
| Validación y cierre | 7-9 | 2:00 min |
| **Total** | **9** | **6:30 min** |

---

# Recomendaciones de diseño para Canva, Gamma o PowerPoint

- Usar máximo 3-5 bullets por diapositiva.
- Priorizar gráficos ya incluidos en el informe.
- Mantener una métrica central por diapositiva cuando corresponda.
- Evitar tablas extensas; la única tabla recomendable es la comparación de modelos.
- Usar colores consistentes:
  - Azul para consumo real.
  - Naranja para Modelo 1.
  - Verde o gris para estimación de la empresa.
- Incluir títulos interpretativos, no solo descriptivos.
- Evitar leer las diapositivas: el texto principal debe estar en el guion oral.

---

# Figuras del informe utilizadas

- `evolucion_hdd_cdd_2025.png`
- `consumo_total_final_vs_cdd_hdd.png`
- `sensibilidad_termica_consumo.png`
- `modelo_1_real_vs_predicho_2025.png`
- `modelo_1_real_vs_predicho_scatter.png`
- `comparacion_modelo_1_empresa_consumo_total_final_2026.png`
- `error_porcentual_vs_hdd.png`
- `error_porcentual_vs_cdd.png`

---

# Checklist final de coherencia

- La presentación se basa en los resultados del informe.
- Se usan todas las figuras incluidas en el informe.
- La duración estimada queda dentro del rango de 5 a 7 minutos.
- Se comunica la diferencia entre ajuste in-sample y validación fuera de muestra.
- Las conclusiones no exageran el alcance predictivo de HDD y CDD.
