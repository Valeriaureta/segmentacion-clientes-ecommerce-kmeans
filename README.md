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

**Dataset:** ecommerce_customers.xlsx  
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

Contiene el flujo completo del proyecto:

1. **Business Understanding**  
   Formalización del problema de negocio, objetivo analítico y definición del valor esperado para marketing y retención.

2. **EDA**  
   Exploración inicial del dataset, análisis de variables, revisión de nulos, duplicados, distribuciones, categorías, outliers y matriz de correlación.

3. **Data Preparation**  
   Limpieza de datos, tratamiento de outliers mediante capping, encoding de variables categóricas y escalamiento de variables numéricas.

4. **Modeling**  
   Evaluación de DBSCAN y K-means. Se selecciona K-means por su mayor interpretabilidad y utilidad para campañas comerciales.

5. **Evaluation**  
   Evaluación del número de clusters mediante métricas como inercia, silhouette, Davies-Bouldin y Calinski-Harabasz.

6. **Business Deployment**  
   Traducción de segmentos en acciones comerciales y exportación de archivos para uso operativo.

---

# Hallazgos por Fase

## 1. Business Understanding

Se identificó que la empresa necesita comprender los distintos patrones de comportamiento de sus clientes para evitar campañas genéricas y mejorar la toma de decisiones comerciales. La segmentación permite diferenciar perfiles de alto valor, baja conversión o riesgo de abandono, facilitando estrategias específicas de fidelización, conversión, reactivación y retención.

---

## 2. Data Understanding & EDA

El dataset contiene 500 clientes y 8 variables.

- No se identificaron valores nulos.
- No se encontraron duplicados.
- `customer_id` funciona como identificador único.

Los análisis exploratorios mostraron diferencias relevantes en:

- gasto,
- visitas,
- transacciones,
- antigüedad.

También se observó que las variables poseen escalas distintas, por lo que fue necesario aplicar escalamiento antes del clustering.

---

## 3. Data Preparation

- Se excluyó `customer_id` del modelamiento.
- Se aplicó tratamiento de outliers mediante capping.
- Se realizó escalamiento de variables numéricas.

Las variables categóricas se utilizaron principalmente para interpretación posterior de segmentos.

---

## 4. Modeling

Se evaluaron dos algoritmos:

- DBSCAN
- K-means

DBSCAN no fue seleccionado porque tendía a generar un solo grupo grande o demasiados puntos de ruido.

K-means fue seleccionado como modelo final por generar segmentos más balanceados, interpretables y accionables para negocio.

---

## 5. Evaluation

Se seleccionó **K-means con 4 clusters** combinando métricas técnicas e interpretabilidad de negocio.

### Segmentos Finales

| Segmento | Descripción |
|---|---|
| 0 | Clientes leales y transaccionales |
| 1 | Visitantes frecuentes de baja conversión |
| 2 | Clientes antiguos con baja actividad |
| 3 | Clientes de alto gasto reciente |

---

## 6. Business Deployment

Se construyó una matriz de priorización para traducir los clusters en acciones comerciales concretas.

También se generaron archivos exportables para uso operativo:

- `clientes_segmentados.xlsx`
- `matriz_priorizacion_segmentos.xlsx`
  
Este output permite llevar la segmentación a una herramienta de CRM o marketing automation para activar campañas diferenciadas

---

# Resultado Final

El modelo final identifica cuatro segmentos accionables de clientes e-commerce:

## 1. Clientes leales y transaccionales

**Recomendación:**  
Fidelización, beneficios VIP, bundles y aumento de ticket promedio.

---

## 2. Visitantes frecuentes de baja conversión

**Recomendación:**  
Campañas de conversión, remarketing y optimización del checkout.

---

## 3. Clientes antiguos con baja actividad

**Recomendación:**  
Campañas de reactivación y prevención de abandono.

---

## 4. Clientes de alto gasto reciente

**Recomendación:**  
Retención temprana, cross-selling y beneficios por segunda compra.

---

# Impacto de Negocio Esperado

La segmentación permite pasar de campañas genéricas a campañas personalizadas por perfil de cliente.

### Beneficios esperados:

- Incremento de ventas.
- Mejora en la conversión.
- Reducción del abandono.
- Mayor retención de clientes valiosos.
- Mejor asignación del presupuesto de marketing.
- Priorización de segmentos estratégicos.

---

