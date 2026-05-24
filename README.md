# Segmentación Inteligente de Clientes E-commerce con K-means

> Modelo de clustering no supervisado que identifica perfiles de clientes según gasto, visitas, transacciones, duración de sesión y antigüedad — permitiendo campañas personalizadas de conversión, fidelización, reactivación y retención temprana.

**Autor(a):** Valeria Thais Ureta Llanque  
**Metodología:** CRISP-DM  
**Programa:** Diplomado Data Scientist  
**Nota:** 20  
**Profesor:** Arnaldo Alvarado Vallejos (Chapter Lead BCP)  
**Stack:** Python 3.12 | pandas | numpy | matplotlib | seaborn | scikit-learn | openpyxl

---
# Problema identificado

Una empresa de e-commerce busca mejorar sus campañas de marketing, fidelización y retención de clientes. Actualmente, la base de usuarios contiene clientes con distintos patrones de gasto, frecuencia de visita, duración de sesión, número de transacciones y antigüedad; sin embargo, estas diferencias no están organizadas en perfiles accionables para negocio.

El problema central es que las campañas pueden terminar siendo genéricas: se envía la misma comunicación a clientes de alto gasto, clientes antiguos con baja actividad, visitantes frecuentes que no compran y usuarios recientes con potencial de retención. Esto reduce la eficiencia comercial, aumenta el riesgo de abandono y limita la personalización de ofertas.

El objetivo del proyecto es aplicar técnicas de segmentación no supervisada para identificar grupos de clientes con comportamientos similares y convertir esos grupos en acciones concretas de marketing, conversión, reactivación y fidelización.

**Dataset:** `ecommerce_customers.xlsx` 
**Granularidad del dataset:** Cada registro representa un cliente único identificado por `customer_id`, con sus respectivas características y variables de comportamiento asociadas.

---

## Estructura del proyecto

```text
.
├── TRABAJO_FINAL_VALERIA_URETA.ipynb           # Notebook principal: EDA, preparación, modelado y reporte final
├── ecommerce_customers.xlsx                   # Dataset original
├── clientes_segmentados.xlsx                  # Dataset con etiqueta de segmento
├── matriz_priorizacion_segmentos.xlsx         # Matriz ejecutiva de priorización comercial
├── requirements.txt
└── README.md
```

---

# Notebook Principal

## `TRABAJO_FINAL_VALERIA_URETA.ipynb`

El notebook contiene:

1. Entendimiento del problema de negocio.
2. Análisis exploratorio de datos.
3. Revisión de calidad de datos.
4. Tratamiento de outliers mediante capping.
5. Escalamiento de variables numéricas.
6. Comparación entre DBSCAN y K-means.
7. Evaluación del número óptimo de clusters.
8. Perfilamiento de segmentos.
9. Recomendaciones accionables por segmento.
10. Exportación de archivos para uso operativo.

DBSCAN no fue seleccionado porque tendía a generar un solo grupo grande o demasiados puntos de ruido. K-means permitió obtener segmentos más balanceados e interpretables para negocio.

---
## Métricas del Modelo Final

| Métrica | Valor |
|---|---:|
| Silhouette Score | 0.15 |
| Davies-Bouldin | 1.74 |
| Calinski-Harabasz | 81.98 |
| Inercia | 1,671.30 |

Aunque el silhouette es moderado, se priorizó una solución interpretable y accionable para campañas comerciales.

---
## Segmentos Identificados

| Segmento | Perfil | Clientes | % base | Acción principal |
|---:|---|---:|---:|---|
| 0 | Clientes leales y transaccionales | 114 | 22.80% | Fidelización y aumento de ticket |
| 1 | Visitantes frecuentes de baja conversión | 125 | 25.00% | Conversión y remarketing |
| 2 | Clientes antiguos con baja actividad | 134 | 26.80% | Reactivación y prevención de abandono |
| 3 | Clientes de alto gasto reciente | 127 | 25.40% | Retención temprana y cross-selling |

---  

## Archivos Generados

- `clientes_segmentados.xlsx`: base de clientes con la etiqueta de segmento asignada.
- `matriz_priorizacion_segmentos.xlsx`: resumen ejecutivo con prioridades, acciones recomendadas y KPIs sugeridos.

---

## Conclusión

El modelo permitió identificar cuatro segmentos accionables de clientes. La recomendación principal es priorizar la retención temprana del segmento de alto gasto reciente y ejecutar campañas de conversión/reactivación para los segmentos con baja conversión o baja actividad.

---

## Limitaciones

- El dataset contiene 500 clientes.
- No se cuenta con una variable real de churn o rentabilidad futura.
- Las recomendaciones deben validarse con campañas piloto o pruebas A/B.
