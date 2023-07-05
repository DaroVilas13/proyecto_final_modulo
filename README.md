# proyecto_final_modulo

para mayor visualizacion del informe se recomienda abrir el archivo pdf dentro de esta git

* nombre del archivo de trabajo principal main_proyecto.ipynb

INFORME PRUEBA FINAL TRATAMIENTO DE DATOS

ALUMNO: Ing. David Alejandro Vilatuña CH.
MATERIA: Tratamiento de datos.
MAESTRIA: Ciberseguridad
FECHA: 04/07/2023

TEMA:
-	Clasificador de carnes
OBJETIVO:
-	Crear un repositorio de GIThub (publico) en el que se va a subir un jupyter notebook y un archivo README.md 
-	Obtener un clasificador de imágenes de forma que dada una nueva imagen se pueda obtener la clase correspondiente
-	Se pide obtener las matrices de confusión del modelo, la matriz de confusión del error en training y la de test.

NOMENCLATURA:
-	PANDAS: es una biblioteca ampliamente utilizada para administrar datos tabulares, manipulación de datos y análisis basados en NumPy. 
-	AMBIENTE VIRTUAL: Es una herramienta para crear entornos Python aislados
-	IPYKERNEL: Este paquete proporciona el kernel de IPython para Jupyter
-	SCIKIT-LEARN: conocido como sklearn, es una biblioteca robusta de aprendizaje automático de Python de código abierto
-	KERAS: API de redes neuronales más utilizadas para el desarrollo y las pruebas de redes neuronales
-	TENSORFLOW: librería de código libre para Machine Learning (ML)
-	OPENPYXL: biblioteca de Python para leer/escribir archivos Excel 2010 xlsx/xlsm/xltx/xltm
-	MATPLOTLI: biblioteca completa para crear visualizaciones estáticas, animadas e interactivas en Python
-	MATH: Este módulo proporciona acceso a las funciones matemáticas definidas por el estándar C
MARCO TEORICO
FUNCIONAMIENTO DE LAS REDES NEURONALES CONVOLUCIONARIAS
Estas redes, son las que se relacionan con la visión por ordenador. Estas son algoritmos utilizados para el Aprendizaje automático, para darle al ordenador la capacidad de VER. Estas CNN procesan las capas utilizando capas, que se asemejan al cortex del ojo humano, identificando características del objeto, para ello se debe poner capas ocultas especilizadas jerárquicamente organizadas.
Para esto es importante tener en cuenta que se requieren muchas imágenes para que pueda captar características de las clasificaciones que se requieran entrenar.

   Esta se puede representar como una matriz de pixeles, van de 0 a 255 y para la red neuronal se normalizar de 0 a 1

El proceso de trabajo es que la red toma como entrada pixeles de una imagen, en el caso de las que tenemos en el ejercicio tomamos unas fotos de 384 x 216= 82944 pixeles y con una capa  de color 3, total 248,832 neuronas de entrada.
Antes de alimentar la red debemos normalizar la misma, dividiendo el valor para 255, esto pone el valor en un rango de 0 a 1.
 
Luego se va a realizar las convoluciones que consiste en tomar grupos de pixeles cercanos de la imagen de entrada y operarlos matematicamenre con una pequeña matriz que se llama kernel, esta matriz recorre todas las neuronas de entrada de izquierda a derecha y de arriba abajo, con ello se genera una nueva matriz de salida.
 
El proceso no ocupa un solo kernel sino que es el conjunto de filtros.
 La imagen se va moviendo hasta obtener una nueva imagen filtrada por el kernel, estas imágenes lo que dibujan son ciertas características de la imagen original, que con ello ayuda a reconocer distintos objetos posteriormente.
 
Con todos los procesos descritos la siguiente imagen explicaría de manera la manera que trabaja.
 
La primera convolución, consiste de una entrada, un conjunto de filtros, un mapa de características un subsampling, que con una imagen de1 solo color se tiene 
 
