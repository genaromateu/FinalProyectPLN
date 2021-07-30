# Modelo para detectar depresión en usuarios en base a comentarios en redes sociales
## Introducción
Este repositorio incluye bases de datos etiquetadas con positivo y negativo de más de 102 mil datos. Los datos fueron obtenidos utilizando bases de datos ya preexistentes que se encuentran disponibles en internet (para más información checar Páginas Consultadas). También se utilizó un webscrapping, se realizó para complementar la información y mantener un balance en los datos sin tener la necesidad de recurrir a recursos como la utilización de datos sintéticos. No se logró utilizar el 100% de los datos recolectados por problemas con Google Colab y espacios de memoria, por lo que tuvimos que reducir la muestra a 20 mil datos. Se llegó a esta cifra tras varios experimentos con diferentes cantidades. Posteriormente, se comprobó que con 20 mil datos se obtenía el mejor desempeño sin tener tiempos muy largos de espera al correr el código.

Los modelos usados dentro del programa nos ayudan a detectar la depresión de los comentarios obtenidos de diferentes plataformas como Twitter y Reddit.

## Requirement

**Se debe de correr el código en Google Colab para asegurar su funcionamiento adecuado.**

Librerias utilizadas:
- pandas
- google
- nltk
- re
- sklearn
- keras
- numpy
- matplotlib
- tensorflow

Librerias instaladas en Google Colab:
- transformers
- emoji

Para más información consultar el archivo requirements.txt

## Uso del código

Al realizar el clone al repositorio se obtienen todos los archivos, en caso de no hacerlo, verificar que se tengan todos los archivos de los datos para su correcto funcionamiento.

Considerar los archivos:
- data_1.txt
- sample_data_1.xlsx
- sample_data_2.xlsx

**Se requiere obtener un archivo kaggle.json para algunas de las bases de datos**

Para más información consultar la documentación oficial https://www.kaggle.com/docs/api

## Clonado del repositorio
```
git clone https://github.com/genaromateu/FinalProyectPLN.git
```
## Descripción y entrenamiento de los modelos

### Modelo 1 BERT

BERT(Bidirectional Encoder Representation from Transformers) es un transformador pre-entrenado propuesto en el siguiente paper https://arxiv.org/abs/1810.04805. En este caso se utilizó la versión de BERT para la clasificación de secuencias para TensorFlow. Se utilizó la función de 'Sparce Categorical Crossentropy' para calcular la pérdida, Adam como optimizador y con un 'learning rate' variable que empieza en 5e-5 y baja linealmente hasta 1e-7. Para el entrenamiento se utilizaron 'batches' de 100 por 3 épocas.

### Modelo 2 DistilBERT

DistilBERT es un transformador derivado de BERT que es más ligero y rápido además de que conserva mucha de la precisión de BERT. Se utilizó la versión para la clasificación de secuencias para TensorFlow, con los mismos hyperparámetros que el modelo anterior.

## Resultados
*Los resultados varían cada vez que se entrena el modelo*

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

## Páginas Consultadas

http://amsantac.co/blog/es/2016/09/20/balanced-image-classification-r-es.html -- se utilizó la web para ver la importancia de trabajar con datos balanceados

https://github.com/JDAI-CV/CoTNet -- se utilizó para basarnos en el estilo del github

https://docs.github.com/es/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax -- se utilizó para conocer los formatos de sintaxis de la plataforma

**Bases de datos**:
- DepressionTweets - https://www.kaggle.com/samrats/depressiontweets
- English depression related posts from Reddit - https://www.kaggle.com/luizfmatos/reddit-english-depression-related-submissions
- Sentimental Analysis NLP - https://www.kaggle.com/ashishpatel26/sentimental-analysis-nlp?select=neg_tweets.txt
- Suicidal Ideation Detection in Online User Contents - https://github.com/shaoxiongji/sw-detection/tree/master/data

