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

Los notebooks de organización y análisis exploratorio mantienen los nombres Fase 2 y Fase 3. Los cuadernos de conglomerados y regresión se numeran como capítulos 4, 5 y 6 para seguir el orden del informe. [Índice y accesos a Google Colab](Notebooks/README.md).

## Datos

Los CSV originales y preparados están en [Data](Data/README.md). Los notebooks de análisis descargan esos archivos desde este repositorio para que puedan ejecutarse en Google Colab sin cargar los datos manualmente.

Repositorio: https://github.com/PARODBE/UAX_Fundamento_Ciencia_de_Datos
