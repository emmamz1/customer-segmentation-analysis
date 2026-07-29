# Customer Segmentation Analysis
## Segmentación de 197K Clientes para Estrategia de Marketing & Retención

---

## Resumen Ejecutivo

Este proyecto analiza **197,000 clientes** y los divide en **6 segmentos** basándose en cuándo compraron y cuánto gastaron. 

**Hallazgo clave:** 32% de clientes generan 65% del revenue (Pareto).

**Resultado accionable:** Estrategia diferenciada por segmento con potencial de **+$16.4M** en revenue.

---

## Objetivo

Responder preguntas de negocio críticas:
- ¿Cuáles son nuestros mejores clientes? → **Champions (31K clientes)**
- ¿A quién debería retener? → **High-Value (31K clientes no compran hace 1 año)**
- ¿Dónde invertir marketing? → **32% VIP clientes = 65% revenue**
- ¿Quién es perdida? → **Lost (31K clientes, no vale invertir)**

---

## Dataset

| Métrica | Valor |
|---|---|
| **Clientes únicos** | 197,000 |
| **Transacciones** | 200,000 |
| **Período** | Enero 2023 - Diciembre 2024 |
| **Revenue total** | $142.4M |
| **Categorías** | 4 (Accessories, Clothing & Apparel, Electronics, Home & Furniture) |

---

---

## Cómo usar este repo

### Opción 1: Explorar en Colab (Recomendado)
1. Clona el repo
2. Sube los archivos a Colab
3. Abre `03_Storytelling.ipynb` (es el reporte final, sin código técnico)

### Opción 2: Ejecutar localmente
```bash
# Clonar
git clone https://github.com/[tu-usuario]/customer-segmentation.git
cd customer-segmentation

# Crear environment
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# Instalar dependencias
pip install pandas numpy matplotlib seaborn jupyter

# Ejecutar Jupyter
jupyter notebook

# Abrir notebooks/03_Storytelling.ipynb
```

### Opción 3: Solo leer los resultados
- Abre `notebooks/03_Storytelling.ipynb` en GitHub (GitHub renderiza automáticamente)
- Verás los gráficos y conclusiones sin ejecutar nada

---

## Hallazgos Principales

### 1. **Regla de Pareto: 32% de Clientes = 65% de Revenue**

| Segmento | Clientes | % Clientes | Revenue | % Revenue |
|---|---|---|---|---|
| Champions | 31,924 | 16% | $43.8M | 31% |
| High-Value | 31,083 | 16% | $42.2M | 30% |
| Loyal | 23,737 | 12% | $25.4M | 18% |
| **VIP Total** | **86,744** | **32%** | **$111.4M** | **65%** |
| — | — | — | — | — |
| At-Risk | 47,013 | 24% | $12.7M | 9% |
| Potential | 31,339 | 16% | $11.9M | 8% |
| Lost | 31,904 | 16% | $6.4M | 4% |
| **Bajo Valor Total** | **110,256** | **56%** | **$31.0M** | **21%** |

---

### 2. **Diferencia entre Global vs Normalizado**

**Comparación Champions vs Potential:**

| Versión | Ratio | Qué Significa |
|---|---|---|
| Global (Notebook 02) | 3.9x | Champions gastan 3.9x más (SESGADO: mezcla categorías) |
| Por Categoría (Notebook 02b) | 2.8x | Champions gastan 2.8x más DENTRO de su categoría (CORRECTO) |

**Conclusión:** El 3.9x NO es por "calidad de cliente", es porque Champions compra electrónica ($1,300 promedio) y Potential compra ropa ($350 promedio).

Cuando normalizamos, el patrón es consistente en todas las categorías (~2.8x).

---

### 3. **High-Value: La Oportunidad Real**

| Métrica | Champions | High-Value |
|---|---|---|
| Gasto promedio | $1,371 | $1,358 |
| Últimas compra | Recientemente | Hace 1+ año |
| Recency Score | Alto (5) | Bajo (1-2) |
| Revenue potencial | Actual | +$42M si reactivamos |

