# Git y Github
**Autora: M. Nayeli Luis-Vargas**

:::{admonition} Objetivo
:class: tip
* Entender la diferencia entre Git y Github.
* Conocer los comandos básicos de Git para actualizar repositorios en GitHub
:::

::::{margin}
:::{admonition} Videos
:class: note
<a href = "https://git-scm.com/video/what-is-version-control">What is Version Control?</a>
::::

## Sistema de control de versiones

Un **sistema de control de versiones** es un sistema que registra los cambios de un archivo o un conjunto de archivos a lo largo del tiempo, de manera que puedas acceder a alguna versión antigua posteriormente. Tod@s hemos generado copias de un archivo para posteriormente modificarlo y así guardar la versión anterior, de manera similar funcionan los sistema de control de versiones. Cuando trabajas solo, generar copias de tus archivos puede funcionar, pero... ¿Qué pasa si estás generando un proyecto en conjunto con otras personas?, para ésto se inventaron los **sistema de control de versiones centralizados** (ver {ref}`control_versiones`), estos tienen un solo servidor que contiene todos los archivos y sus versiones, de manera que los usuarios puede extraer, cosultar o modificar archivos desde ese sitio central. El problema que tenemos ahora es que todo se encuentra en un sólo servidor, si éste falla se corre el riesgo de perder todos esos archivos.

<br>

En ésta parte de la historia entra los **sistemas de control de versiones distribuidos** como Git, Mercurial, Bazaar o Darcs. En estos sistemas los clientes no solo revisan la última version de los archivo, más bien ellos pueden ver todo el repositiorio completo con sus versiones. Además, si algún servidor muere el resto de los colaboradores tienen un clon de los archivos, literalmente un copia de seguridad completa de todos los datos (ver {ref}`control_versiones`).

<br>

```{figure} images/git_github/control_versiones.png
---
height: 500px
name: control_versiones
---
Diferencia entre control de versiones (centralizado y distribuido).
```
<br>

## Git

<a href = "https://git-scm.com/">Git</a> es un sistema de control de versiones  distribuido.  Otros sistemas de control de versiones almacenan la información como una lista del conjunto de archivos y los cambios realizados en cada archivo a lo largo del tiempo (esto es comúnmente descrito como control de versiones basado en delta).

<br>

Git no trabaja de esa forma, Git piensa en sus datos como una serie de copias instantáneas (*snapshots*) de un sistema de archivos en miniatura. Con Git, cada vez que se confirma o se guarda el estado de un proyecto, Git literamente toma una foto de cómo se ven todos sus archivos en ese momento y almacena una referencia a esa *snapshot*. Además, para aumentar su eficiencia, Git no vuelve a almacenar el archivo, solo un enlace al archivo idéntico al anterior ya almacenado. Además, Git sólo necesita archivos y recursos locales para trabajar.

<br>

### Los tres estados de Git

Ahora, es importante recalcar que Git tiene tres estados principales en los que se pueden encontrar los archivos:

<br>

* *Modified* (modificado): Significa que ha cambiado un archivo pero aún no se ha enviado a la base de datos.
* *Staged* (en proceso/preparación): Significa que ha marcado un archivo modificado en su versión actual para que vaya en tu próxima confirmación.
* *Commited* (confirmado): Significa que los datos ya se almacenan de forma segura en su base de datos.

<br>

Est nos lleva a las tres secciones principales de un proyecto Git: el directorio de trabajo, el área de preparación  (*staging area*) y el directorio Git (ver {ref}`arbol_git`)

<br>

```{figure} images/git_github/arbol_git.png
---
height: 400px
name: arbol_git
---
Secciones de un proyecto Git.
```

<br>

El directorio de Git es donde se alamacenan los metadatos y la base de datos objetos para tu proyecto. El directorio de trabajo es una copia de una versión del proyecto y el área de preparación almacena la información acerca de lo que va a ir en tu próximo `commit` (confirmación), el área de preparación es como el sitio de espera.

<br>

Entonces el flujo de trabajo de Git es el siguiente:
1. Se modifican archivos en tu directorio de trabajo.
2. Se eligen los archivos que desea que formen parte de su próxima versión, en el área de preparación.
3. Se hace una confirmación, que toma los archivos tal como están en el área de preparación y se alamcena una *snapshot* permanente en su directorio de Git.

### Instalación de Git

Para instalar Git en sistema Linux:

<br>

```{code-block} bash
sudo dnf install git-all
```
<br>

o

```{code-block} bash
sudo apt install git-all
```

<br>

En macOS, se debe tener instalado <a href = "https://brew.sh/">Homebrew</a> o <a href = "https://developer.apple.com/xcode/">Xcode</a> para posteriormente
<a href = "https://git-scm.com/download/mac">instalar Git</a>.

## GitHub

<a href = "https://github.com/">GitHub</a> es el host más grande para los repositiorios Git y es el punto central de colaboración de millones de desarrolladores y proyectos.

<br>

## Primeros pasos con Git y GitHub


::::{margin}
:::{admonition} Buscador de comandos
<a href = "https://git-scm.com/docs">Aquí</a> la documentación de Git, para que busques y revises los comandos que necesites.
:::
::::

