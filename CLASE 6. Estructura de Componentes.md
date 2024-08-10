# 6. Components Structure.

Los ***componentes (components)*** son el ***conjunto*** de ***elementos HTML*** definidos en un ***archivo***, los cuales forman un ***elemento independiente*** para ser mostrado en la ***IU***.

## Estructura de Componente

Los ***componentes*** son la pieza mas ***básica***. en el ámbito.

La ***estructura*** de estos es ***muy similar*** a los ***layouts***, cuentan con ***3 partes***.

	- Importaciones
	- Contenido
	- Estilos CSS

## 1. Importaciones

El ***módulo*** de las ***importaciones*** es ***idéntico*** al de los otros ***2 elementos*** ya vistos.

En este ***módulo*** se ***definen*** las ***propiedades*** que serán recibidas, así como los ***tipos de datos*** de estas.

Así mismo, podemos ***desestructurar*** las ***propiedades*** del ***componente*** que se encuentran dentro de ***Astro.props*** para utilizarlas como ***identificadores simples***.

~~~
---
interface Props {
	title: string;
	body: string;
	href: string;
}

const { href, title, body } = Astro.props;
---
~~~

El ***componente*** de este ***ejemplo*** recibe ***3 parametros***, todos definidos como ***strings***, los cuales son: ***title***, ***body*** y ***href***.

Por los tanto, el ***componente*** debió ser invocado, de la siguiente manera:

~~~
<Card
	href="https://docs.astro.build/"
	title="Documentation"
	body="Learn how Astro works and explore the official API docs."
/>
~~~

***Nota:*** La palabra definida ***Card*** viene de con que nombre sea ***importado***, en este caso, fue con la palabra ***Card***, pero puede ser cambiada.

~~~
import Card from '../components/Card.astro';
~~~

	Dentro del módulo de IMPORTACIONES tambien podemos utilizar codigo JS al gusto, incluso importar otros componentes para ingresar en nuestro componente actual.

## 2. Contenido

Dentro del ***contenido*** del ***componente*** se encuentra el ***código HTML*** puro que deseamos ***simplificar*** al ***llamar*** al componente***.

Ejemplo:

~~~
<li class="link-card">
	<a href={href}>
		<h2>
			{title}
			<span>&rarr;</span>
		</h2>
		<p>
			{body}
		</p>
	</a>
</li>
~~~

Las ***propiedades*** son ***utilizadas*** dentro del ***contenido***, para poder personalizar el ***componente***.

## 3. Estilos CSS

Los ***estilos*** son simple ***CSS***, explicado en la ***clase 4*** en ***estilos CSS***. sin olvidar el ***scope*** de los estilos.
