# Spotify Music Clustering

<p align="center">
   <img src="https://github.com/user-attachments/assets/92b2a52d-aad9-4cc3-933e-997646f47114" alt="Géneros dominantes por clúster" width="850">
</p>

## Descripción del proyecto

Este proyecto aplica técnicas de aprendizaje de máquina no supervisado para segmentar canciones de Spotify según sus características de audio.

El objetivo principal es descubrir patrones musicales ocultos en el dataset y agrupar canciones similares mediante algoritmos de clustering. Para ello, se utilizaron variables como `danceability`, `energy`, `acousticness`, `instrumentalness`, `liveness`, `speechiness`, `valence`, `tempo`, `loudness` y `popularity`.

A diferencia de un modelo supervisado, este proyecto no busca predecir una variable objetivo. En cambio, utiliza las características de audio disponibles para encontrar grupos naturales dentro de las canciones.

---

## Objetivo

Aplicar aprendizaje no supervisado para identificar perfiles musicales dentro de un conjunto de canciones de Spotify, utilizando técnicas de clustering, reducción dimensional y visualización de datos.

---

## Dataset

El dataset utilizado corresponde a canciones de Spotify con características de audio.

Fuente del dataset:

[Spotify Tracks Dataset - Audio Features en Kaggle](https://www.kaggle.com/datasets/saichaitanyareddyai/spotify-tracks-dataset-audio-features)

El dataset contiene información como:

- Nombre de la canción
- Artista
- Género
- Popularidad
- Duración
- Bailabilidad
- Energía
- Volumen
- Acústica
- Instrumentalidad
- Presencia en vivo
- Valencia emocional
- Tempo

La variable `track_genre` no fue utilizada para entrenar el modelo. Se utilizó únicamente como apoyo para interpretar los clústeres obtenidos.

---

## Herramientas utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Técnicas aplicadas

- Análisis exploratorio de datos
- Limpieza de datos
- Selección de variables numéricas
- Escalamiento con StandardScaler
- K-Means Clustering
- Método del codo
- Silhouette Score
- PCA
- t-SNE
- Análisis de perfiles promedio por clúster
- Visualización de géneros dominantes
- Interpretación de clústeres

---

## Flujo del proyecto

1. Carga del dataset
2. Exploración inicial de los datos
3. Limpieza y revisión de valores nulos
4. Selección de variables de audio
5. Escalamiento de variables
6. Evaluación del número de clústeres
7. Entrenamiento del modelo K-Means
8. Visualización de clústeres con PCA y t-SNE
9. Interpretación de los perfiles musicales
10. Análisis de géneros y canciones más representativas por clúster
11. Conclusiones finales

---

## Visualizaciones principales

### Método del codo

<p align="center">
  <img src="https://github.com/user-attachments/assets/4422e47b-185e-4614-9c0c-7e8064e0c05a" alt="Método del codo" width="750">
</p>

El método del codo fue utilizado para observar cómo disminuye la inercia a medida que aumenta el número de clústeres. Esta visualización ayuda a seleccionar una cantidad razonable de grupos para el modelo K-Means.

---

### Visualización de clústeres con PCA

<p align="center">
  <img src="https://github.com/user-attachments/assets/5dfec910-719d-440f-942f-28878a7b8c17" alt="Clusters visualizados con PCA" width="750">
</p>

PCA permitió reducir las variables originales a dos componentes principales para representar visualmente los clústeres en un espacio bidimensional.

---

### Visualización de clústeres con t-SNE

<p align="center">
  <img src="https://github.com/user-attachments/assets/b4412f3f-7b96-4fc5-8579-1118ea48285f"" alt="Clusters visualizados con t-SNE" width="750">
</p>

t-SNE fue utilizado como técnica de reducción dimensional no lineal para explorar la separación visual de los grupos musicales.

---

### Perfil promedio por clúster

<p align="center">
  <img src="https://github.com/user-attachments/assets/b0b87ae0-6c87-42ce-b13d-5db73b2246bf" alt="Heatmap del perfil promedio por clúster" width="850">
</p>

El heatmap muestra el perfil promedio estandarizado de cada clúster. Esta visualización permitió interpretar las principales diferencias entre los grupos según sus características de audio.

---

### Géneros dominantes por clúster

<p align="center">
  <img src="https://github.com/user-attachments/assets/92b2a52d-aad9-4cc3-933e-997646f47114" alt="Géneros dominantes por clúster" width="850">
</p>

Este gráfico muestra los géneros más frecuentes dentro de cada clúster. Aunque el género no fue utilizado para entrenar el modelo, permitió validar e interpretar musicalmente los grupos encontrados.

---

### Canciones más populares por clúster

<p align="center">
  <img src="https://github.com/user-attachments/assets/fd9e70ee-4b5e-4634-85c0-5d602294f776" alt="Canciones más populares por clúster" width="850">
</p>

Esta tabla permite observar las canciones más populares dentro de cada perfil musical identificado por el modelo.

---

### Distribución de canciones por clúster

<p align="center">
  <img src="https://github.com/user-attachments/assets/57ef4334-d034-41b4-8d7c-05973d6a936e" alt="Distribución de canciones por clúster" width="750">
</p>

Esta visualización permite revisar cuántas canciones fueron asignadas a cada clúster, ayudando a evaluar la distribución de los grupos obtenidos.

---

### Radar chart por clúster

<p align="center">
  <img src="https://github.com/user-attachments/assets/6cb63478-f8b1-4838-9db2-c7e84fca5830" alt="Radar chart por clúster" width="850">
</p>


El radar chart resume las características musicales promedio de cada clúster, facilitando la comparación visual entre perfiles.

---

## Resultados obtenidos

El modelo permitió identificar cuatro perfiles musicales principales:

| Clúster | Perfil interpretado | Características principales |
|---|---|---|
| Clúster 0 | Bailable / Latino / Positivo | Alta bailabilidad, mayor valence y perfil rítmico |
| Clúster 1 | Intenso / Metal / Alta energía | Mayor energía, loudness y tempo |
| Clúster 2 | En vivo / Vocal / Spoken content | Alta presencia de liveness y speechiness |
| Clúster 3 | Acústico / Ambiental / Relajado | Alta acousticness e instrumentalness, menor energía |

---

## Interpretación general

El análisis permitió observar que las canciones pueden agruparse en perfiles musicales coherentes usando únicamente características de audio.
El clúster bailable y positivo agrupa canciones con mayor `danceability` y `valence`, mientras que el clúster intenso presenta valores elevados de `energy`, `loudness` y `tempo`.
Por otro lado, el clúster asociado a contenido en vivo o vocal destaca por valores altos de `liveness` y `speechiness`. Finalmente, el clúster acústico y ambiental presenta mayor `acousticness` e `instrumentalness`, junto con menor energía y menor volumen.
Estos resultados muestran que el aprendizaje no supervisado puede ser útil para explorar catálogos musicales, detectar patrones de audio y construir segmentaciones interpretables.

---

## Aplicaciones posibles

Este tipo de análisis podría utilizarse en:

- Sistemas de recomendación musical
- Creación automática de playlists
- Segmentación de catálogos musicales
- Análisis de géneros y estilos musicales
- Exploración de patrones de consumo musical
- Organización de bibliotecas musicales extensas

---

## Estructura del repositorio

```text
spotify-music-clustering/
│
├── data/
│   └── spotify_tracks_dataset_detailed.csv
│
├── images/
│   ├── generosdominantes_porcluster.png
│   ├── Heatmap_perfilpor_cluster.png
│   ├── radar_chart_cluster.png
│   ├── pca_clusters.png
│   ├── tsne_clusters.png
│   ├── top_tracks_by_cluster.png
│
├── notebook/
│   └── spotify_music_clustering.ipynb
│
└── requirements.txt
