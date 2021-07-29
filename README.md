# Modelo para detectar depresión en usuarios en base a comentarios en redes sociales
## Introducción
Este repositorio incluye bases de datos etiquetadas con positivo y negativo de más de 102mil datos, estos datos fueron obtenidos por medio de otras bases de datos ya preexistentes(al final del documento se encuentra la información de donde se tomó la información) además de una complementación de estas por medio de un webscrapping, esto se realizó para terminar de complementar la información y que se tuviera un balance de la misma sin tener la necesidad de utilizar recursos como la utilización de datos sintéticos. no se logró utilizar el 100% de los datos por problemas de googlecolab y espacios de memoria por lo que tuvimos que reducir la muestra de la información a 20mil datos para tener un desempeño óptimo sin tener tiempos muy largos de espera al correr el código.

Los modelos usados dentro del programa nos ayudan detectar la depresión de los diferentes tipos de comentarios

## Uso 
## Requirement:
de forma específica se puede encontrar en el archivo requirements.txt 
pero las librerías que se utilizaron que no se encuentran en colab fueron las siguientes:

- nltk
- emoji
- re
- transformers

**se debe de correr el código en google Colab para asegurar su correcto funcionamiento**

## Clonado del repositorio
```
git clone https://github.com/genaromateu/FinalProyectPLN.git
```
## entrenamiento del modelo
## Descripción del modelo
## Resultados
























## Paginas Consultadas:

http://amsantac.co/blog/es/2016/09/20/balanced-image-classification-r-es.html -- se utilizó la web para ver la importancia de trabajar con datos balanceados

https://github.com/JDAI-CV/CoTNet -- se utilizó para basarnos en el estilo del github

