# 🎨 Generación de paletas de colores a partir de imágenes usando Machine Learning no supervisado

**Colaboradores:** Cristian Murillo, Diego Pedreros  
**Tecnologías:** Python, OpenCV, Scikit-learn, HDBSCAN, t-SNE, PCA, Matplotlib, Seaborn

## 📌 Objetivo

Desarrollar un método automatizado, basado en técnicas de aprendizaje no supervisado, para generar una paleta coherente y estéticamente atractiva a partir de los colores predominantes en una imagen.

## 🖼️ Conjunto de datos

Se utilizaron imágenes de obras de arte obtenidas desde [WikiArt (Kaggle)](https://www.kaggle.com/datasets/steubk/wikiart). Estas obras presentan una gran diversidad de estilos artísticos, lo cual enriquece la extracción de paletas.

## ⚙️ Técnicas y herramientas utilizadas

- **Clustering:** K-Means, Mean-Shift, Agglomerative Clustering, HDBSCAN
- **Preprocesamiento de imágenes:** OpenCV, Pillow
- **Visualización de alta dimensión:** PCA, t-SNE
- **Evaluación de modelos:** Silhouette Score, Davies-Bouldin Index
- **Visualización:** Matplotlib, Seaborn

## 🧪 Pipeline del proyecto

1. **Carga y preprocesamiento de imágenes**
   - Redimensionamiento a 128x128 px
   - Conversión de BGR a RGB
   - Estandarización de los datos
2. **Modelado**
   - Pruebas con varios algoritmos de clustering
   - Determinación del número óptimo de clústeres con el método del coeficiente de silueta
3. **Extracción de paleta**
   - Obtención de los centroides o modos de los clústeres
   - Representación visual en franjas de color
4. **Visualización de distribución**
   - Reducción de dimensiones con PCA/t-SNE para representar la separación entre clústeres

## 🖌️ Visualización de paletas

Se generó una imagen de 50x300 px con franjas proporcionales a cada color dominante, simulando una paleta. La representación en 2D mediante PCA o t-SNE permite observar cómo se distribuyen los colores en el espacio de características.

## 📊 Evaluación comparativa

| Algoritmo             | Silhouette Score | Davies-Bouldin | Observaciones                                |
|-----------------------|------------------|----------------|----------------------------------------------|
| **K-Means**           | Alto (~0.5-0.75) | Bajo           | Buen balance entre rendimiento y eficiencia  |
| **Mean-Shift**        | Similar a KMeans | Similar        | Mayor costo computacional                    |
| **HDBSCAN**           | Bajo/Negativo    | Alto           | No logra separar bien los colores            |
| **Jerárquico**        | Moderado         | Moderado       | Muy costoso computacionalmente               |

## ✅ Conclusiones

- **K-Means** y **Mean-Shift** fueron los métodos más efectivos para la tarea.
- **K-Means** se destaca como la opción más eficiente al escalar a conjuntos de imágenes más grandes.
- **HDBSCAN** no resultó adecuado para este tipo de problema por su enfoque basado en densidad.
- La visualización en 2D permite interpretar la separación entre grupos de colores, lo cual ayuda a validar los resultados obtenidos.

## 📁 Estructura del código

- `load_and_preprocess_images()`: Carga y transforma las imágenes
- `create_color_palette()`: Genera la visualización horizontal de la paleta
- `silhouette_method()`: Determina el número óptimo de clústeres
- `analyze_image_colors_with_kmeans()`: Pipeline de análisis y visualización con KMeans
