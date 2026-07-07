# Portafolio Web

**Estudiante: ** Edwin Alexis Esperanza Chavez ** ***Verano 2026 Programacion Web*

## Descripción del Proyecto

Este proyecto es un portafolio personal interactivo diseñado para mostrar mis proyectos, habilidades y experiencia como Ingeniero en Sistemas. El sitio está construido con **HTML5, JavaScript puro (Vanilla JS) y SCSS/CSS puro**[cite: 6, 8, 9], sin el uso de frameworks externos como Bootstrap o Tailwind, lo que permite un control total sobre el diseño, animaciones y rendimiento, aplicando la metodología BEM para la organización del código.

Se utilizó una plantilla base como punto de partida, la cual fue fuertemente modificada y adaptada para cumplir con los requerimientos visuales y funcionales modernos.

**Plantilla original:** [portfolio-responsive-complete]({https://github.com/bedimcode/portfolio-responsive-complete})

### Secciones del Portafolio

El portafolio es una Single Page Application (SPA) estructurada en las siguientes secciones:

*   **Inicio (`#home`):** Sección de bienvenida o hero. Incluye un título principal, enlaces a redes sociales (LinkedIn y GitHub) y un gráfico SVG integrado que enmarca la foto de perfil.
*   **Sobre Mí (`#about`):** Una breve biografía que detalla mi enfoque autodidacta y mi objetivo profesional de fusionar el desarrollo web y de redes con la creación de software de audio profesional.
*   **Habilidades (`#skills`):** Un desglose visual de mi stack tecnológico, utilizando barras de progreso animadas para representar el nivel de dominio en lenguajes y herramientas como Java (95%), HTML (95%), CSS (80%), JavaScript (85%), Bases de Datos (90%), C++ (60%) y Python (50%).
*   **Proyectos (`#work`):** Una galería tipo grid que exhibe capturas de los proyectos desarrollados, con efectos de escalado al hacer hover.
*   **Contacto (`#contact`):** Un formulario de contacto funcional validado mediante JavaScript.

## Proceso de Creación

La construcción de este portafolio implicó una serie de pasos desde la integración de la plantilla hasta la personalización avanzada del código:

1.  **Adaptación de la estructura base:** Se limpió el HTML de la plantilla original y se definieron etiquetas semánticas (`<header>`, `<main>`, `<section>`, `<footer>`) para mejorar la accesibilidad y el SEO.
2.  **Implementación de un Tema Oscuro (Dark Mode):** Se migraron las variables de CSS a SCSS para tener un mejor control del entorno. Se modificó la paleta de colores completa, estableciendo un esquema oscuro con un color de fondo `#191919` y un color de acento rojo utilizando la variable `--hue-color: 355`.

    ```scss
    /* Modificación de variables SCSS para el entorno oscuro */
    :root {
        --hue-color: 355;
        --first-color: hsl(var(--hue-color), 89%, 60%);
        --body-color: hsl(var(--hue-color), 20%, 8%);
        --container-color: hsl(var(--hue-color), 20%, 12%);
        --text-color: hsl(var(--hue-color), 20%, 88%);
    }
    ```
3.  **Creación de animaciones CSS Avanzadas:** Se reemplazaron los estilos de botones genéricos por componentes personalizados con efectos de "borde mágico" o "gusano", logrados exclusivamente con pseudo-elementos (`::before` y `::after`) y `conic-gradient`. Esto añade un alto nivel de dinamismo sin cargar scripts adicionales.

    ```css
    /* Efecto de borde dinámico en botones */
    .button::before {
        content: "";
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: conic-gradient(from 0deg, transparent 70%, var(--first-color) 100%);
        animation: spinWorm 2s linear infinite;
        z-index: -2;
    }
    ```
4.  **Validación y Lógica del Formulario:** Para evitar envíos vacíos o erróneos, se desarrolló un script en JavaScript que captura el evento `submit`, limpia los datos (`trim()`) y evalúa el formato del correo mediante expresiones regulares (`/^[^\s@]+@[^\s@]+\.[^\s@]+$/`) antes de procesar el mensaje.

## Capturas de Pantalla

A continuación, se muestra el resultado final del portafolio ejecutándose en el navegador:

**Vista de Inicio y Menú de Navegación:**
![Vista de la seccion de inicio](https://i.postimg.cc/ry9Ss63W/Captura-de-pantalla-2026-07-06-230239.png)

**Sección de Habilidades y Tecnologías:**
![Vista de la sección de habilidades](https://i.postimg.cc/kX4t52xq/Captura-de-pantalla-2026-07-06-230817.png)

**Sección de Proyectos:**
![Vista de la galería de proyectos](https://i.postimg.cc/8zb5BDdB/Captura-de-pantalla-2026-07-06-230954.png)

**Formulario de Contacto (con validación activa):**
![Vista de la sección de contacto](https://i.postimg.cc/L8v9gDRV/Captura-de-pantalla-2026-07-06-231541.png)