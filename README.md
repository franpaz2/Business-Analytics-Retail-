# Retail Business Analytics
**Market Entry Strategy & Data-Driven Business Model para Cafetería de Especialidad**

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Data Storytelling](https://img.shields.io/badge/Data_Storytelling-4B0082?style=for-the-badge)
![Data Engineering](https://img.shields.io/badge/Data_Wrangling-F24E1E?style=for-the-badge)
![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-0048C0?style=for-the-badge)

> **Retail Business Analytics** es un proyecto integral de inteligencia de mercado diseñado para validar la viabilidad comercial de una cafetería en Torrevieja. Combina un pipeline robusto de ingeniería de datos (ETL en R) con un análisis de negocio profundo para transformar datos demográficos y de movilidad crudos en decisiones operativas y financieras accionables.

---

## El Reto de Negocio
El sector del Retail y la hostelería presenta una alta tasa de fracaso durante el primer año debido a decisiones basadas en la intuición. El reto consistió en evaluar un espacio comercial reducido (25m2 útiles) con un aforo máximo de 15 personas. El objetivo era maximizar la rentabilidad del metro cuadrado definiendo el *target* óptimo, las franjas horarias de mayor conversión y la estrategia de producto basándonos en la evolución demográfica real y el análisis de la competencia.

---

## Arquitectura Técnica y Procesamiento de Datos (Data Wrangling)

Para garantizar la precisión de las conclusiones comerciales, se desarrolló un pipeline de datos estructurado en el entorno R Markdown, procesando múltiples fuentes de datos en bruto (.csv).

### 1. Stack Tecnológico
* **Lenguaje:** R
* **Manipulación y ETL:** `dplyr`, `readr`
* **Series Temporales:** `lubridate`
* **Visualización Avanzada:** `ggplot2`

### 2. Pipeline ETL y Limpieza de Datos
* **Regex y Type Casting:** Limpieza algorítmica de formatos europeos (eliminación de separadores de miles mediante `gsub`) y conversión estricta de cadenas de texto a variables numéricas continuas para habilitar el cálculo estadístico.
* **Procesamiento de Series Temporales:** Desestructuración de campos temporales anidados (ej. "2023M01") extrayendo sub-cadenas para instanciar variables independientes de año (`year`) y mes (`month`).
* **Enriquecimiento de Datos (Joins):** Cruce de subtablas espaciales y demográficas (mediante `merge()`) para consolidar volúmenes poblacionales con métricas paramétricas de gasto por nacionalidad.

### 3. Feature Engineering y Modelado Dimensional
* **Normalización de Estacionalidad:** Cálculo de la tasa de estacionalidad normalizando el peso turístico mensual respecto a la sumatoria anual total.
* **KPIs Sintéticos de Negocio:** Diseño de nuevas variables derivadas en cascada (Pipeline de `dplyr`), destacando el cálculo predictivo del *Impacto Total* (población multiplicada por gasto promedio cruzado entre turistas y residentes locales).
* **EDA Multidimensional:** Programación de gráficos de alta densidad en `ggplot2` mapeando 4 dimensiones matemáticas simultáneas en el análisis de competencia: Distancia al local (Eje X), Puntuación (Eje Y), Volumetría de reseñas (Tamaño) y Ticket Medio (Gradiente de color continuo).

---

## Descubrimientos Clave y Estrategia Accionable (Key Insights)

El cruce de datos demográficos y el pipeline de *Feature Engineering* revelaron los siguientes ejes estratégicos:

### 1. Segmentación y Público Objetivo
* **Cambio Sociodemográfico:** El porcentaje de población española ha descendido al 47.9%, mientras que la población ucraniana y del norte de Europa ha experimentado un incremento crítico. 
* **Estrategia Omnicanal:** Implementación obligatoria de menús digitales (QR) en Español, Inglés, Ruso y Ucraniano.

### 2. Optimización Operativa por Franjas Horarias
* **07:30 – 10:00 (35% del gasto):** Tráfico dominado por trabajadores locales. Requiere un modelo operativo centrado en la rapidez y el formato *Take Away* para mitigar la limitación de aforo.
* **10:00 – 13:00 (30% del gasto):** Dominado por residentes extranjeros orientados a un consumo prolongado (*Brunch*).
* **Adaptación de Producto:** Alineación de la oferta con tendencias detectadas (productos *gluten-free*, veganos y leches vegetales), ajustando el ticket medio al crecimiento sostenido de la renta per cápita del municipio.

---

## Cómo reproducir el análisis

1. Clona el repositorio:
```bash
git clone [https://github.com/tu-usuario/retail-business-analytics.git](https://github.com/tu-usuario/retail-business-analytics.git)
cd retail-business-analytics
install.packages(c("dplyr", "ggplot2", "readr", "lubridate"))
```
Ejecuta el notebook limpieza_graficas.Rmd para compilar el pipeline de datos y generar el documento analítico final.
Análisis y Data Engineering co-desarrollado por el ecosistema Iceberg Datum.
