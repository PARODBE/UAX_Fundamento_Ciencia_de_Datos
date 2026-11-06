# Datos del proyecto

## Archivos CSV

- `DILIst_FDA.csv`: fuente de la FDA, con 1.279 registros y cuatro columnas.
- `estructuras_nombres.csv`: compuestos de DILIst para los que PubChem devolvió una estructura; incluye nombre, InChIKey y SMILES. En esta ejecución contiene 1.184 estructuras únicas.
- `dilist_descriptores.csv`: compuestos con estructura asociada y descriptores calculados con RDKit.
- `dilist_train.csv` y `dilist_test.csv`: particiones de entrenamiento y prueba, con 947 y 237 compuestos, respectivamente.

## Cómo se prepararon

La fase 2 lee el CSV de DILIst y consulta PubChem con PubChemPy usando el nombre del compuesto. Cuando PubChem devuelve resultados, se conserva el primero que tiene estructura disponible; después se eliminan duplicados por InChIKey. El CSV de estructuras contiene solo las coincidencias obtenidas. En esta ejecución quedaron 95 registros de DILIst sin estructura asociada. No se consulta ChEMBL.

RDKit calcula 217 descriptores moleculares escalares. También se incluye `LipinskiViolations`, una variable derivada del número de criterios de Lipinski incumplidos. No se calculan fingerprints.

La partición train-test se realiza antes de los análisis posteriores, en proporción 80/20 y con estratificación por cuantiles de MolLogP y, cuando el tamaño de los grupos lo permite, por clase DILI. La etiqueta 1 corresponde a DILI positiva y 0 a DILI negativa. Las fases 3 a 6 leen estos CSV desde GitHub; no es necesario cargar los archivos manualmente en Colab.

Los límites para identificar valores extremos se calculan con train y se aplican también a test. Las transformaciones de los modelos se ajustan con train y se aplican después a ambas particiones.