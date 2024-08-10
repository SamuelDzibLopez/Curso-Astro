# 4. Pages Structure.

	Los archivos de Astro son .astro

***Nota:*** Para visualizar mejor los ***.astro***, podemos descargar el ***plugin oficial*** de ***astro*** en ***VSC***.

Las ***pages*** son el ***archivo en bruto*** que se crea para la navegación de la pagina mediante su ***URL***.
## Estructura de una page

Las ***paginas*** (dentro de ***pages***) siguen una ***estructura***.

### 1. Importaciones.

Al ***inicio*** de una ***page*** (y de también otros elementos .astro), encontraremos las ***inportaciones***:

~~~
---
import Layout from '../layouts/Layout.astro';
import Card from '../components/Card.astro';
---
~~~

***Nota:*** Siempre ***delimitados*** por los ***---***.

Estas ***importaciones de módulos*** son los ***elementos externos*** que utilizaremos dentro de la misma ***page***, tanto para ***renderizarlos*** como para otros asuntos (funciones).

Esto es ***JavaScript***, por lo que dentro de esta ***estructura***, podemos escribir ***código*** de ayuda.

***Nota:*** Como se muestra, el ***código anterior*** importa un ***elemento*** llamado ***Layout*** que se encuentra en el archivo con ruta ***../layouts/Layout.astro***. Este es una ***pantilla***.

Y otro ***elemento*** llamado ***Card*** ubicado en el archivo de ***../components/Card.astro***. Este es un ***componente***.

	Podemos hacer todas las importaciones que deseamos o necesitemos, de cualquier elemento (componente o layout).

### 2. Contenido

Después de las ***importaciones*** tenemos el ***contenido*** de la ***page***.

~~~
<Layout title="Welcome to Astro.">
	<main>
		<h1>Welcome to <span class="text-gradient">Astro</span></h1>
		<p class="instructions">
			To get started, open the directory <code>src/pages</code> in your project.<br />
				<strong>Code Challenge:</strong> Tweak the "Welcome to Astro" message above.
		</p>
		<ul role="list" class="link-card-grid">
			<Card
				href="https://docs.astro.build/"
				title="Documentation"
				body="Learn how Astro works and explore the official API docs."
			/>

			<Card
				href="https://astro.build/integrations/"
				title="Integrations"
				body="Supercharge your project with new frameworks and libraries."
			/>

			<Card
			href="https://astro.build/themes/"
			title="Themes"
			body="Explore a galaxy of community-built starter themes."
			/>

			<Card
				href="https://astro.build/chat/"
				title="Community"
				body="Come say hi to our amazing Discord community. ❤️"
			/>
		</ul>
	</main>
</Layout>
~~~

	Se ha eliminado el svg para una mejor explicación.

Donde en el ***contenido*** se encuentra lo que ***parece ser HTML***, pero con algunas ***etiquetas*** desconocidas (a estas etiquetas se les llama ***componentes***):

	- Layout
	- Card

Si nos fijamos, nos los mismo ***elementos*** que ***importamos*** en el ***módulo*** de ***importación.

Todo lo demás son ***etiquetas HTML*** simples.

#### Componentes en pages (Layouts y Componentes)

Los ***componentes*** son elementos, cuya estructura se encuentra ***definda*** en un ***archivo externo*** y que luego de ser ***importados*** y ***colocado*** en el ***contenido*** (definiendo sus ***props***) se puede visualizar.

Los ***componentes*** tienen reglas para ser definidos

	- Su nombre debe empezar con MAYUSCULA, para no confundirse con una etiqueta HTML simple

No es lo mismo:

~~~
<Button>Hola</Button>
~~~

Que:

~~~
<Button>Hola</Button>
~~~

La ***primera*** es una ***etiqueta HTML*** y la ***segunda*** es un ***componente***.

##### Layouts

Los ***layouts*** son los ***componentes*** que son ***ingresados*** dentro de una ***page***.

Estos contendrán el ***contenido*** que se desea mostrar, tales como ***elementos HTML*** o como también otros ***componentes***.

Como ejemplo, un ***layout*** tiene la sintaxis:

~~~
<Layout title="Welcome to Astro.">
	<!--Contenido de la pagina -->
</Layout>
~~~

Los ***layouts*** tienen una ***etiqueta de inicio*** y otra de ***final***, debido a que necesitan ***contenido***, a diferencia de los ***componentes***, los cuales solo necesitan una ***sola etiqueta***.

***Nota:*** El ***layout*** del ejemplo y el ***código*** tiene definido una ***propiedad*** llamada ***title***.

##### Componentes

Los ***componentes*** pueden ser un ***elemento*** o un ***conjunto*** de ***etiquetas HTML*** separadas por si solas de manera ***independiente*** en un archivo externo.

Los ***componentes*** son llamados dentro de los ***layouts***.

Un ejemplo de ***components***:

~~~
<Card

	href="https://astro.build/chat/"
	title="Community"
	body="Come say hi to our amazing Discord community. ❤️"
/>
~~~

Los ***componentes*** solo necesitan una ***sola etiqueta***, ya que su ***contenido*** se coloca dentro del archivo externo.

***Nota:*** El ***componente Card*** tiene definido diferentes ***propiedades***, tales como ***href***, ***title*** y ***body***.

### 3. Estilos CSS

Después del ***contenido***, viene la definición de ***estilos CSS***.

~~~
<style>
	main {
		margin: auto;
		padding: 1rem;
		width: 800px;
		max-width: calc(100% - 2rem);
		color: white;
		font-size: 20px;
		line-height: 1.6;
	}

	.astro-a {
		position: absolute;
		top: -32px;
		left: 50%;
		transform: translatex(-50%);
		width: 220px;
		height: auto;
		z-index: -1;
	}

	h1 {
		font-size: 4rem;
		font-weight: 700;
		line-height: 1;
		text-align: center;
		margin-bottom: 1em;
	}

	.text-gradient {
		background-image: var(--accent-gradient);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-size: 400%;
		background-position: 0%;
	}

	.instructions {
		margin-bottom: 2rem;
		border: 1px solid rgba(var(--accent-light), 25%);
		background: linear-gradient(rgba(var(--accent-dark), 66%), rgba(var(--accent-dark), 33%));
		padding: 1.5rem;
		border-radius: 8px;
	}

	.instructions code {
		font-size: 0.8em;
		font-weight: bold;
		background: rgba(var(--accent-light), 12%);
		color: rgb(var(--accent-light));
		border-radius: 4px;
		padding: 0.3em 0.4em;
	}

	.instructions strong {
		color: rgb(var(--accent-light));
	}

	.link-card-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(24ch, 1fr));
		gap: 2rem;
		padding: 0;
	}
</style>
~~~

Es ***identico CSS***, pero los ***estilos CSS*** dentro de archivos ***.astro*** tienen ***scope***, es decir, son locales únicamente al ***archivo*** definido.

Si deseamos que una ***etiqueta CSS*** sea global, necesitamos declararla:

~~~
<style is:global>
</style>
~~~

Con el ***atributo is*** con valor ***global***. De esta manera, sera una regla universal.