**Insight:** High-Value gasta IGUAL que Champions pero no compran hace mucho. 
Si implementamos estrategia de reactivación (email + descuento), recuperamos ~20% = **$8.6M adicionales**.

---

### 4. **Distribución de Segmentos es Universal**

Cada categoría tiene distribución similar:
- ~24% At-Risk
- ~16% Champions
- ~16% Potential
- ~16% Lost
- ~16% High-Value
- ~12% Loyal

**Esto indica:** El segmento de un cliente NO depende de qué compra, sino de CUÁNDO y CUÁNTO compró relativamente a su categoría.

---

## Recomendaciones por Segmento

### Champions (Mantener)
**Inversión:** Alta | **ROI:** Garantizado

- Email semanal con novedades
- Acceso early-access a productos
- Programa de referral
- VIP customer service

---

### High-Value (URGENTE - Reactivar)
**Inversión:** Media | **ROI:** Muy Alto

- Email personalizado: "Te extrañamos"
- Descuento "Bienvenida de vuelta" (15-20%)
- Contacto directo si es posible
- Regalo pequeño de reactivación

**Potencial:** $8.6M si 20% vuelve

---

### Loyal (Convertir a Champions)
**Inversión:** Media | **ROI:** Alto

- Loyalty program (puntos → descuentos)
- Email cada 2 semanas
- Recompensas progresivas
- Acceso a contenido exclusivo

---

### Potential (Upsell)
**Inversión:** Baja | **ROI:** Medio

- Email educativo sobre productos premium
- Bundle offers
- Recomendaciones personalizadas
- Testimonios de Champions

---

### At-Risk (Último Intento)
**Inversión:** Muy Baja | **ROI:** Bajo

- "Última oportunidad" email con descuento fuerte
- Pregunta directa: ¿Qué salió mal?
- Si no responden → parar inversión

---

### Lost (Abandonar)
**Inversión:** Ninguna | **ROI:** Negativo

- Email único de despedida
- Guardar para futuro "re-targeting" especial
- **No invertir en traerlos de vuelta**

---

## ROI Proyectado

Si implementas estas estrategias correctamente:

| Acción | Grupo | Éxito Esperado | Impacto |
|---|---|---|---|
| Reactivación | High-Value | 20% vuelven | +$8.6M |
| Retención | At-Risk | 5% se quedan | +$3.0M |
| Upsell | Potential | 10% sube gasto | +$2.8M |
| Loyalty | Loyal | 15% sube nivel | +$2.0M |
| — | **TOTAL** | — | **+$16.4M (11% revenue)** |

---

## Metodología

### RFM Segmentation (Adaptado)

Usamos segmentación **RFM** modificada para one-time buyers:

**R (Recency):** Días desde última compra
- Score 5: 0-70 días (reciente) 
- Score 1: 281-730 días (antiguo) 

**M (Monetary):** Revenue total por cliente
- **Global (Notebook 02):** M_Score sobre TODO el dataset
- **Por Categoría (Notebook 02b):** M_Score recalculado dentro de cada categoría

**Segmentos (R × M):**
- R≥4 + M≥4 = Champions
- R≥4 + M≥2 = Potential
- R≤2 + M≥4 = High-Value
- R≤2 + M≤2 = Lost
- R≥3 + M≥3 = Loyal
- Otros = At-Risk

### Por Qué No Frequency?

El dataset tiene ~97% de clientes con 1 sola compra. Sin histórico de recompra, 
Frequency no es un predictor útil. Usamos solo R + M (adaptado para categoría).


## Estructura final del repo
```
customer-segmentation/
├── README.md                             
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Segmentacion_Global.ipynb
│   ├── 02b_Segmentacion_PorCategoria.ipynb
│   └── 03_Storytelling.ipynb
└── data/
    ├── product_sales_dataset_SAMPLE.csv
    ├── customer_segmentation_SAMPLE.csv
    └── customer_segmentation_BY_CATEGORY_SAMPLE.csv
```

## Tech Stack

| Herramienta | Propósito |
|---|---|
| **Python 3.x** | Análisis |
| **Pandas** | Manipulación de datos |
| **NumPy** | Cálculos numéricos |
| **Matplotlib & Seaborn** | Visualizaciones |
| **Jupyter** | Notebooks interactivos |

