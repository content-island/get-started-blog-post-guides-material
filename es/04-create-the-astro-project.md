# 4. Creando el proyecto en Astro

Para crear el proyecto con Astro, vamos a arrancar desde cero.

Lo primero, utlizamos el CLI de Astro para crear la estructura del proyecto:

```bash
npm create astro@latest
```

Le damos como nombre al proyecto "myblog".

Elegimos la opción "A basic, minimal starter".

Elegimos en "Install Dependencies", Yes.

Y en "Initalize Git Repository", como quieras, en este caso Yes.

Ahora entramos en la carpeta del proyecto (lo ideal es abrir la carpeta nueva desde VSCode).

Arrancamos el proyecto y vemos que funciona.

```bash
npm run dev
```

Abrimos en el navegador y navegamos a la ruta "locahost:4321" y vemos que se muestra la página de ejemplo.

Para estar más cómodos, voy a abrir el proyecto en VSCode, directamente desde la carpeta que se ha creado, y para que sea más fácil formatear el código, vamos a instalar prettier y la extensión para astro

```bash
npm install --save-dev prettier
```

```bash
npm install --save-dev prettier-plugin-astro
```

Y añadimos configuración para prettier en el archivo ".prettierrc":

```json
{
  "plugins": ["prettier-plugin-astro"],
  "overrides": [
    {
      "files": "*.astro",
      "options": {
        "parser": "astro"
      }
    }
  ]
}
```

# Limpiando

Y, ya que estamos, borramos los ficheros que no necesitamos:

- _./src/assets/astro.svg_
- _./src/assets/background.svg_
- _./components/Welcome.astro_

y en _./src/routes/index.astro_ actualizamos:

```diff
---
- import Welcome from '../components/Welcome.astro';
import Layout from '../layouts/Layout.astro';

// Welcome to Astro! Wondering what to do next? Check out the Astro documentation at https://docs.astro.build
// Don't want to use any of this? Delete everything in this file, the `assets`, `components`, and `layouts` directories, and start fresh.
---

<Layout>
-	<Welcome />
+ <h1>Hello Blog !</h1>
</Layout>

```

Ya estamos listos para empezar a crear nuestro blog.
