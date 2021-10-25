# Datos, variables y operadores

## Datos
Un dato es una representación simbólica (un número, letra, grafo, lo que quieras) de una característica de un elemento u objeto. Los datos pueden clasificarse en función de su composición, si son números, si tienen caracteres alfanuméricos, etc.

### Datos alfanuméricos
Estos datos se componen de la combinación de todos los caracteres conocidos, letras, dígitos, caracteres especiales (como ·, % ,/, _, etc.).  Estos se dividen en:

* Catacter: Literalmente, son los datos que solo tienen un caracter. Ejemplo: "b", "0", "1".
* Cadena o *string*: Son los datos compuestos por un conjunto de varios caracteres. Ejemplo: "Nayeli Luis".

:::{admonition} Nota
En la mayoría de los lenguajes de programación, este tipo de datos se escribe entre comillas o comillas simples. Así indicamos que se trata de una *string* o caracter.
:::

### Datos numéricos
Son los datos que se componen únicamente por números y signos positivo o  negativo. Estos se dividen en:

* Enteros: Números que no tienen punto decimal.
* Reales, flotantes o *float*: Son datos con un componente decimal, pueden ser negativos, positivos o cero.

### Datos lógicos o booleanos
Son aquellos que toman solo uno de dos posibles valores: `Verdadero`/`True`o `Falso`/`False`. Estos son equivalentos a los dígitos del sistema binario: 1 = Verdadero y 0 = Falso.

## Variables
En programación, una variable es una posición o espacio de memoria en el cual se almacena un dato. Su valor puede cambiar en cualquier momento de la ejecución de un programa, de ahí su nombre.

<br>

Para trabajar con variables, se deben tener presentes los siguientes elementos:
* Tipo: Se refiere al tipo de dato que va a lamacenar: caracter, cadena, entero, flotante o booleano.
* Nombre o identificador: Será la manera en que el programa se refiera al mismo dato durante toda su ejecución. Es importante que los identificadores sean descriptivos.
* Contenido

## Operadores
Un operador es un símbolo que permite realizar una operación con números o con datos que se encuentran almacenados en variables. En programación existen tres tipos: aritméticos, relacionales y lógicos.

### Operadores aritméticos
Se usan para realizar operaciones aritméticas entre datos numéricos.

<br>

|    Símbolo    |   Significado     |
| :------------ | ----------------: |
|        +      |        suma       |
|        -      |       resta       |
|        *      |  multiplicación   |
|        /      |      división     |
|        %      | residuo o módulo  |
|        ^      |      potencia     |

### Operadores relacionales o de comparación

<br>
Se utilizan para escribir expresiones de comparación, las cuales van a producir un resultado lógico o booleano (Verdadero o Falso).

|    Símbolo    |   Significado     |
| :------------ | ----------------: |
|        <      |    menor que      |
|        >      |    mayor que      |
|       <=      | menor o igual que |
|       =>      | mayor o igual que |
|       !=      |    diferente de   |
|       ==      |      igual que    |

### Operadores lógicos
Se utilizan para crear expresiones lógicas cuyo resultado sera de tipo lógico, es decir, verdadero o falso.

|    Símbolo    |   Significado     |
| :------------ | ----------------: |
|    AND (Y)    |    conjunción     |
|     OR (O)    |    disyunción     |
|    NOT (NO)   |     negación      |

Para aplicar estos operadores es necesario conocer las tablas de verdad.

#### AND

Para el operador `AND`, consideremos `p` y `q` como dos expresiones diferentes.

|   p   |   q   | p AND q    |
| :-----| ------ | ---------: |
|    V  |   V    |      V     |
|    V  |   F    |      F     |
|    F  |   F    |      F     |
|    F  |   V    |      F     |

Ejemplo:

¿Cuá es el resulado de lo siguiente?

```{code-block} none
p = 3 > 1 = Verdadero
q = 4 > 34 = Falso

Entonces la operación:
p AND q = Falso
```

Es decir que, ambas expresiones deben ser ciertas para que el resultado sea cierto.

#### OR

Para el operador `OR` la tabla de verdad sería la siguiente:

<br>

|   p   |    q   |  p  OR q    |
| :---- |--------| ----------: |
|    V  |   V    |      V      |
|    V  |   F    |      V      |
|    F  |   F    |      F      |
|    F  |   V    |      V      |

<br>

En este caso, solo se requiere que una de las expresiones sea cierta, para que el resultado de la lógica sea cierta.

#### NOT
 El operador `NOT` literalmente es una negación,  entonces:

 <br>

|    p   |    NOT p    |
| :----- | ----------: |
|   V    |      F      |
|   F    |      V      |




::: {admonition} Nota importante
Éste capítulo es una modificación de una parte del siguiente libro: Herrera morales, J.O, Gutiérrez posada, J.E y Pulgarin Giraldo, R. (2017). *Introducción a la Lógica de Programación*. (1a ed.). Colombia: EIIZCOM.
:::