En esta primera convolución el modelo observa características primitivas como líneas y curvas, con mas de estas capas el modelo ya conocera mas formas complejas
 
La segunda 
 
La forma de la red cnn se la indica en el siguiente grafico.

 
 
 
Es importante comentar que la sunción Softmax conecta contra la capa de salida final que tendría las neuronas correspondientes con las clases que estamos clasificando.
Las salidas del entrenamiento tendrán un formato conocido como one-hot-encoding, que pasa a ser una variación representada por números binarios.
La arquitectura básica de las cnn son:
Entrada: Serán los pixeles de la imagen. Serán alto, ancho y profundidad será 1 sólo color o 3 para Red,Green,Blue.
Capa De Convolución: procesará la salida de neuronas que están conectadas en “regiones locales” de entrada (es decir pixeles cercanos), calculando el producto escalar entre sus pesos (valor de pixel) y una pequeña región a la que están conectados en el volumen de entrada. Aquí usaremos por ejemplo 32 filtros o la cantidad que decidamos y ese será el volumen de salida.
“CAPA RELU” aplicará la función de activación en los elementos de la matriz.
POOL ó SUBSAMPLING: Hará una reducción en las dimensiones alto y ancho, pero se mantiene la profundidad.
CAPA “TRADICIONAL” red de neuronas feedforward que conectará con la última capa de subsampling y finalizará con la cantidad de neuronas que queremos clasificar.

DESARROLLO
Para este desarrollo, vamos a realizar una Convolutional Neural Network con Keras y Tensorflow, con el lenguaje de programación Python, para el reconocimiento de imágenes.
En base a las imágenes entregadas tenemos 2 una carpeta de Train y otra de Test, 
Lo que se utilizara para el desarrollo de la aplicación son: 
-	Python
-	Notebook Jupyter
-	Anaconda
-	Keras y Tensorflow
Instrucciones de instalación:
python -m virtualenv venv #preparamos el ambiente virtual
.\venv\Scripts\activate
pip install pandas # instalamos pandas
pip install ipykernel # instalamos ipykernel # 
pip install scikit-learn
pip install keras
pip install tensorflow  
pip install openpyxl
pip freeze > requirements.txt
pip install matplotli
pip install math

 
Declaramos todas las librerías a utilizar
 
 
 
 
 Se realiza la lectura de las imágenes en el disco 
 
Realizamos la lectura de las categorías de las imágenes en el disco 

 
se prepara el set de datos 
 

 
Preparamos las redes de las capas intermedias 
 
 
 
 
Entrenamos el modelo 
 
Evaluamos el modelo
 

Se genera la matriz de confusión


 

CONCLUSIONES Y RECOMENDACIONES:

-	Si bien la teoría de tratamiento de datos nos ha servido para profundizar en este tipo de lecciones, es importante reconocer que el reconocimiento de imágenes es un proceso mas complejo de manejo de información, Ya que en el se realizan muchos tipos de programación las cuales de manera personal me parece muy interesante pero es importante tener un conocimiento mucho mas acertado con el proceso, y manejo de librerías de los tratamientos de imágenes
-	Se reconoce la complejidad de la enseñanza a modelos neuronales ya que los parámetros de información deben validarse de acuerdo a la información realizada. 
-	Las personas que se dedican a este campo deben formar parte de expertos en el campo de redes con lo cual se puede complicar mucho mas los datos de seguimiento para la clasificación exacta de estas redes.
-	Se recomienda, realizar un modelo de acercamiento de las imágenes en clase ya que por mas que se trata de seguir la programación que se encuentra colgada en algunos sitios es importante siempre tener el direccionamiento de como funciona para que sirve y como se configura.
-	A medida de lo que se entendió en el proceso se puede decir que se logro trabajar el proyecto, para mi nivel de programación pues fue un reto hacer lo que se alcanzo a realizar.









