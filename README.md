# Práctica de Clustering (Pokémon) — K-Means, DBSCAN y Aglomerativo

Repositorio con **dos notebooks** y un **informe** para un análisis de datos utilizando *clustering* a un dataset de **734 Pokémon**. Se exploran agrupamientos “naturales” usando enfoques basados en **centroides**, **densidad** y **jerarquía**, y se analiza si los clústeres se alinean con los **tipos oficiales** o con **roles/estilos funcionales** definidos por estadísticas. :contentReference[oaicite:1]{index=1}

---

## Contenido del repositorio

- `PW3_E1_GROUP[3C6].ipynb` — **Ejercicio 1**: EDA + *preprocessing* + **K-Means** (codo/WCSS y silhouette) + **DBSCAN** (k-distance, eps/min_samples) + análisis e interpretación.
- `PW3_E2_GROUP[3C6].ipynb` — **Ejercicio 2**: **Clustering jerárquico aglomerativo**, comparación de *linkages* y métricas, **dendrogramas** y análisis de casos.
- `RESEARCH_PW3_GROUP[3C6].pdf` — Memoria/informe con metodología, resultados y conclusiones.
-`pokemons-1.json` — Fichero JSON con datos

---

## Dataset y variables utilizadas

- **734 instancias** (Pokémon) y variables numéricas derivadas del JSON:
  - Stats base: `hp, atk, def, spa, spd, spe`
  - Variables auxiliares/derivadas: `n_moves, n_types, n_abilities, hasEvo`  

---

## Metodología (resumen)

### Análisis Exploratorio de Datos (EDA)
- Estudio inicial de la estructura de los datos
- Investigación de distribuciones y correlaciones de las variables númericas
- Análisis de estadísticas básicas (cuartiles, rangos, desviación, media, etc.)

### Preprocesado
- Revisión de nulos y outliers (sin imputación).
- Escalado con **StandardScaler** (media 0, desviación 1) por ser algoritmos basados en distancia. :contentReference[oaicite:3]{index=3}

### Primer Notebook — K-Means y DBSCAN
- **K-Means**
  - Selección de `k` óptimo con **método del codo (WCSS/inercia)** + **Silhouette Score**. 
- **DBSCAN**
  - Selección de `eps` guiada por **k-distance graph** y búsqueda en rejilla de `(eps, min_samples)`.
- Comparativa final entre modelos por **calidad interna** e **interpretabilidad**. :contentReference[oaicite:4]{index=4}

### Segundo Notebook — Aglomerativo/Jerarquico + dendrogramas
- Se prueban y comparan diferentes *linkages*: `single`, `complete`, `average`, `ward`.
- Se evalúan configuraciones con:
  - **Silhouette** (↑ mejor)
  - **Davies–Bouldin** (↓ mejor)
  - **Calinski–Harabasz** (↑ mejor)
- Uso de **dendrogramas** para justificar cortes y detectar efectos de outliers. :contentReference[oaicite:5]{index=5}

---

### Colaboradores

Mario Martinez Lozano
Vittorio Perillo
Jose Alejandro Viveros Rotonda
