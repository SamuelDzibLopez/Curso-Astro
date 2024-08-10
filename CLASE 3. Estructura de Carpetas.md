# 3. Folder Structure.

Una vez ***creado*** el ***proyecto***, visualizemos su ***contenido*** y ***estructura***.

***Estructura:***

	- .vscode (Carpeta de ayuda a VSC)
	- node_modules (Carpeta de dependencias)
	- public (Carpeta para recursos publicos (img, etc))
	- src
		- components (Carpeta para los componentes)
		- layouts (Carpeta para las plantillas)
		- pages (Carpeta para paginas)

Ademas de los ***archivos*** de ***configuración***:

	.gitignore (Archivo util para git)
	astro.config.mjs (Archivo util para configuraciones de Astro)
	package-lock.json (Archivo util para informacion de version y datos)
	package.json (Archivo util para informacion de version y datos)
	README.md (Archivo para informacion md)
	tsconfig.json (Archivo de informacion de TypeScript)

La ***gran mayoria*** de ***librerias*** y ***frameworks*** basados en ***componentes***, suelen mantener una ***estructura similar***.

## Tipos de recursos

Donde ***cada*** de ***recurso*** es dividido por su ***tipo***.

	- Componentes: Partes de la UI reutilizables.

	- Layauts: Estructuras HTML basicas, donde dentro de estas se colocan los pages y Componentes.

	- Paginas: Plantillas y backgrounds que envuelven un contenido (una seccion o una pagina entera).

	- Recursos en public: Recursos utiles para la pagina, desde imagenes, icons, svgs, etc.

