Solicitud de beca Erasmus+ · DAW Mobility

Proyecto de interfaz web desarrollado para el módulo de Diseño de Interfaces Web (2.º CFGS DAW). Consiste en una página de solicitud de becas Erasmus+ para prácticas en empresas europeas, construida íntegramente con HTML5 semántico y CSS3 moderno, sin dependencias externas ni imágenes.

Estructura del proyecto

├── index.html          # Estructura semántica, formulario accesible y cuadro de ayuda
├── styles/
│   └── estilos.css     # Hoja de estilos completa (layout responsive y CSS avanzado)
└── README.md           # Documentación del proyecto y auditoría de contraste


Características implementadas

1. HTML5 semántico y accesibilidad

Estructura de documento clara: Uso de etiquetas semánticas (<header>, <nav>, <main>, <aside>, <footer>) y agrupación lógica de controles mediante <fieldset> y <legend>.

Navegación por teclado: Enlace de salto directo al contenido principal (.salto), estados de foco visibles (:focus y :focus-visible) e indicador de página activa con aria-current="page".

Formularios accesibles: Asociación explícita entre <label> e <input>, textos de ayuda vinculados mediante aria-describedby, atributos autocomplete e inputmode adecuados y validación nativa HTML5 (required, min, max, step, maxlength, accept).

Áreas táctiles: Todos los controles interactivos y botones garantizan una altura mínima de 44px.

2. Diseño adaptable (Mobile-First)

Cabecera y pie flexibles: Maquetados con Flexbox (flex-wrap: wrap) para adaptarse sin desbordamientos desde móviles de 320px hasta pantallas de escritorio.

Rejillas con CSS Grid:

Distribución general de una columna en móvil que pasa a dos columnas (2fr 1fr) a partir de 56em.

Rejilla interna de 6 columnas y uso de grid-template-areas dentro de los bloques del formulario a partir de 40em.

Botonera adaptable que apila los botones al 100 % de ancho en móvil y los alinea en una fila en pantallas medianas y grandes.

3. Acabados con CSS avanzado 

Paleta centralizada en variables (:root): Todos los colores de la interfaz (primarios, fondos, bordes, estados de foco, errores y sombras con transparencia) están declarados una única vez como propiedades personalizadas con nombres funcionales, sin valores hexadecimales ni rgb() sueltos en el resto de la hoja.

Relieve y profundidad:

Sombras suaves (box-shadow) en las cuatro tarjetas del formulario (.grupo) y en el bloque lateral de ayuda (.ayuda), verificadas sin recortes en resoluciones de 1280px, 768px y 320px.

Sombra discreta (text-shadow) en la marca DAW Mobility de la cabecera para mejorar su legibilidad.

Degradados lineales con respaldo: Cabecera (.cabecera) y pie de página (.pie) rellenos con linear-gradient(to right, ...) desde el azul principal (#12355b) hasta un tono más claro (#1f5088), manteniendo un background-color liso debajo como respaldo.

Botones interactivos y transiciones:

El botón principal (Enviar solicitud) cuenta con relieve en reposo (box-shadow) que se reduce al mantenerlo pulsado (:active).

Todos los botones comparten una transición suave de 0.2s declarada en la clase base .boton sobre las propiedades concretas (background-color, transform y box-shadow, evitando all).

Al pasar el ratón (:hover) o enfocar con teclado (:focus-visible), cambian su color de fondo y se elevan 2px mediante transform: translate(0, -2px), conservando visible el contorno de foco (outline).

Microinteracción en los pasos de ayuda: Al situar el cursor sobre cualquiera de los pasos de Antes de empezar (.ayuda__paso:hover), su círculo numerado crece un 10 % (transform: scale(1.1)) de forma fluida en 0.2s sin desplazar ni solapar el texto adyacente.

Medición de contraste (WCAG AA)

Para comprobar que el texto blanco (#ffffff) de la cabecera y el pie mantiene una legibilidad adecuada incluso en el extremo más claro del degradado (#1f5088), se realizó la siguiente verificación:

Valor obtenido: 8.36:1 (supera ampliamente el mínimo de 4.5:1 exigido por el criterio WCAG 2.1 nivel AA para texto normal).

Método de medición:

Se abrió la página en el navegador y se inspeccionó el enlace situado más a la derecha de la cabecera (Contacto) mediante las Herramientas de desarrollo (DevTools).

En el panel de estilos de .menu__enlace, se abrió el selector de color de la propiedad color (#ffffff).

En la sección Relación de contraste del selector, se tomó como referencia de fondo el color del extremo derecho del degradado (#1f5088), confirmando el cumplimiento del nivel AA y AAA.

Cómo visualizar el proyecto

Clona o descarga este repositorio.

Abre el archivo index.html directamente en cualquier navegador web moderno (o mediante una extensión como Live Server en Visual Studio Code).