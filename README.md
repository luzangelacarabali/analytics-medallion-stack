# Analytics Medallion Stack

Proyecto 3 — Frameworks y Herramientas para Big Data  
Uso de Arquitectura Lakehouse en Azure Databricks con pipeline de ingesta y cargue de datos.

---

# Objetivo

Implementar una arquitectura Lakehouse usando Azure Databricks y el patrón Medallion Architecture (Bronze → Silver → Gold), migrando un pipeline open source hacia una solución cloud basada en Delta Lake y Apache Spark.

El proyecto implementa procesos de:

- Ingesta de datos
- Transformación
- Validación de calidad
- Agregaciones analíticas
- Orquestación de pipelines
- Consumo desde DuckDB
- Visualización en Power BI

---

# Arquitectura Implementada

## Arquitectura Medallion

### Bronze Layer
- Datos crudos
- Formato Parquet
- Escritura overwrite
- Ingesta mensual
- 2 meses del año 2023

### Silver Layer
- Datos limpios y normalizados
- Formato Delta
- Escritura MERGE
- Manejo de duplicados
- Validación de registros insertados/actualizados
- Columna `load_date`

### Gold Layer
- KPIs y métricas analíticas
- Formato Delta
- Escritura MERGE
- Agregaciones de negocio
- Columna `load_date`

---

# Tecnologías Utilizadas

- Azure Data Lake Gen2
- Azure Databricks
- Unity Catalog
- Delta Lake
- Apache Spark
- PySpark
- DuckDB
- Power BI
- Python

---

# Infraestructura

Servicios desplegados:

- Azure Data Lake Gen2
- Unity Catalog
- Delta Tables
- Apache Spark Cluster
- Databricks Jobs
- Azure Key Vault
- Access Connector

---

# Estructura del Proyecto

```bash
analytics-medallion-stack/
│
├── notebooks/
│   ├── bronze_ingest.ipynb
│   ├── silver_transform.ipynb
│   ├── gold_agg.ipynb
│   └── orchestrator.ipynb
│
├── diagrams/
│   └── medallion_architecture.jpeg
│
├── powerbi/
│   └── proyecto-3.pbix
│
├── doc/
│   ├── Proyecto 3 - Frameworks y herramientas para big data.pdf
│   ├── Rubrica Proyecto 3 - Frameworks y herramientas para big data.xlsx
│   └── Despleiegue Lakehouse con Databricks en Azure.pdf
│
└── README.md
