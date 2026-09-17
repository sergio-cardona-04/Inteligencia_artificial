# Dino run: EDa conceptual:

## Contexto del Juego

* Nuestro personaje es un dinosaurio, el cual al dar click en la tecla de espacio, salta (realiza un movimiento en Y, luego desciende) y al dar click en la tecla de la flecha abajo, se agacha (su tamanio disminuye) para poder evitar ciertos objetos, partiendo del hecho de que los objetos terrestres pueden ser de dos medidas, grandes o chicos y los obstaculos del aire solo una, entoces, tenemos 3 variables a evitar.
* el dinosaurio se mueve inicialmente a una velocidad constante, dependiendo de la cantidad de terreno recorrida la velocidad aumenta, la cantidad de recorrido que tenemos es medible
* los obstáculos están "quietos", es decir, siempre vienen a la velocidad a la que se mueve el entorno.

## Escenarios analizables

### Morirá en el siguiente frame?

* variable objetivo Y: tipo, binaria (Morirá? si/no)
* Variables de entrada:
    * Frame (cada 16 ms): es la que nos permitirá hacer la comparación para saber a qué distacia del dinosaurio se encuentra el elemento colisionante
    * Distacia del elemento con respecto del dinosaurio: nos sirve para calcular 
    * posición del dinosaurio: el lugar en donde se encuentra
    * Velocidad del elemento: es la distancia que recorre en un frame.
    * Altura del elemento: por alguna razón, hay obstáculos altos en los que no necesitas agacharte ni saltar para esquivar
* Granularidad: Necesito un frame cada 16 ms, ya que lo que necesito es predecir si va a morir en el -siguiente frame-
* Tamanio mínimo razonable: una sola partida, ya que, al no tener acciones que realizar directamente con el dinosaurio, solo debemos de medir la distancia que corresponde entre el dinosaurio y el objeto
* Riesgo si el database está mla definido: Si no definimos ben la cercanía del proyectil con la velocidad, podemos asumir que para el siquiente frame no morirá, siendo de que puede hacerlo;

### Cuántos puntos alcanzará esta partida al morir? 

* variable objetivo Y: columna puntos (numerica)
* Variables de entrada:
    * frame: indice del frame
    * tiempo: tiempo desde que empezó la partida
    * score: puntuación en pantalla
    * Muerte: valor obtenido tras calcular el escenario anterior
    * Velocidad: velocidad a la que viene el dinosaurio
* Granularidad: necesito un resumen pot partida
* tamanio minnimo razonable
* Riesgo si el dataset está mal: datos erróneos, no devolver el puntaje, no parar nunca por error de la funcióno de verificar si murió.

### Qué tipo de obstáculo viene próximo? 

* variable objeto: objeto de tipo categórica (cactus chico, cactus grande, pájaro altura media, pajaro altura alta)
* variables de entrada
    * frame: Índice del frame de la partida
    * obstacle_type: el tipo de ostáculo 
    * velocidad
    * posición del dinosaurio
    * altura del objeto
* Granularidad: se necesita un frame cada 16 ms
* Tamanio mínimo razonable: 