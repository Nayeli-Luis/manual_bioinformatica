# Algoritmos
**Autora: M. Nayeli Luis-Vargas**

:::{admonition} Objetivo
:class: tip
* Enteder la importancia del diseño de algoritmos para la resolución de un problema.
:::

*Un algorotmo es un conjunto de acciones o pasos finitos, ordenados de forma lógica y que se utilizan para resolver un problema o para obtener un resultado.* Si te detienes a pensarlo por un momemto, podrás darte cuenta que nuestra vida cotidiana está dirigida por algortimos. Hasta pedir una pizza es un algoritmo, el dogma central de la biología molecular es un algortimo. Los algortimos tienen que cumplir tres características:

<br>

1. Ordenado: El orden en la ejecución de sus pasos debe ser riguroso, algunos tendrán que ser ejecutados antes que otros, de manera lógica. Por ejemplo, no puedes pedir la pizza sin antes haber llamado o haber abierto la app de comida a domicilio. No puede haber traducción sin antes haber transcripción.

2. Definido: si el algoritmo se ejecuta en repetidas ocasiones, usando los mismos datos, debe producir siempre el mismo resultado.

3. Finito: todo algoritmo posee un inicio, de igual forma debe tener un final, la ejecución de sus instrucciones debe terminar una vez procese los adtos y entregue resultados.

<br>

Los algoritmos deben ser representados de alguna forma para que puedan ser más entendibles para nosotros como humanos. Debe usarse una notación simple y lo suficientemente clara para que no haya ambiguedades. Estas notaciones son muy útiles para entender la lógica de lo que estamos haciendo y poder luego traducirlas a cualquier lenguaje de programación.

<br>

En programacion se diseñan algoritmos paara resolver algun problena con ayuda de una computadora. Prácticamente, le damos instrucciones a la computadora para que ella haga el trabajo pesado por nosotros. Sin embargo, nuestra comunicación debe ser clara de otra forma la computadora no llevará a cabo la tarea simplemente porque no comprendió las instrucciones que le hemos dado.

<br>

 Dentro de las formas más utilizadas para representar algortimos se encuentran las siguientes.

* Descripción narrada
* Diagramas de flujo
* Pseudocódigo

## Descripción narrada

Los pasos o instrucciones se describen mediante un lenguaje natural, usando palabras, frases normales, frases comunes y corrientes.

<br>

Ejemplo: Vamos a escribir un algoritmo para saber si un número es mayor a 1.  Recuerda que tienes que escribir instrucciones para que alguién más las ejecute, no son para ti. De manera, que cada vez que escribas un algoritmo debe ser de la forma más detallada posible.

<br>

1. Inicio de algoritmo
2. Escribe un número.
3. Lee le número.
2. Si el número que lees es mayor a 1, entonces escribe "Es mayor a uno".
3. Si el número es menor a uno, entonces escribe, "Es menor a uno."
4. Fin de algoritmo

Un algoritmo se puede hacer tan complejo como sea necesario, en este caso, con estos pasos es suficiente.

<br>

## Diagrama de flujo
Es la representación gráfica de un algoritmo. Lo conforma un conjunto de componentes que permiten representar acciones, decisiones o cálculos con los cuales se soluciona un problema determinado. Cuando el diagrama de flujo está bien diseñado, la concepción de un programa en un leguaje de programación, es fácilmente codificable. Por conseso, los componentes gráficos utilizados son los mismos en todos los algoritmos, y puedes consultarlos <a href = "https://drive.google.com/file/d/1_v94a7uGLWT7cY_9N3Uf3tu3kZRm1B2u/view?usp=sharing">aquí</a>.

<br>

Ahora tomemos el algoritmo narrado que escribimos arriba, y dibujemos un diagrama de flujo.  Se vería de la siguiente forma:

```{figure} images/intro_programacion/diagrama_flujo.png
---
height: 350px
name: diagrama_flujo
---
Diagrama de flujo.
```

<br>

## Pseudocódigo
Literalmente es "una especie de código" o "un código falso". Se le ha dado ésta denominación porque no es un lenguaje de programación, sino otra de las formas de expresar un algoritmo, usando palabras similares a las propias de los lenguajes de programación.

<br>

El pseudocódigo está compuesto por un conjunto de palabras en español, inglés o cualquier otro lenguaje natural, que representan una instrucción entendida de una manera específica por el algoritmo en la solución de un problema.

<br>

Por ejemplo, el algoritmo que hemos estado haciendo en pseudocódigo se vería así:

<br>

```{code-block} none
Algoritmo numero_mayor_uno
  Definir x como Entero
	Escribir 'Escribe un número:'
	Leer x
	Si x>1 Entonces
		Imprimir 'El número es mayor a 1.'
	SiNo
		Imprimir 'El número es menor a 1.'
	FinSi
FinAlgoritmo
```
<br>

Es importante mencionar que el pseudocódigo utilizar un grupo de palabras reservadas, algunas de las cuales son:

<br>

`Algoritmo -FinAlgoritmo`
: Indica el comienzo y final del algoritmo, respectivamente. Cada algoritmo tentra solo un inicio y solo un final.

`Definir`
: Instrucción donde indicamos que se va a definir una variable y se indica el tipo de dato que contendrá.

`Escribir`
: Indicamos que el usuario ingresara un dato.

`Leer`
: Le indicamos a nuestro algoritmos que lea un dato de entrada, ingresado por el usuario, y que lo almacene en la memoria.

`Imprimir`
: Indicamos un mensaje de salida que puede leer el usuario.

`Entero, Real, Cadena, Caracter, Logico`
:Se usan para declarar el tipo de dato de las variables (veremos tipos de datos en los siguientes capitulos).

`Constante`
: Se utiliza para declarar constantes.

`Si, Entonces, SiNo, FinSi`
: Se usan para la toma de decisiones.

`Segun, Caso, FinCaso, EnOtroCaso, FinSegun`.
: Se usan para la toma de decisiones múltiples.

`Para, Hasta, Incremento, Decremento, FinPara`
: Especifican una estructura repetitiva condicionada al comienzo.

`Mientras, FinMientras`
: Se usan para el manejo de una estructura repetitiva condicionada al comienzo.

`Haga, MientrasQue`
: Se utilizan para diseñar una estructura repetitiva condicionada al final.

`Funcion, FinFuncion`
: Permite hacer la división en bloques funcionales independientes que retornan valores.

:::{admonition} Ejercicios (opcional)
:class: hint
Desarrolla un algoritmo narrado, diagrama de flujo y pseudocódigo para un programa que sume dos números y que escriba el resultado.

<br>

Consulta <a href = "https://drive.google.com/file/d/1_v94a7uGLWT7cY_9N3Uf3tu3kZRm1B2u/view?usp=sharing" >este documento</a>, para conocer los diagramas que puedes utilizar.
:::

::: {admonition} Nota importante
Éste capítulo es una modificación de una parte del siguiente libro: Herrera morales, J.O, Gutiérrez posada, J.E y Pulgarin Giraldo, R. (2017). *Introducción a la Lógica de Programación*. (1a ed.). Colombia: EIIZCOM.
<br>

Si deseeas saber más y/o practicar más utilizando pseudocódigo, te recomiendo <a href= "http://pseint.sourceforge.net/">PSeInt</a>.
:::