---
## Datos

### Muestras Incluidas en el Repo

El repositorio incluye **muestras pequeñas (2,000 filas)** de los datasets para demostración. Esto sirve para ver la estructura y ejecutar los notebooks en Colab sin descargar datos gigantes.

---

### Datos Completos (197K Clientes)

Para reproducir el análisis completo, necesitás el dataset original:

**Opción A: Descargar de Kaggle (Recomendado)**

1. Descarga aquí: [Product Sales Dataset 2023-2024](https://www.kaggle.com/datasets/yashyennewar/product-sales-dataset-2023-2024)
2. Renómbralo a `product_sales_dataset_final.csv`
3. Sube a `/data/` en tu copia local del repo
4. Ejecuta `notebooks/02_Segmentacion_Global.ipynb` para generar automáticamente:
   - `customer_segmentation.csv`
   - `customer_segmentation_BY_CATEGORY.csv`

**Opción B: Ejecutar en Colab (Sin descargar)**

1. Abre `notebooks/02_Segmentacion_Global.ipynb`
2. Sube `product_sales_dataset_final.csv` de Kaggle directamente a Colab
3. Ejecuta las celdas
4. Descarga los CSVs generados desde Colab

**Opción C: Contactarme**

Si necesitás los datasets completos procesados, contactame: emmamendoza170@gmail.com

---
## Nota Sobre Tamaño

Los archivos completos pesan +25MB cada uno, por eso no están en GitHub. 
Las muestras (SAMPLE) pesan ~2MB y sirven para explorar la estructura del análisis.

---
## Notas Importantes

### Sobre el Sesgo de Categoría

**Notebook 02** compara clientes de TODAS las categorías usando M_Score global.
Resultado: "Champions es 3.9x mejor que Potential"

**Problema:** No es justo. Champions compra electrónica cara ($1,300 promedio).
Potential compra ropa barata ($350 promedio).

**Solución:** **Notebook 02b** recalcula M_Score dentro de cada categoría.
Resultado: "Champions es 2.8x mejor que Potential" (más justo y consistente).

**Recomendación:** Usa Notebook 02b para decisiones. Notebook 02 es solo para contexto Pareto.

---

### Limitaciones del Dataset

1. **One-time buyer:** 97% de clientes compran solo 1 vez → sin histórico de recompra
2. **Sin demografía:** No hay edad, género, ubicación (solo región de compra)
3. **Sin satisfacción:** No hay reviews/ratings, churn scoring basado en comportamiento
4. **Ventana temporal:** 2 años (2023-2024), limitado para proyecciones a largo plazo
5. **Sin devoluciones:** No hay datos de returns, CLV podría estar sesgado hacia arriba

---

## Autor

**Emmanuel Mendoza**
-  emmamendoza170@gmail.com
-  [LinkedIn](https://linkedin.com/in/emmanuel-mendoza17)
-  [GitHub](https://github.com/emmamz1)

Estudiante de Tecnicatura en Inteligencia Artificial (UNR)
Especializado en BI & Análisis de Datos

---

## Licencia

Este proyecto es de uso libre para propósitos educativos y comerciales.

---

## Contribuciones

¿Sugerencias? ¿Mejoras? Abrí un issue o contactame directamente.

---

## Preguntas Frecuentes

**P: ¿Por qué hay dos notebooks de segmentación?**  
R: Notebook 02 muestra análisis global (util para Pareto). Notebook 02b corrige el sesgo de categoría (recomendado para decisiones).

**P: ¿Cómo sé si una estrategia funcionó?**  
R: Segmenta de nuevo 3 meses después. Si High-Value reactivation generó 20% de vuelta, es éxito.

**P: ¿Puedo usar esto en otra industria?**  
R: Sí. La metodología RFM funciona en retail, SaaS, servicios, etc. Solo cambia los datos.

---

**Última actualización:** Julio 2024  
**Datos:** 197,000 clientes | 200,000 órdenes | $142.4M revenue  
**Status:** Completo
