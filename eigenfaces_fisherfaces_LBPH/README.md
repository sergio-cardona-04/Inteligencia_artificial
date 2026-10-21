# Comparación de Eigenfaces, Fisherfaces y LBPH

## Propósito de los programas

Los tres programas recorren las carpetas de personas de un conjunto de imágenes, cargan cada imagen en escala de grises, asignan una etiqueta numérica a cada persona, entrenan un reconocedor facial y guardan el modelo en un archivo XML. En los tres casos, las imágenes deben estar en la ruta `/home/likcos/pruebacaras`, organizadas en subcarpetas, una por persona.

Al ejecutarlos, no se abre la cámara ni se muestra una predicción de identidad. La salida visible en la consola sirve para indicar qué personas encontró el programa y si terminó de guardar el modelo. Por eso, los mensajes finales confirman la creación del archivo, pero no indican por sí solos qué tan bien reconoce rostros cada método.

## Comparación observable

| Programa | Qué muestra en la consola | Reconocedor que entrena | Archivo que genera |
|---|---|---|---|
| `eigenfaces.py` | Imprime la lista de entradas encontradas en la ruta y, para cada subcarpeta, su etiqueta y el número de imágenes que pudo leer. | Eigenfaces | `laloEigenface.xml` |
| `fisherfaces.py` | Imprime la lista de subcarpetas. No muestra el conteo de imágenes por persona. | Fisherfaces | `laloFisherFace.xml` |
| `lbph.py` | Imprime la lista de subcarpetas. No muestra el conteo de imágenes por persona. | LBPH | `laloLBPHFace.xml` |

Los tres asignan las etiquetas siguiendo el orden alfabético de las carpetas. En `eigenfaces.py`, la lista inicial incluye cualquier entrada que exista en la ruta, aunque no sea una carpeta; después, el programa solo intenta cargar imágenes de las carpetas. Los otros dos filtran desde el principio para mostrar únicamente directorios. Esta diferencia puede notarse si el conjunto contiene archivos sueltos junto a las carpetas de personas.

La diferencia más fácil de ver al final es el nombre del archivo XML: cada script guarda un modelo distinto. También cambia la línea de creación del reconocedor: uno usa Eigenfaces, otro Fisherfaces y el tercero LBPH. El proceso general y el formato de salida son parecidos, pero los programas no imprimen tiempos, porcentajes de acierto ni comparaciones de predicciones; con la salida de consola solamente no se puede concluir cuál reconoce mejor.

## Salida de consola esperada

Los nombres y cantidades dependen de las carpetas y las imágenes disponibles. Si, por ejemplo, el conjunto contiene las carpetas `Persona_A` y `Persona_B`, la forma de la salida de `eigenfaces.py` sería similar a esta:

```text
Personas: ['Persona_A', 'Persona_B']
  Persona_A (label=0): N imágenes
  Persona_B (label=1): M imágenes
Modelo escrito: laloEigenface.xml
```

En `fisherfaces.py`, la forma sería similar a esta:

```text
Personas: ['Persona_A', 'Persona_B']
Modelo escrito: laloFisherFace.xml
```

Y en `lbph.py`:

```text
Personas: ['Persona_A', 'Persona_B']
Modelo escrito: laloLBPHFace.xml
```

`N` y `M` representan las imágenes que OpenCV logró leer dentro de cada carpeta; no son valores fijos. Los ejemplos muestran el formato de los mensajes, no resultados medidos de este repositorio.

## Condiciones para ejecutarlos

Los tres scripts esperan que exista `/home/likcos/pruebacaras` y que contenga una subcarpeta por persona con sus imágenes. También necesitan Python, NumPy y una instalación de OpenCV que incluya el módulo `cv.face`. Si falta la ruta o la dependencia, el entrenamiento no llega a guardar el XML. Los modelos se escriben en el directorio desde el que se ejecuta cada comando.

En esta revisión no fue posible ejecutar los entrenamientos: el repositorio no incluye el conjunto de rostros, la ruta configurada no existe en el entorno de revisión y tampoco está instalado `cv2`. Por esa razón, la comparación anterior describe el comportamiento que se observa directamente en los códigos y el formato de consola que producirían con datos y dependencias disponibles; no presenta conteos ni resultados de precisión inventados.
