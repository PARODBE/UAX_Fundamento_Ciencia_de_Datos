# Datos del proyecto

## CSV utilizados

- `DILIst_FDA.csv`: fuente original de DILIst en CSV (1.279 registros).
- `estructuras_nombres.csv`: mapa único de nombres de DILIst a InChIKey y SMILES; incluye la fuente de la coincidencia y el estado de búsqueda para poder revisar nombres no resueltos.
- `dilist_descriptores.csv`: compuestos con estructura inequívoca y descriptores calculados con RDKit.
- `dilist_train.csv` y `dilist_test.csv`: particiones 80/20 con semilla 42, estratificadas por cuantiles de MolLogP y clase DILI.

La fase 2 del proyecto lee la fuente y el mapa de estructuras, calcula descriptores y vuelve a generar las tres tablas preparadas. Las fases 3 a 6 descargan las particiones desde este directorio; no hace falta subir archivos manualmente a Colab.

## Estructuras y descriptores

Las asociaciones se hicieron con coincidencias de nombre preferido en ChEMBL y búsquedas de respaldo en PubChem. Solo se conservaron coincidencias únicas por InChIKey. El mapa contiene también los nombres ambiguos o sin coincidencia para documentar la cobertura. De los 1.279 registros de DILIst, 1.186 obtuvieron estructura; al deduplicar por InChIKey quedaron 1.182 compuestos para el análisis.

RDKit calcula el catálogo de descriptores escalares disponible (217 en la versión usada para preparar estos archivos), no fingerprints. El EDA muestra cinco variables interpretables: peso molecular, LogP, donantes y aceptores de enlaces de hidrógeno, y TPSA. Para regresión lineal y logística se consideran descriptores numéricos más amplios, se excluyen variables que filtran el objetivo y se retiran predictores constantes o muy correlacionados usando solo entrenamiento. El clustering se limita a cinco propiedades fisicoquímicas interpretables.

La partición de entrenamiento y prueba se realiza por cuantiles de MolLogP y, cuando el tamaño de los estratos lo permite, también por clase DILI. La etiqueta 1 corresponde a DILI positiva y 0 a DILI negativa.
