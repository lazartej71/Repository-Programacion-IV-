# AIda – Asistente Institucional UTN FRT

**Trabajo Final – Tecnicatura Universitaria en Programación – UTN FRT**

Sistema de gestión de consultas y conocimiento académico con panel web y asistente conversacional basado en IA.

## Integrantes
- Lazarte, Jorge Exequiel
- Díaz, Juan Gabriel

## Descripción breve
AIda es una plataforma integral que centraliza la información académica de la UTN FRT (mesas de examen, inscripciones, correlativas, trámites, ingreso de nuevos estudiantes, calendario) y la pone a disposición de los estudiantes a través de un asistente conversacional inteligente, con citas de fuentes oficiales y derivación a personal humano cuando no se tiene certeza. Además, incluye un panel de gestión para Bedelía, Alumnado y Secretaría para cargar y actualizar la información, atender consultas derivadas y medir métricas de uso.

## Tecnologías utilizadas
- **HTML5 semántico**
- **CSS3** (variables, Flexbox, Grid, media queries)
- **Git & GitHub** (control de versiones, ramas `main` y `dev`, Pull Requests)

## ¿Dónde utilizaron Flexbox?
- En el **header**, para distribuir el logo y la navegación horizontalmente.
- En el **hero**, para alinear el texto y la imagen de forma flexible.
- En el **footer**, para separar la información institucional del logo.

## ¿Dónde utilizaron Grid?
- En la sección **"Cómo funciona"**, donde las tarjetas se organizan en una cuadrícula adaptable (`grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`).
- En la sección **"Temas"**, donde los elementos se distribuyen en una cuadrícula responsiva (`grid-template-columns: repeat(auto-fit, minmax(160px, 1fr))`).

## ¿Qué variables CSS crearon?
- Colores principales: `--color-primary`, `--color-primary-light`, `--color-primary-dark`
- Colores de fondo: `--color-bg`, `--color-bg-alt`
- Colores de texto: `--color-text`, `--color-text-light`
- Espaciados: `--spacing-sm`, `--spacing-md`, `--spacing-lg`, `--spacing-xl`
- Otros: `--border-radius`, `--box-shadow`, `--transition`

## ¿Cómo implementaron el Responsive Design?
Se utilizaron **tres breakpoints** con `@media`:
- **Escritorio (>900px)**: diseño completo con dos columnas en hero y grid de 3 columnas.
- **Tablet (600px - 900px)**: el hero pasa a una columna, el grid se reduce a 2 columnas.
- **Móvil (<600px)**: el header y el nav se apilan verticalmente, los grids pasan a una columna (o dos para temas), y se ajustan tamaños de fuente y espaciados.

Además, se emplearon unidades flexibles como `%`, `vw`, `vh`, `fr`, `rem` y `auto-fit` para que los contenedores se adapten automáticamente al ancho disponible.

---

## Estrategias de SEO implementadas
1. **Título único y descriptivo** en la etiqueta `<title>`.
2. **Meta descripción** clara y atractiva (`<meta name="description">`).
3. **Jerarquía de encabezados** correcta: `h1` → `h2` → `h3`.
4. **Etiquetas semánticas** (`header`, `nav`, `main`, `section`, `article`, `footer`) para mejorar la estructura.
5. **Atributos `alt`** en todas las imágenes, describiendo su contenido.

---

## Instrucciones de uso (Git)
1. Clonar el repositorio.
2. Crear y cambiar a la rama `dev`:  
   `git checkout -b dev`
3. Realizar los cambios y commits en `dev`.
4. Subir `dev` al remoto:  
   `git push origin dev`
5. Crear un Pull Request desde `dev` hacia `main` en GitHub.
6. Asignar revisores y, tras la aprobación, fusionar.

---

## Nota
Este proyecto es puramente educativo y forma parte del Trabajo Final de la Tecnicatura Universitaria en Programación.   