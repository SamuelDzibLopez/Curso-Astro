# 2. Installation

A continuación, se detallan los ***pasos ordenados*** para poder crear un ***proyecto Astro***

## Paso 1. Instalación de node.js 

Como primer paso, se necesita realizar la instalación del ***ambiente node.js***  en el equipo.

	https://nodejs.org/en/download/package-manager

Para ***realizar la instalación***, puede consultar el ***enlace oficial*** de ***node.js***.

***Nota:*** Puede descargar el ***instalador*** o ***instalar*** directamente desde el ***CMD*** o ***terminal***.

---
## Paso 2. Verificación de instalación de node.js y versión

Puede ***verificar*** la ***versión*** de ***node.js*** una vez instalada:

~~~
node -v
~~~

Para ello el ***comando***.

---
## Paso 3. Creación de Nuevo Proyecto Astro

A continuación, crearemos un ***nuevo proyecto*** de ***Astro***, para ello, utilizaremos el siguiente comando:

~~~
npm create astro@latest
~~~

Si es nuestra primera ocasión, ***node***  avisará de la falta de ***Astro*** y preguntarnos si deseamos instalarlo (y).

***Nota:*** No olvidemos ***acceder*** al ***directorio*** donde se desea crear el ***proyecto***.

---
## Paso 4. Configuración del Proyecto

A continuación, configuraremos nuestro ***proyecto***, con unas preguntas.

1. Definir ***nombre del proyecto***.

Se nos pedirá colocar un nombre:

	Where should we create your new project?

Donde deberemos colocar un ***nombre*** al ***proyecto***:

~~~
[nombre-del-proyecto]
~~~

2. Creación de ***archivos del proyecto***

Podremos elegir como deseamos ***inicializar*** nuestro ***proyecto***.

	How would you like to start your new project?
         ● Include sample files (recommended)
         ○ Use blog template 
         ○ Empty 

Ya sea:

	- incluir archivos simples
	- Una plantilla tipo blog ya creada
	- vacio

3. Instalación de ***dependencias del proyecto***.

Preguntará se deseamos utilizar ***TypeScript***:

	Do you plan to write TypeScript?
	● Yes  ○ No 

A elección.

Si ***elegimos Yes***, preguntara el ***tipo***:

	How strict should TypeScript be?
         ● Strict (recommended)
         ○ Strictest 
         ○ Relaxed 

A continuación, se nos pregunta si deseamos instalar ***dependencias***.

	Install dependencies? (recommended)
         ● Yes  ○ No 

***Accedemos*** con ***Yes***.

4. Inicializacion de ***repositorio del proyecto***.

Y para ***finalizar***, inicializar un ***repositorio***.

	Initialize a new git repository? (optional)
         ● Yes  ○ No 

***De esta MANERA, empezará a CREAR nuestro PROYECTO, con las configuraciones***.

---

## Paso 5. Acceder al Proyecto

Una vez ***creado*** el ***proyecto*** accedemos

~~~
cd [nombre-del-proyecto]
~~~

***Nota:*** Podemos ***abrir*** el ***proyecto*** en ***VSC***:

~~~
code .
~~~
