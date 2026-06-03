# TP-LMC
Trabajo práctico de Laboratorio de Métodos Cuantitativos Aplicado a la Gestión

# Análisis y Estimación de Consumo Energético mediante HDD/CDD

## Integrantes

| Nombre             | GitHub                    |
| ------------------ | ------------------------- |
| Santiago Drelewicz | SantiagoEzequielDrelewicz |
|                    |                           |
|                    |                           |
|                    |                           |
|                    |                           |
| Didier Detchemendy | did1310                   |

---

## Descripción del Proyecto

Este trabajo tiene como objetivo modelar y estimar el consumo energético a partir de variables climáticas utilizando los indicadores **Heating Degree Days (HDD)** y **Cooling Degree Days (CDD)**.

La metodología propuesta busca:

* Integrar múltiples fuentes de datos en un único dataset.
* Calcular indicadores climáticos mensuales.
* Estimar parámetros del modelo de consumo.
* Analizar la relación entre consumo energético y condiciones climáticas.
* Generar proyecciones y visualizaciones para el año 2026.

---

## Estructura del Modelo

El modelo considera una temperatura de confort:

$$
T_c = 20^\circ C
$$

A partir de ella se calculan:

### HDD (Heating Degree Days)

Representa la necesidad de refrigeración.

$$
HDD_d = \max(T_{promedio} - T_c, 0)
$$

Luego:

$$
HDD_{mes} = promedio(HDD_d)
$$

---

### CDD (Cooling Degree Days)

Representa la necesidad de calefacción.

$$
CDD_d = \max(T_c - T_{promedio}, 0)
$$

Posteriormente se agregan los valores diarios para obtener el indicador mensual.

---

## Flujo General de Procesamiento

### 1. Integración de datasets

Se combinan las fuentes de datos disponibles:

```python
df_dataset = pd.concat([
    dataset_a,
    dataset_b,
    dataset_c,
    dataset_d
])
```

---

### 2. Obtención de B_cliente consumo por cliente

---

### 3. Cálculo de HDD y CDD

A partir de la tabla de temperaturas:

```python
T_DIA_HORA
```

Se generan:

* HDD diario
* HDD mensual
* CDD diario
* CDD mensual

---

### 4. Construcción de la función de consumo

La variable objetivo será:

```text
CONSUMO TOTAL FINAL
```

Agrupada por mes y sumada sobre todos los clientes.

Se define:

$$
C(mes) = B + \beta_C CDD(mes) + \beta_H HDD(mes)
$$

como la evolución temporal del consumo mensual.

---

### 5. Ajuste del modelo

Se estudia la relación:

$$
Consumo = f(HDD, CDD)
$$

y se estiman los parámetros correspondientes mediante técnicas de regresión y análisis estadístico.

---

## Distribución de Tareas

| Tarea                                                        | Responsable |
| ------------------------------------------------------------ | ----------- |
| Estimación $β_C$ (2025)                                         | YANI        |
| Estimación $β_H$ (2025)                                         | IVAN        |
| B por cliente + tratamiento HDD/CDD                          | SANTI       |
| Estimación 2026                                              | SOL         |
| Integración del modelo, estructura troncal y visualizaciones | DIDIER      |

---

## Objetivos Pendientes

* [x] Integrar todos los datasets.
* [x] Calcular HDD mensual.
* [x] Calcular CDD mensual.
* [x] Estimar B por cliente.
* [ ] Estimar βC.
* [ ] Estimar βF.
* [ ] Construir el modelo completo.
* [ ] Validar resultados.
* [ ] Generar gráficos finales.
* [ ] Elaborar conclusiones.

---

## Resultados Esperados

* Modelo de consumo energético basado en variables climáticas.
* Estimación de parámetros globales y por cliente.
* Predicción y análisis para el año 2026.
* Visualizaciones que permitan interpretar el impacto de HDD y CDD sobre el consumo.
