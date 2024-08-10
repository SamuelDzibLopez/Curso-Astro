# 5. Layouts Structure.

Los ***layouts*** son el ***componente*** que envuelve dentro de si el ***contenido general*** ***dentro*** de la ***page***.
## Estructura de Layout

La ***estructura*** de un ***layout*** es muy similar a los ***pages***, únicamente diferente debido a sus características, pero tiene la misma ***estructura básica***.

Cuenta con sus:

	- Importaciones
	- Contenido
	- Estilos CSS

### 1. Importaciones

Igual a las ***pages***, los ***layouts*** tienen la sección de ***importación***.

Dentro de esta, se definen las ***reglas*** de las ***propiedades*** que recibe el ***layout***, tales como el tipo de dato.

Así mismo, también se suelen ***desestructurar*** las ***props*** de esta, para un manejo mas sencillo

Un ejemplo:

~~~
---
interface Props {
	title: string;
}

	const { title } = Astro.props;
---
~~~

En este código de ***importaciones*** se define que la ***prop*** de nombre ***title*** debe ser un ***string***, así como se desestructura una ***constante del mismo nombre*** que el ***atributo title*** que se encuentra en ***Astro.props***.

El ***layout*** debió invocarse en otro archivo:

~~~
<Layout title="Welcome to Astro.">
</Layout>
~~~

Definiendo una ***propiedad*** con el mismo ***nombre title*** y un valor ***string***.

***Nota:*** dentro de este, también podemos escribir ***codigo JavaScript*** e invocar ***importaciones*** de otros ***componentes*** si lo necesitamos.

***TipeScript*** tambien nos ayuda a poder ***delimitar*** las ***props***, de tal manera que ***no aceptará props*** no definidas.

Un ejemplo llamando un ***layout*** pasando una ***prop*** que no existe.

~~~
<Layout title="Welcome to Astro." a="Hola">
</Layout>
~~~

***Nota:*** Al pasar el ***cursor*** en la ***prop*** ***no definida***, nos mostrará el ***error***.

El error se soluciona ***agregando*** la ***propiedad*** al ***layout***:

~~~
interface Props {
	title: string;
	a: string;
}
~~~

### 2. Contenido

No hay nada nuevo, dentro del ***contenido*** del ***layout*** se coloca la ***estructura HTML estática*** que deseamos contenga.

En el ejemplo, es toda la ***estructura principal básica*** de un ***archivo .html***.

~~~
<!doctype html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="description" content="Astro description" />
		<meta name="viewport" content="width=device-width" />
		<link rel="icon" type="image/svg+xml" href="/favicon.svg" />
		<meta name="generator" content={Astro.generator} />
		<title>{title}</title>
	</head>
	<body>
		<slot />
	</body>
</html>
~~~

El ***codigo dinámico*** que deseamos ***introducir*** al llamarlo en una ***page*** se coloca con la ***etiqueta slot***. definiendo el contenido de este el el archivo ***page*** (mostrado en la clase 4).

***Nota:*** El uso de las ***propiedades*** se realiza por medio de sus ***identificadores***.

Como en el ejemplo del ***title***:

~~~
	<title>{title}</title>
~~~

Dentro de los ***{}*** podemos definir ***código JS***.

~~~
{console.log("hola")}
~~~

***Nota:*** La ***consola*** de ***astro*** es el ***CMD*** desde al cual abrimos el ***proyecto***.

### 3. Estilos CSS

Los ***estilos*** son simple ***CSS***, explicado en la ***clase 4*** en ***estilos CSS***. 

