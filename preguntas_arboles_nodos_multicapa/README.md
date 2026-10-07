# Actividad — Árboles de decisión y redes neuronales multicapa

## Parte I. Conceptos y definiciones

### Pregunta 1

**¿Qué es un árbol de decisión y cuál es su objetivo principal dentro de un problema de clasificación?**

Un árbol de decisión es un modelo de aprendizaje automático que toma decisiones a partir de una serie de condiciones aplicadas a los datos. Su estructura se parece a un árbol, donde cada decisión permite avanzar por diferentes caminos hasta llegar a un resultado final.

Dentro de un problema de clasificación, su objetivo principal es analizar las características de los datos y asignarlos a una categoría o clase determinada. Para hacerlo, divide los datos utilizando diferentes condiciones hasta encontrar una clasificación adecuada.

### Pregunta 2

**¿Cuáles son los siguientes elementos de un árbol de decisión?**

* **Nodo raíz:** Es el primer nodo del árbol y representa el punto donde comienza el proceso de decisión. Contiene la primera condición que se utiliza para dividir los datos.

* **Nodo interno:** Es un punto intermedio del árbol en el que se evalúa alguna característica de los datos. Dependiendo del resultado de esa evaluación, se continúa por una rama diferente.

* **Rama:** Representa uno de los posibles caminos que se pueden seguir después de evaluar una condición en un nodo. Cada rama corresponde a un posible resultado de dicha condición.

* **Hoja:** Es el último punto de un camino dentro del árbol. Ya no realiza más divisiones y contiene la clasificación o resultado final que el modelo asigna al dato.

### Pregunta 3

**¿Qué es una red neuronal multicapa y qué función cumplen las siguientes capas?**

Una red neuronal multicapa es un modelo de aprendizaje automático formado por varias capas de neuronas artificiales conectadas entre sí. 

* **Capa de entrada:** Es la capa que recibe los datos que serán procesados por la red neuronal. 

* **Capa oculta:** Es la encargada de procesar y transformar la información recibida. puede haber una o varias capas ocultas.

* **Capa de salida:** Es la última capa de la red neuronal y genera el resultado final.

### Pregunta 4

**¿Qué representan los pesos y los sesgos dentro de una red neuronal?**

Los pesos representan la importancia que tiene cada conexión entre las neuronas. Un peso mayor puede hacer que cierta información tenga más influencia en el resultado, mientras que un peso menor reduce dicha influencia.

Los sesgos son valores adicionales que se agregan a los cálculos de las neuronas para dar mayor flexibilidad al modelo. Permiten que una neurona pueda producir diferentes resultados incluso cuando los valores de entrada son pequeños o iguales a cero.


### Pregunta 5

**¿Cuál es la principal diferencia entre la forma en que aprende un árbol de decisión y la forma en que aprende una red neuronal multicapa?**

La principal diferencia se encuentra en la manera en que cada modelo obtiene conocimiento a partir de los datos.

Un árbol de decisión aprende buscando las características y condiciones que permiten separar mejor los datos. Durante el entrenamiento determina qué variables utilizar, qué condiciones aplicar y en qué orden realizar las divisiones. Como resultado, aprende una estructura formada por nodos, ramas y hojas.

Una red neuronal multicapa, aprende modificando los pesos y los sesgos de las conexiones entre sus neuronas. Los datos pasan por sus diferentes capas y, cuando la predicción obtenida es incorrecta, la red ajusta estos valores para disminuir el error.

## Parte II. Análisis y aplicación

### Pregunta 6

Una institución bancaria desea desarrollar un sistema que detecte posibles compras fraudulentas.

El sistema dispone de información como:

* Monto de la compra.
* Hora de la operación.
* Ciudad donde se realizó.
* Tipo de establecimiento.
* Número de compras realizadas durante el día.
* Historial de compras del cliente.

**Analice las ventajas y desventajas de utilizar un árbol de decisión y una red neuronal multicapa.**

* Red neuronal: 
* Árbol de desición: 

**¿Cuál utilizaría y por qué?**

### Pregunta 7

Una escuela quiere detectar estudiantes que presentan riesgo de reprobar una materia.

Se conocen variables como:

* Asistencia.
* Calificaciones.
* Tareas entregadas.
* Participación.
* Número de materias reprobadas anteriormente.
* Suponga que un árbol de decisión y una red neuronal obtienen prácticamente la misma precisión.

**¿Qué otros factores tomaría en cuenta para elegir uno de los dos modelos?**

Justifique su respuesta.

### Pregunta 8

Un hospital desarrolla un sistema para determinar qué pacientes necesitan atención prioritaria utilizando:

* Edad.
* Temperatura.
* Presión arterial.
* Frecuencia cardiaca.
* Síntomas.
* Antecedentes médicos.

Una red neuronal obtiene mejores resultados que un árbol de decisión, pero resulta más difícil explicar cómo obtuvo su respuesta.

**¿Considera que la mayor precisión es suficiente para elegir la red neuronal?**

Analice las consecuencias que podría tener esta decisión.

### Pregunta 9

Una empresa de reparto quiere predecir si un pedido llegará tarde considerando:

* Distancia.
* Tráfico.
* Clima.
* Hora del día.
* Cantidad de pedidos.
* Experiencia del repartidor.

Para determinado pedido, el árbol de decisión indica:

```
Llegará a tiempo
```

mientras que la red neuronal indica:

```
Probablemente llegará tarde
```

**¿Cómo determinaría cuál de los dos modelos está realizando una mejor predicción?**

Explique qué información adicional debería analizar.