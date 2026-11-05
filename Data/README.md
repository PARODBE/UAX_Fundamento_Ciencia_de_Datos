# Datos del proyecto

## Archivos principales

- `DILIst_FDA.csv` y `dilist_original.csv`: archivo fuente de DILIst en CSV.
- `dilist_normalizado.csv`: variables originales con la etiqueta renombrada como `DILI`.
- `dilist_con_descriptores.csv`: conjunto completo, con las estructuras identificadas, sus identificadores y descriptores RDKit; conserva también los registros sin estructura resuelta.
- `dilist_descriptores.csv`: compuestos con InChIKey única, sin etiquetas contradictorias y con una fila por estructura.
- `dilist_train.csv` y `dilist_test.csv`: partición reproducible 80/20 (semilla 42), estratificada por cuantiles de MolLogP y clase DILI.
- `dilist_sin_estructura.csv`: registros para los que no se encontró una estructura inequívoca.
- `dilist_conflictos.csv`: compuestos con etiquetas DILI distintas para una misma InChIKey. En la preparación actual no se encontraron casos.

## Cálculo y trazabilidad

Las estructuras se asociaron por nombre normalizado. Se usaron coincidencias de nombre preferido en ChEMBL y, para los nombres restantes, búsquedas en PubChem; se conservaron solo resultados únicos por InChIKey. Los archivos `chembl_prefname_structures.csv` y `pubchem_fallback_lookup.csv` documentan esas consultas. No se asignó estructura cuando la búsqueda fue ambigua o no encontró coincidencia.

Los descriptores se calcularon con RDKit a partir de SMILES: MolWt, MolLogP, donantes y aceptores de enlaces de hidrógeno, TPSA, enlaces rotables, anillos, átomos pesados y FractionCSP3. `LipinskiViolations` cuenta incumplimientos de los cuatro límites habituales (peso molecular >/= 500, LogP > 5, HBD > 5 y HBA > 10).

La fuente contiene 1.279 registros. Se obtuvieron estructuras para 1.186 registros y, tras retirar estructuras repetidas por InChIKey, quedaron 1.182 compuestos para el análisis y la partición. Los registros sin una estructura inequívoca se mantienen en el archivo completo y en el archivo de auditoría, pero no entran en los análisis que requieren descriptores.