Lo que vamos a aprender a continuación es a manejar repositorios desde nuestra comput
Primero, para poder utilizar Git y Github desde tu computadora debes crear un token de acceso personal, el cual utilizarás como contraseña en la línea de comandos, para ellos debes seguir <a href = "https://docs.github.com/es/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token">este tutorial</a>. Guarda tu token en un lugar seguro, no lo compartas.

Ahora, vamos a iniciar sesión en Github y a crear un nuevo repositorio.

<br>

```{figure} images/git_github/01_nuevo_repositorio.png
---
height: 400px
name: 01_nuevo_repositorio
---
Generar nuevo repositorio.
```
<br>

Podemos nombrar, dar una descripción de nuestro repositorio, elegir si deseamos que sea público o privado y elegir si queremos que se generen automáticamnte algunos archivos (recomiendo que des click en "Learn more" para saber de qué va cada uno). Una vez que hayamos configurado nuestro nuevo repositorio, damos click en "Create repository".

 <br>

 ```{figure} images/git_github/02_nombrar_repositorio.png
 ---
 height: 500px
 name: 02_nombrar_repositorio
 ---
 Configurar repositorio.
 ```

Nos llevará a una ventana en donde nos mostrará la dirección de nuestro repositorio y algunas opciones que podemos configurar desde nuestra línea de comandos. Por ahora, copia la dirección de tu repositorio.

<br>

```{figure} images/git_github/03_direccion.png
---
height: 450px
name: 03_direccion
---
URL de nuestro repositorio.
```
<br>

Ahora, comenzaremos a usar nuestra línea de comandos para trabajar archivos desde nuestra computadora y subirlos a Github. Para esto lo primero que haremos será clonar nuestro repositorio a nuestra computadora con los comandos `git clone url_repositorio`. Elige el lugar donde quieras que esté, yo la pondré en mi carpeta de Documentos.

<br>

```{code-block} bash
cd Documentos
git clone https://github.com/Nayeli-Luis/pruba_repositorio.git
```
Cuando hagas esto, te pedirá un usuario y tu contraseña. Tu usuario de Github aparece en la URL: https://github.com/nombre-usuario, en mi caso https://github.com/Nayeli-Luis, entonces mi usuario seria Nayeli-Luis. Por otro lado, la contraseña es el token que has creado previamente, NO es la contraseña de tu cuenta de Github.

<br>

Después de que hayas ingresado tus datos te debe aparecer una carpeta con el nombre de tu repositorio, puedes comporbarlo haciendo un listado con `ls`. Lo que haremos ahora es generar un archivo de texto.  Una vez que tu archivo esté generado, editalo escribiendo tu nombre, tu correo y tu película favorita. Sino recuerdas como hacer algo de esto, te sugiero que revises el capítulo anterior.

<br>
También puedes creear una carpeta en tu computadora y generar un repositorio vacío escribiendo:

```{code-block} bash
git init
```

<br>

Ahora subiremos nuestro archivo con `git add`, paa subir todo lo que tenemos en nuestro repositorio se agrega `./*`, entonces escribimos en terminal:

 ```{code-block} bash
 git add ./*
 ```

También podemos agregar un archivo en específico poniendo `git add nombre_archivo`.

<br>

y damos 'Enter', en terminal verás que no ocurre nada, pero Git ha recibido la instrucción de agregar todos los archivos al repositorio. De aquí, podemos confirmar que
vamos a guardar ese archivo en nuestro repositorio local con `git commit`, además podemos usar la opción `-m` para agregar algún mensaje. Entonces escribimos en terminal:

```{code-block} bash
git commit -m "estoy subiendo un archivo nuevo"
```

Finalmente, vamos a transferir o enviar la confirmación que se realizó en nuestra computa al repositorio remoto en GitHub con `git push`.

```{code-block} bash
git push
```
<br>

Si entramos a GitHub debemos ver el archivo que hemos subido, el mensaje cuando hicimos `commit` y desde hace cuánto tiempo lo subimos:

<br>

```{figure} images/git_github/04_archivo_github.png
---
height: 200px
name: 04_archivo_github
---
Archivo en GitHub.
```

<br>

Si estamos colaborando en un proyecto más grande y deseamos ver el historial de todos los "commits" (confirmaciones) que se han hecho, podemos escribir en terminal:

<br>

```{code-block} bash
git log
```
<br>

Te aparecerá algo similar a esto:

<br>

```{figure} images/git_github/05_git_log.png
---
height: 150px
name: 05_git_log
---
Mensaje en terminal de git log.
```
<br>

En donde te la clave del `commit`, el autor quien lo llevó a cabo y la fecha.

<br>

Para conocer el status de todos tus archivos en general, podemos escribir en terminal:

```{code-block} bash
git status
```
<br>

:::{admonition} Resumen de comandos de Git
:class: tip
`git clone`
: Clonar un repositorio virtual en computadora local.

`git init`
: Crea un repositorio vació en la carpeta actual (directorio de trabajo).

`git add`
: Agregar archivo al repositorio

`git commit`
: Guarda los cambios en el repositorio local.

`git push`
: Envia los cambios al repositorio virtual.

`git log`
: Ver el historial de los *commits* que se han hecho en un proyecto.

`git status`
: Conocer el estado de todos los archivos de un repositorio.
:::


:::{admonition} Para saber más
:class: attention
Éste capítulo es un resumen de parte del libro de <a href = "https://git-scm.com/book/en/v2">Git Pro</ao>
:::
