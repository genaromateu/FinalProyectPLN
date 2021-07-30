# Modelo para detectar depresión en usuarios en base a comentarios en redes sociales
## Introducción
Este repositorio incluye bases de datos etiquetadas con positivo y negativo de más de 102 mil datos. Los datos fueron obtenidos utilizando bases de datos ya preexistentes que se encuentran disponibles en internet (para más información checar Paginas Consultadas). Tambien se utilizo un webscrapping, se realizó para complementar la información y mantener un balance en los datos sin tener la necesidad de recurrir a recursos como la utilización de datos sintéticos. No se logró utilizar el 100% de los datos recolectados por problemas con Google Colab y espacios de memoria, por lo que tuvimos que reducir la muestra a 20 mil datos. Se llego a esta cifra tras varios experimentos con diferentes cantidades, con 20 mil datos se logro el mejor desempeño sin tener tiempos muy largos de espera al correr el código.

Los modelos usados dentro del programa nos ayudan detectar la depresión de los comentarios obtenidos de diferentes plataformas como Twitter y Reddit.

## Requirement:

**Se debe de correr el código en Google Colab para asegurar su correcto funcionamiento.**

Librerias utilizadas:
- pandas
- google
- nltk
- re
- sklearn
- keras

Librerias instaladas en Google Colab:
- transformers
- emoji

Para mas informacion consultar el archivo requirements.txt

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

          Normal       0.95      0.95      0.95      1225
       Depressed       0.95      0.95      0.95      1275

        accuracy                           0.95      2500
       macro avg       0.95      0.95      0.95      2500
    weighted avg       0.95      0.95      0.95      2500

                      Pred. Normal	  Pred. Depressed
    True Normal       1164	          61
    True Depressed	  65              1210
    
    
![image](https://user-images.githubusercontent.com/22597422/127587702-18dc116d-d16a-4727-b956-c3c7ac7740fe.png)


### DistilBERT

                  precision    recall  f1-score   support

          Normal       0.97      0.97      0.97      1225
       Depressed       0.97      0.97      0.97      1275

        accuracy                           0.97      2500
       macro avg       0.97      0.97      0.97      2500
    weighted avg       0.97      0.97      0.97      2500
    
    
                      Pred. Normal	  Pred. Depressed
    True Normal       1192	          33
    True Depressed	  37              1238



![image](https://user-images.githubusercontent.com/22597422/127587590-bbf56240-d4d8-43ea-8c01-3f5c73758f50.png)

## Paginas Consultadas:

http://amsantac.co/blog/es/2016/09/20/balanced-image-classification-r-es.html -- se utilizó la web para ver la importancia de trabajar con datos balanceados

https://github.com/JDAI-CV/CoTNet -- se utilizó para basarnos en el estilo del github

https://docs.github.com/es/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax se utilizó para conocer los formatos de sintaxis de la plataforma

se utilizó para obtener parte de la data
 - https://github.com/shaoxiongji/sw-detection/tree/master/data 
 
- https://www.kaggle.com/saurabhshahane/twitter-dataset-based-on-depressive-words?select=tweetdata.txt

