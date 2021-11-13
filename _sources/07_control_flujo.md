#  Control de flujo de un algoritmo
**Autora: M. Nayeli Luis-Vargas**
<!--Falta varias cosas de control de flujo--->

:::{admonition} Objetivo
:class: tip
* Entender que todos los algoritmos tienen un control de flujo.
* Comprender los tipos de control de flujo que existen y las estructuras de control de cada tipo.
:::

## Secuencial

Control de flujo se refiere a la forma en la que nuestra computadora va a ir leyendo y ejecutando las instrucciones que le damos. El control de flujo *secuencial* es el más básico, implica que no se debe tomar alguna decisión. Simplemente las instrucciones se van ejecutando una tras otra hasta que el algoritmo llega a su fin.

<br>

Por ejemplo:

<br>

```{code-block} none
Algoritmo hola_nombre
  Definir nombre como Caracter
	Escribir "Escribe tu nombre:"
	Leer nombre
	Escribir "Hola " nombre
FinAlgoritmo
```

<br>

::::{margin}
:::{admonition} Consejo
:class: hint
Puedes copiar y pegar el código de los algoritmos de éste capítulo en <a href= "http://pseint.sourceforge.net/">PSeInt</a>, para poder ver con mejor detalle cómo funciona cada uno.
:::
::::

En el algoritmo anterior, la computadora no tuvo que que tomar alguna decisión o considerar algo para poder ejecutar el programa. Ejecutó una instrucción tras otra hasta que se terminaron las instrucciones, esto puede verse con claridad en el diagrama de flujo:

```{figure} images/intro_programacion/secuencial.png
---
height: 350px
name: secuencial
---
Diagrama de flujo de un algortimo secuencial.
```
<br>

## Selectivo

Sin embargo, existen programas en donde si se tiene que hacer una evaluación antes de ejecutar alguna instrucción, a este tipo de control de flujo se le llama *selectivo*. Aquí el proceso deja de ser lineal, y se tornoa en un proceso de toma de decisiones, y para que el programa pueda tomar decisiones entonces utilizamos **estructuras de control de flujo**.

<br>

### If-Else (Si-Sino)
En el algoritmo del capítulo anterior utilizamos ésta estructura de control, en donde el programa tuvo que tomar una decisión. ¿Qué decidió? Si el número que ingresamos era mayor a 1 o no lo era,  y en función de eso imprimió cierta instrucción.

<br>

```{code-block} none
Algoritmo numero_mayor_uno
  Definir x como Entero
	Escribir 'Escribe un número:'
	Leer x
	Si x>1 Entonces
		Escribir 'El número es mayor a 1.'
	SiNo
		Escribir 'El número es menor a 1.'
	FinSi
FinAlgoritmo
```
<br>

En un diagrama de flujo de un algoritmo selectivo podemos ver una bifurcación, en donde el programa tiene que contestar a una pregunta, en éste caso ¿x es mayor a 1?. En función de esa pregunta va a tomar una decisión y a ejecutar una u otra instrucción (ver {ref}`selectivo_simple`).

<br>

```{figure} images/intro_programacion/selectivo_simple.png
---
height: 350px
name: selectivo_simple
---
Diagrama de flujo de un algoritmo selectivo tipo if-else simple.
```

<br>

De manera que el esqueleto general de la estructura if-else es:

<br>

```{code-block} none
Si (condicion) Entonces
  instruccion 1
  instruccion 2
SiNo
  instruccion 1
FinSi
```
<br>

Algunas veces, es posible que no se requiera que se ejecuten instrucciones cuando la condición sea falsa , así que podemos prescindir de esa zona:

<br>

```{code-block} none
Si (condicion) Entonces
  instruccion 1
  instruccion 2
FinSi
```

### If-Else anidado
La estructura de decisión if-else se puede usar cuantas veces sean necesarias en un algoritmo, incluso dentro de otra estructura de decisión.

<br>
Por ejemplo: Escribiremos un algoritmo que va a determinar un mensaje según la calificación obtenida.

<br>

::::{margin}
:::{admonition} Tip
:class: tip
Si te cuesta trabajo leer algún algoritmo, trata de hacer el diagrama de flujo.
:::
::::

```{code-block} none
Algoritmo calificacion
	Definir cali Como Real
	Escribir "Ingrese su calificación final:"
	Leer cali
	Imprimir "Su nota es: " cali
	Si cali < 5 Entonces
		Imprimir "Su nota es insuficiente."
	SiNo
		Si cali == 6 Entonces
			Imprimir "Su nota es suficiente."
		SiNo
			Si cali > 7 Entonces
				Imprimir "Su nota es sobresaliente."
			FinSi
		FinSi
	FinSi
FinAlgoritmo
```

<br>

En este caso, el algoritmo se tiene que hacer varias preguntas, no solo una. Y de igual manera, en función de esas preguntas va a tomar una decisión. Para el algoritmo anterior, la pregunta uno sería: ¿La calificación es menor a 5?, en caso se ser cierto, el algoritmo tiene la instrucción de imprimir un mensaje, por el contrario, si la calificación es mayor a 5, entonces se hará otra pregunta: ¿La calificación es igual a 6?. Si ésta segunda pregunta es cierta, entonces se imprime otro mensaje pero en caso de que la respuesta sea falsa, entonces se hará una última pregunta: ¿La calificación es mayor a 9?, y si es cierto, el programa imprimirá otro mensaje. El diagrama de flujo del éste algoritmo se verá de la siguiente forma:

<br>

```{figure} images/intro_programacion/selectivo_anidado.png
---
height: 350px
name: selectivo_anidado
---
Diagrama de flujo de un algoritmo selectivo tipo if-else anidado.
```

<br>

### Switch
Ésta estructura de control de utiliza en caso de tener varias opciones, aquí el algoritmo va a escoger de entre una lista de opciones dadas, como si fuera un menú, de manera que la pregunta del algoritmo es: ¿El dato ingresado está dentro de mi menú?, si es así, entonces se lleva a cabo la instrucción dada para esa opción. Ejemplo:

<br>

```{code-block} none
Algoritmo elige_numero
	Definir num Como Entero
	Escribir "Elige un número del 1 al 4:"
	Leer num
	Segun num
		Caso 1: Imprimir "Has elegido el 1."
		Caso 2: Imprimir "Has elegido el 2."
		Caso 3: Imprimir "Has elegido el 3."
		Caso 4: Imprimir "Has elegido el 4."
	FinSegun
FinAlgoritmo
```

<br>

El diagrama de flujo para el algoritmo anterior se ve de la siguiente forma:

<br>

```{figure} images/intro_programacion/switch.png
---
height: 350px
name: switch
---
Diagrama de flujo de un algoritmo selectivo tipo switch.
```

<br>

Y por último, la estructura general de la estructura switch sería:

```{code-block} none
Segun variable
  Caso valor1: Instruccion 1
               Instruccion 2
               ...
               FinCaso
  Caso valor2: Instruccion 1
               Instruccion 2
               ...
               FinCaso
  FinSegun
```

:::{admonition} Ejercicios (opcional)
:class: hint

Desarrolla un algoritmo en pseudocódigo para un programa que determine si un número es primo.

<br>

Pista: ¿Cuál es la característica de los números primos?
:::
