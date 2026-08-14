# Contexto del proyecto — Prototipo e-commerce

Prototipo visual y funcional de tienda online para una marca ficticia de ropa
con sede en Francia. Proyecto académico de 4Geeks Academy (Ingeniería de IA).

Trabajo individual. Se aplica el flujo completo de ramas y pull requests que
exige el enunciado; la revisión cruzada entre dos personas no aplica.

---

## Restricciones — NO negociables

Estas reglas vienen del enunciado del proyecto. No las contradigas nunca,
aunque exista una forma "mejor" de hacer las cosas.

sección de restricciones

- **Solo HTML y Tailwind CSS.** Prohibido React, Vue, Angular, Next, Astro
  o cualquier framework de JavaScript.
- **Tailwind CSS v4 compilado con CLI** (`@tailwindcss/cli`).
  **NO usar Play CDN** — la documentación oficial de Tailwind lo desaconseja
  para producción, y este proyecto se despliega en una URL pública que será
  medida con PageSpeed Insights.
- El CSS compilado vive en `./dist/output.css` y se enlaza con `<link>`.
  El archivo fuente es `./src/input.css` y contiene una sola línea:
  `@import "tailwindcss";`
- **JavaScript:** solo si es imprescindible. Vanilla, mínimo, sin librerías.
  Este es un prototipo visual, no una tienda funcional.
- **No inventes datos de contacto reales.** Direcciones, teléfonos y emails
  son ficticios y deben parecerlo.
- **No uses marcas reales** (Chanel, Lacoste, Zara...) ni sus logos.
  La marca es ficticia.
  - La marca se llama **Verline**. Escríbelo siempre exactamente así, sin
  variantes ni traducciones. Aparece en los cinco `<title>`, en el logo de
  la navbar, en el footer y en el JSON-LD de `Organization`.
 
  ## Paleta

- Neutros: rampa `stone` de Tailwind. Texto principal `stone-900`,
  secundario `stone-600`, bordes `stone-200`, fondo blanco o `stone-50`.
- Acento: `vino` (#6B2737), hover `vino-oscuro` (#52202C). Definido en
  `src/input.css` con `@theme`.
- No introduzcas otros colores. Nada de azules, verdes ni grises de otras
  rampas.

---

## Estructura de archivos

```
index.html          → Home
catalogo.html       → Catálogo
producto.html       → Vista de producto
carrito.html        → Carrito
pago.html           → Checkout
src/input.css       → fuente de Tailwind
dist/output.css     → CSS compilado (SÍ se commitea)
node_modules/       → ignorado en .gitignore
```

`index.html` mantiene ese nombre en inglés porque GitHub Pages lo requiere
como punto de entrada. El resto va en español, **sin tildes ni eñes** en
nombres de archivo (las tildes en URLs se codifican y rompen enlaces).

La **navbar y el footer son idénticos en las cinco vistas**. Al modificar
uno, hay que replicar el cambio en los cinco archivos.

---

## Contenido mínimo por vista

**Home (`index.html`)**
- Navbar: logo, barra de búsqueda, menú de cuenta de usuario
- Hero destacando campaña o productos especiales
- Dos listados horizontales de cards: "Nuevos lanzamientos" y "Más vendidos"
- Footer: categorías (calzado, camisas, pantalones, accesorios),
  legal (términos, privacidad, sobre la marca), contacto

**Catálogo (`catalogo.html`)**
- Barra de filtros antes del listado: por categoría y por talla
- Rejilla 4×5 (20 productos de referencia)

**Producto (`producto.html`)**
- Dos columnas: imagen a la izquierda (~50% del ancho), datos a la derecha
- Datos: nombre, código/referencia, talla, precio, selector de cantidad,
  botón "Agregar al carrito"
- Debajo: sección de descripción con materiales y uso recomendado

**Carrito (`carrito.html`)**
- Vista completa de página, NO panel lateral
- 3 productos de ejemplo con miniatura, precio unitario, cantidad, total
- Cuadro de totalización: subtotal, impuestos, total, botón "Comprar"

**Checkout (`pago.html`)**
- Flujo de 3 pasos: (1) datos personales, (2) dirección de entrega,
  (3) pago con tarjeta

---

## Criterios de evaluación

- **HTML semántico:** `<header>`, `<nav>`, `<main>`, `<section>`, `<form>`,
  `<footer>`. Landmarks correctos en todas las vistas. Un solo `<h1>` por
  página, jerarquía de encabezados sin saltos.
- **Tailwind:** clases utility coherentes, breakpoints responsivos
  (`sm:`, `md:`, `lg:`). Sin frameworks ajenos al enunciado.
- **Responsive:** las cinco vistas usables en móvil, tablet y escritorio.
  Sin layout roto ni scroll horizontal en móvil.
- **Schema.org (JSON-LD):** `Organization` en la home, `Product` en la vista
  de producto.
- **Accesibilidad:** todas las imágenes con `alt` descriptivo, todos los
  inputs con `<label>` asociado. Cuenta para SEO y para PageSpeed.
- **PageSpeed Insights:** mínimo 80 puntos en la URL pública,
  idealmente más de 90.

---

## Flujo de Git

- Una rama por vista: `feature/inicio`, `feature/catalogo`,
  `feature/producto`, `feature/carrito`, `feature/pago`
- Una pull request por cada rama, con descripción de lo que incluye
- `git pull origin main` antes de abrir la PR
- Commits frecuentes con mensajes claros y en español
  (ej. "Añadir navbar y hero al inicio")
- Un cambio lógico por commit
- Nunca `force-push`
- No trabajar de forma prolongada directamente en `main`

---

## Cómo trabajar conmigo

- Explica cada bloque antes o después de escribirlo — no vuelques código
  sin contexto.
- Avanza por bloques, no páginas enteras de una vez.
- Si algo del enunciado es ambiguo o contradictorio, dilo en lugar de
  asumir.
- Si no estás seguro de un dato, márcalo como incierto. No inventes
  URLs, nombres de paquetes ni cifras.

---

## Fuente autoritativa

El enunciado original y completo está en `docs/briefing.md`. Ante cualquier
duda, ambigüedad o contradicción, **ese archivo manda sobre este**. Este
documento es un resumen operativo y puede contener errores de síntesis.
