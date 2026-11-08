# Cuando la química compromete la cura

Proyecto de análisis de datos sobre lesión hepática inducida por fármacos (DILI), a partir de DILIst, estructuras químicas recuperadas de PubChem y descriptores calculados con RDKit.

## Estructura del informe

3. **Comprensión de los datos y análisis exploratorio:** evaluación de la fuente, resumen univariante, comparaciones bivariantes, correlaciones, calidad de los datos y valores extremos.  
4. **Análisis de conglomerados:** PCA y K-means para describir perfiles fisicoquímicos; DILI se utiliza después para describir la composición de los grupos.  
5. **Regresión lineal:** modelado de MolLogP.  
6. **Regresión logística:** clasificación DILI.  
7. **Discusión.**  
8. **Conclusiones.**

## Notebooks

Los notebooks mantienen la numeración de fases de la asignatura, que no coincide con todos los capítulos del informe. Por ejemplo, el análisis de conglomerados corresponde a la Fase 6 del curso y al capítulo 4 del informe. [Índice y accesos a Google Colab](Notebooks/README.md).

## Datos

Los CSV originales y preparados están en [Data](Data/README.md). Los notebooks de las fases 3 a 6 descargan esos archivos desde este repositorio para que puedan ejecutarse en Google Colab sin cargar los datos manualmente.

Repositorio: https://github.com/PARODBE/UAX_Fundamento_Ciencia_de_Datos
