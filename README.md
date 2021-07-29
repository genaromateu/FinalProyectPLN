# Modelo para detectar depresión en usuarios en base a comentarios en redes sociales
## Introducción
Este repositorio incluye bases de datos etiquetadas con positivo y negativo de más de 102mil datos, estos datos fueron obtenidos por medio de otras bases de datos ya preexistentes(al final del documento se encuentra la información de donde se tomó la información) además de una complementación de estas por medio de un webscrapping, esto se realizó para terminar de complementar la información y que se tuviera un balance de la misma sin tener la necesidad de utilizar recursos como la utilización de datos sintéticos. no se logró utilizar el 100% de los datos por problemas de googlecolab y espacios de memoria por lo que tuvimos que reducir la muestra de la información a 20mil datos para tener un desempeño óptimo sin tener tiempos muy largos de espera al correr el código.

Los modelos usados dentro del programa nos ayudan detectar la depresión de los diferentes tipos de comentarios

## Uso 
## Requirement:

**se debe de correr el código en google Colab para asegurar su correcto funcionamiento**

de forma específica se puede encontrar en el archivo requirements.txt 
pero las librerías que se utilizaron que no se encuentran en colab fueron las siguientes:

- nltk
- emoji
- re
- transformers



## Clonado del repositorio
```
git clone https://github.com/genaromateu/FinalProyectPLN.git
```
## Descripción y entrenamiento de los modelos

### Modelo 1 BERT

BERT(Bidirectional Encoder Representation from Transformers) es un transformador pre-entrenado propuesto en el siguiente paper https://arxiv.org/abs/1810.04805. En este caso se utilizo la versión de BERT para la clasificación de secuencias para TensorFlow. Se utilizo la función de 'Sparce Categorical Crossentropy' para calcular la perdida y Adam como optimizador, con un 'learning rate' variable que empieza en 5e-5 y baja linealmente hasta 1e-7. Para el entrenamiento se utilizaron 'batches' de 100 por 3 épocas.

### Modelo 2 DistilBERT

DistilBERT es un transformador derivado de BERT que es más ligero y rápido ademas de que conserva mucha de la precisión de BERT. Se utilizo la versión para la clasificación de secuencias para TensorFlow, con los mismos hyperparametros que el modelo anterior.

## Resultados

### BERT

                  precision    recall  f1-score   support

               0       0.95      0.95      0.95      1225
               1       0.95      0.95      0.95      1275

        accuracy                           0.95      2500
       macro avg       0.95      0.95      0.95      2500
    weighted avg       0.95      0.95      0.95      2500

                      Pred. Normal	  Pred. Depressed
    True Normal       1164	          61
    True Depressed	  65              1210

### DistilBERT

                  precision    recall  f1-score   support

               0       0.97      0.97      0.97      1225
               1       0.97      0.97      0.97      1275

        accuracy                           0.97      2500
       macro avg       0.97      0.97      0.97      2500
    weighted avg       0.97      0.97      0.97      2500
    
    
                      Pred. Normal	  Pred. Depressed
    True Normal       1192	          33
    True Depressed	  37              1238





















## Paginas Consultadas:

http://amsantac.co/blog/es/2016/09/20/balanced-image-classification-r-es.html -- se utilizó la web para ver la importancia de trabajar con datos balanceados

https://github.com/JDAI-CV/CoTNet -- se utilizó para basarnos en el estilo del github

https://docs.github.com/es/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax se utilizó para conocer los formatos de sintaxis de la plataforma

