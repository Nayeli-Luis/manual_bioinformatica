# Explorando directorios desde la terminal

:::{admonition} Objetivo
:class: tip
* Identificar la arquitectura jerárquica que tienen los directorios en una computadora.
* Entender los comandos `pwd`, `cd`, `ls`, `mkdir`.
:::

::::{margin}
:::{admonition} Shortcuts
:class: tip
Algunos shortcuts para hacer más fluído tu uso de la terminal:
* `tab`: Completa el nombre de un fichero o directorio existente.
* `Ctrl + a`: Ir al principio de la línea.
* `Ctrl + e`: Ir al final de la línea.
* `Ctrl + l` o comando `clean`: Limpiar pantalla.
* Uso de flechas del teclado permite ver el historial de comandos recientes.
* `Ctrl + r`: Espera que des un patrón de búsqueda. Te regresa las líneas que has ejecutado que contengan ese patrón. 

:::
::::

Una vez que ya conoces los comandos básicos para usar en terminal, vamos a practicar un poco. Para este ejercicio utilizaremos una terminal virtual llamada <a href = "https://sandbox.cs50.io/">CS50 Sandbox </a>, al dar click te aparecerá la siguiente ventana:
<br>

```{figure} images/03_explorando_direc/1.png
---
height: 400px
name: ventana Sandbox
---
Ventana de la terminal virtual Sandbox
```

<br>
Da click en crear para poder acceder a la terminal virtual.

<br>
:::{admonition} Nota
:class: warning
Para poder acceder debes tener una cuenta de <a href = "https://github.com/">GitHub</a>, sino la has creado, ahora es el momento perfecto.
:::

<br>
En seguida te aparecerá la siguiente interfaz:

<br>

```{figure} images/03_explorando_direc/2.png
---
height: 450px
name: interfaz
---
Interfaz de la terminal virtual Sandbox.
```

<br>

Vamos a crear un directorio con el comando de ***make directory*** (`mkdir`), para ello escribirás lo siguiente en la terminal y darás 'Enter'.
<br>

```{code-block} bash
mkdir mi_directorio
```

<br>

En seguida te aparecerá el directorio que creeaste en el árbol de directorios:

<br>

```{figure} images/03_explorando_direc/3.png
---
height: 300px
name: directorios
---
Árbol de directorios de la terminal virtual de Sandbox.
```

<br>

Ahora accedamos a ese directorio con el comando ***change directory*** (`cd`):
<br>

```{code-block} bash
cd mi_directorio
```

<br>
y vamos a crear dos directorios aquí:
<br>

```{code-block} bash
mkdir dir1 dir2
```

<br>
Si das click en tu carpeta principal 'mi_directorio', en el árbol de directorios te aparecerán tus dos nuevas carpetas. Pero si queremos verlas desde la terminal, podemos dar la instrucción de que las liste (`ls`).
<br>

```{code-block} bash
ls
```

<br>
¿Qué notas? Si pones atención en la terminal, los diectorios aparecen marcados de azul y con una diagonal (/) al final del nombre.
<br>

```{figure} images/03_explorando_direc/4.png
---
height: 300px
name: nombres directorios
---
Nombre de los directorios aparecen resaltados.
```
<br>
Bien, ahora entremos al 'dir1' y creemos un par de directorios más.
<br>

```{code-block} bash
cd dir1
mkdir dir3 dir4
```

<br>
¿Notaste que pude crear dos directorios de golpe?
<br>

Si no tuvieramos la pestaña del árbol de directorios pero quisieramos saber en dónde se encuentra nuestra carpeta 'dir3', utilizariamos `pwd`.
<br>

Accede a tu carpeta 'dir3' y teclea el comando para imprmir la ruta o dirección.
<br>

```{code-block} bash
cd dir3
pwd
```

<br>
Te aparerá algo así:
<br>

```{code-block} bash
/root/sandbox/mi_directorio/dir1/dir3
```

<br>
Ésta es tu directorio de trabajo (***working directory***), te encuentras en el directorio llamado 'dir3', y si creas más directorios o archivos, se colocarán aquí.
<br>

Ahora ¿Qué pasa si quieres volver al directorio anterior?, la isntrucción que darás es la siguiente:
<br>

```{code-block} bash
cd ..
```

<br>
Y si imprimes la ruta verás que ahora te encuentras en 'dir1'.
<br>

```{code-block} bash
/root/sandbox/mi_directorio/dir1
```

<br>
Por último, si quisieramos volver al directorio raíz, es decir, a 'root/sandbox', tendríamos que escribir:
<br>

```{code-block} bash
cd
```

<br>
Imprime de nuevo la ruta para que te asegures:
<br>

```{code-block} bash
/root/sandbox
```
<br>

## Rutas absolutas y rutas relativas

Una **ruta absoluta** de un directorio nos indica todo el camino que hay que recorrer para llegar a él. Mientras que, una **ruta relativa** apunta a una referencia y luego indica el camino a partir de esa referencia. Imagina que invitas a un@ amig@ a tu casa, no es lo mismo darle instrucciones si el punto de partida es su casa; a darle instrucciones si el punto de partrida es desde la tienda más cercana a tu casa. Acá sucede lo mismo.

<br>

Considerando el ejercicio que hemos estado realizando, nuestro árbol de directorios se vería así:

<br>

```{figure} images/03_explorando_direc/arbol_ejercicio.png
---
height: 400px
name: arbol arbol_ejercicios
---
Representación gráfica del árbol de directorios para éste ejercicio.
```
<br>

Si quisieramos acceder a 'dir3' desde la terminal y escribiendo su ruta absoluta, ésta sería:

<br>

```{code-block} bash
cd /root/sandbox/mi_directorio/dir1/dir3
```

<br>

Sin embargo, si estuvieramos en 'dir2' y quisieramos acceder a 'dir3', estamos apuntando ahora a una referencia. Tendríamos primero que volver a 'mi_directorio' para luego ingresar a 'dir1' y finalmente a 'dir3', por tanto, la ruta relativa se vería así:

<br>

```{code-block} bash
cd ../dir1/dir3
```
 <br>

Nota que no escribí 'mi_directorio', en linea de comandos `../` indica "volver a la carpeta superior".


:::{admonition} Lo que debes saber:
:class: important
Con este pequeño tutorial debes saber:
* Que el orden de los directorios en una computadora tienen un orden jerárquico.
* El comando `mkdir` sirve para crear directorios.
* El comando `cd` sirve para cambiar de directorio.
* El comando `ls` sirve par enlistar los elementos que hay en un directorio.
* El comando `pwd` sirve para imprimir la ruta del directorio.
:::
