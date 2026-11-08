# Notebooks del proyecto

Los notebooks se presentan en el orden de trabajo del informe. La numeración de las fases 4–6 se ha dispuesto para que coincida con sus capítulos: primero conglomerados, después regresión lineal y, por último, regresión logística. Cada cuaderno puede abrirse en Google Colab desde su enlace.

1. **Fase 2: Organización y preparación de datos**  
   [![Abrir Fase 2 en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PARODBE/UAX_Fundamento_Ciencia_de_Datos/blob/main/Notebooks/Fase_2_Organizacion_Datos.ipynb)  
   Lee DILIst y el mapa de estructuras, calcula descriptores RDKit y genera los CSV utilizados en el análisis.
2. **Fase 3: Análisis exploratorio**  
   [![Abrir Fase 3 en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PARODBE/UAX_Fundamento_Ciencia_de_Datos/blob/main/Notebooks/Fase_3_Analisis_Exploratorio.ipynb)  
   Resume propiedades moleculares, compara clases DILI, examina correlaciones y documenta calidad de datos y valores extremos.
3. **Fase 4: Análisis de conglomerados**  
   [![Abrir Fase 4 en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PARODBE/UAX_Fundamento_Ciencia_de_Datos/blob/main/Notebooks/Fase_4_Conglomerados.ipynb)  
   Corresponde al capítulo 4 del informe. Aplica PCA y K-means a cinco propiedades fisicoquímicas y describe los perfiles y la composición DILI de los grupos.
4. **Fase 5: Regresión lineal de MolLogP**  
   [![Abrir Fase 5 en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PARODBE/UAX_Fundamento_Ciencia_de_Datos/blob/main/Notebooks/Fase_5_Regresion_Lineal_MolLogP.ipynb)  
   Corresponde al capítulo 5. Estima MolLogP mediante otros descriptores moleculares y compara el ajuste entre entrenamiento y prueba.
5. **Fase 6: Regresión logística de DILI**  
   [![Abrir Fase 6 en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PARODBE/UAX_Fundamento_Ciencia_de_Datos/blob/main/Notebooks/Fase_6_Regresion_Logistica_DILI.ipynb)  
   Corresponde al capítulo 6. Clasifica la etiqueta DILI, interpreta odds ratios y evalúa las métricas en entrenamiento y prueba.

## Correspondencia con los capítulos del informe

- **Capítulo 3:** comprensión de los datos y análisis exploratorio (Fases 2 y 3).
- **Capítulo 4:** análisis de conglomerados (Fase 4).
- **Capítulo 5:** regresión lineal de MolLogP (Fase 5).
- **Capítulo 6:** regresión logística de DILI (Fase 6).
- **Capítulo 7:** discusión y limitaciones.
- **Capítulo 8:** conclusiones.

Los notebooks de análisis descargan los CSV de [Data](../Data/README.md), así que no es necesario subir archivos manualmente a Colab.
