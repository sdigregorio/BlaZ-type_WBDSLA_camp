## Proyecto final del WBDS LA Camp - BlaZ type

**Autora:** Sabrina Di Gregorio

## Introducción:
La cefazolina es el antibiótico recomendado en pacientes con endocarditis y bacteriemias por *Staphylococcus aureus* meticilino sensible (SAMS)([Li 2017](https://pubmed.ncbi.nlm.nih.gov/28035690/)).

Sin embargo, existen cepas de SAMS que son mas resistentes a la cefazolina debido al CzIE("Cefazolin Inoculum Effect").

Aunque el mecanismo de CzIE aún no está bien caracterizado, se piensa que está mediado por la expresión de la β-lactamasa estafilocócica BlaZ, y se ha asociado a variantes específicas de esta enzima.

Los tipos de la betalactamasa BlaZ se definen por los aminoácidos presentes en las posiciones 128 y 216 de la enzima (cerca del sitio activo), ([Voladri 1996](https://journals.asm.org/doi/epdf/10.1128/jb.178.24.7248-7253.1996), [Voladri 1998](https://journals.asm.org/doi/10.1128/AAC.42.12.3163)). 

Hay descriptos 6 tipos de BlaZ (A, B, C, D, E, F) ([Harrison 2019](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7611363/pdf/EMS83234.pdf)).


## Objetivos del proyecto
El siguiente proyecto tiene como objetivo conocer el tipo de BlaZ de *S. aureus* depositadas en NCBI con el fin de:

A- Ver si hay depositadas en la base de datos alguna proteína con potencial nuevo tipo de BlaZ.

B- Armar una base de datos de secuencias de esta proteína para posteriormente estudiar su filogenia.


## Instalación
Para realizar el siguiente proyecto hacen falta:
* Python
* Pandas
* Biopython
* SeqIO
* Entrez
* yaml
* MAFFT version 7
* Aliview 1.28
* IQ-TREE version 1.6.12


## Resumen
En este proyecto se emplean diversos programas y bibliotecas que permiten:

**1.**   Buscar las secuencias de BlaZ de la especie *S. aureus* en la base de datos de proteínas de NCBI (Refseq).(Bio Entrez).

**2.**   Descargar dichas secuencias como archivo multi .fasta (Bio SeqIO) y alinearlas junto con secuencias de referencia de BlaZ pertenecientes a distintos tipos (MAFFT).

**3.**   Determinar el tipo y la frecuencia de cada secuencia de BlaZ utilizando técnicas de análisis y visualización de datos (Pandas, Biopython).

**4.**   Encontrar secuencias de BlaZ no tipables que podrían corresponder con nuevas variantes de la enzima (Pandas).

**5.**   Analizar y visualizar las relaciones filogenéticas entre los distintos tipos de BlaZ encontrados (IQTree, Figtree).


## Corrida
El procedimiento detallado se explicita en el archivo [proyecto_final.ipynb](https://colab.research.google.com/drive/1z0T8mDiaLUC9bqtDg36E5NZjKKLMgYT1?usp=sharing).

**1**: Preparar el entorno 

**2**: Editar el archivo config.yaml proporcionado agregando la dirección de correo electrónico de quien realiza la búsqueda en NCBI. Luego de subir este archivo al colabnotebook, correr la sección 2 del notebook para buscar las secuencias con Entrez.

**3**: Luego de obtener las secuencias en formato multifasta (BlaZ_sequences.fasta), bajarlas a su computadora personal. Con un editor de texto, agregar al archivo multifasta la secuencia de BlaZ_typeA.fasta, y correr MAFFT con este nuevo archivo (puede usarse el servidor https://mafft.cbrc.jp/alignment/server/). Con Aliview visualizar y editar el alineamiento obtenido (quitar la secuencia de referencia).

**4**: Subir el alineamiento al entorno de colabnotebook, y leerlo para pasarlo a formato lista que contenga todas las secuencias.

**5**: Correr el código (usa Pandas y Biopython) para generar un dataframe a partir del cual se pueda determinar el tipo de BlaZ.

**6**: Analizar la frecuencia de cada tipo de BlaZ en el set de datos (Pandas).

**7**: Guardar el dataframe en formato tabular (Pandas), y descargarlo a su computadora personal. Este servirá para anotar la filogenia con el resultado de BlaZ type para cada taxon.

**8**: Proceder a realizar el alineamiento con MAFFT. Para ello, con un editor de texto agregar a BlaZ_sequences.fasta las secuencias de referencia presentes en BlaZ_references.fasta.  De ser necesario editar el alineamiento con Aliview.

**9**: Correr IQTree para obtener el árbol filogenético (puede usarse el servidor: http://iqtree.cibiv.univie.ac.at/). Utilizar anotacion_BlaZ_type.txt generado a partir del dataframe para anotar la filogenia en Figtree.


## Perspectivas futuras

El proyecto planteado permitió conseguir los objetivos. Ver conclusiones detalladas en el archivo proyecto_final.ipynb.
Se planea a futuro automatizar el agregado/edición de secuencias de referencia al archivo multifasta.



