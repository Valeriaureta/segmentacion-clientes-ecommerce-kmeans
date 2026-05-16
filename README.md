# Segmentación Inteligente de Clientes E-commerce con K-means

> Modelo de clustering no supervisado que identifica perfiles de clientes según gasto, visitas, transacciones, duración de sesión y antigüedad — permitiendo campañas personalizadas de conversión, fidelización, reactivación y retención temprana.

**Autor(a):** Valeria Thais Ureta Llanque  
**Metodología:** CRISP-DM  
**Programa:** Diplomado Data Scientist  
**Profesor:** Arnaldo Alvarado Vallejos (Chapter Lead BCP)  
**Stack:** Python 3.12 | pandas | numpy | matplotlib | seaborn | scikit-learn | openpyxl

---
# Problema identificado

Una empresa de e-commerce busca mejorar sus campañas de marketing, fidelización y retención de clientes. Actualmente, la base de usuarios contiene clientes con distintos patrones de gasto, frecuencia de visita, duración de sesión, número de transacciones y antigüedad; sin embargo, estas diferencias no están organizadas en perfiles accionables para negocio.

El problema central es que las campañas pueden terminar siendo genéricas: se envía la misma comunicación a clientes de alto gasto, clientes antiguos con baja actividad, visitantes frecuentes que no compran y usuarios recientes con potencial de retención. Esto reduce la eficiencia comercial, aumenta el riesgo de abandono y limita la personalización de ofertas.

El objetivo del proyecto es aplicar técnicas de segmentación no supervisada para identificar grupos de clientes con comportamientos similares y convertir esos grupos en acciones concretas de marketing, conversión, reactivación y fidelización.

**Modelo seleccionado:** K-means clustering  
**Modelo contrastado:** DBSCAN  
**Unidad de análisis:** Cliente e-commerce  
**Variables principales:** gasto promedio mensual, frecuencia de visita, duración promedio de sesión, número de transacciones, antigüedad del cliente, canal preferido y región.  
**Resultado final:** 4 segmentos accionables de clientes y una matriz de priorización comercial.
---
## Estructura del proyecto

```text
.
├── TRABAJO_FINAL_VALERIAURETA.ipynb              # Notebook principal: EDA, preparación, modelado y reporte final
├── ecommerce_customers.xlsx                      # Dataset original
├── clientes_segmentados.xlsx                     # Dataset con etiqueta de segmento
├── matriz_priorizacion_segmentos.xlsx            # Matriz ejecutiva de priorización comercial
├── requirements.txt
