---
fecha: 2026-09-24
tipo: apunte-de-estudio
tecnologia: Bootstrap 5
tema: Contenedores (Containers)
nivel: Principiante
etiquetas:
  - diseño-web
  - bootstrap
  - html
  - css
---
[[BOOTSTRAP_BREAKPOINTS]]
# 📦 Guía Fácil: ¿Qué son los Contenedores en Bootstrap?

Si estás aprendiendo a crear páginas web con **Bootstrap** (una herramienta que te da código prefabricado para hacer páginas web bonitas y adaptables), lo primero que debes entender son los **Contenedores** (*Containers*).

---

## 🧐 ¿Qué es un Contenedor? (Explicación Sencilla)

Imagina que un contenedor es como una **caja o marco transparente** dentro de tu página web. 

Si pones texto, imágenes o botones sueltos en una página, se van a pegar a los bordes de la pantalla y se verán desordenados en un celular o en un computador. 

El **contenedor** se encarga de:
1. **Agrupar** todo tu contenido dentro de una caja.
2. **Dejar un margen/espacio vacio** a los lados para que las cosas no queden pegadas a las orillas de la pantalla.
3. **Centrar** tu contenido automáticamente en el medio de la pantalla.

> 💡 **Regla de oro:** Casi siempre que vayas a construir una sección en Bootstrap, necesitas meterla dentro de un contenedor.

---

## 🚦 Los 3 Tipos de Contenedores que Existen

Bootstrap nos da tres formas diferentes de usar estos contenedores según lo que necesitemos:

### 1. El Contenedor Normal (`.container`)
* **¿Cómo funciona?**: Tiene un tamaño fijo que va cambiando por "saltos" según el tamaño de la pantalla.
* **¿Cuándo usarlo?**: Es el más usado. Sirve para páginas normales donde quieres que el texto y las imágenes queden centrados y alineados en medio de la pantalla.

### 2. Contenedores Responsivos (`.container-sm`, `.container-md`, etc.)
* **¿Cómo funciona?**: En pantallas pequeñas (como celulares) ocupan el **100% del ancho** de la pantalla. Pero cuando la pantalla se vuelve más grande que el tamaño que elegiste, la caja se encoge y se centra.
* **¿Cuándo usarlo?**: Cuando quieres que en celular se aproveche todo el espacio, pero en un computador o tablet se vea como una caja centrada.

### 3. El Contenedor Fluido (`.container-fluid`)
* **¿Cómo funciona?**: Ocupa **siempre el 100% del ancho** de la pantalla, sin importar si estás en un celular pequeño o en un televisor gigante.
* **¿Cuándo usarlo?**: Ideal para barras de navegación superiores (menús), mapas, o secciones donde quieres que el fondo o los elementos abarquen toda la pantalla de extremo a extremo.

---

## 📏 Pantallas y Medidas (Breakpoints)

En diseño web, las pantallas se dividen en 6 tamaños principales llamados *breakpoints* (puntos de interrupción):

* **Extra Small (xs)**: Celulares pequeños (menos de `576px` de ancho).
* **Small (sm)**: Celulares grandes o acostados (`576px` o más).
* **Medium (md)**: Tablets (`768px` o más).
* **Large (lg)**: Laptops / Portátiles (`992px` o más).
* **Extra Large (xl)**: Monitores de computador de escritorio (`1200px` o más).
* **Extra Extra Large (xxl)**: Pantallas muy grandes o televisores (`1400px` o más).

---

## 📊 Tabla Comparativa de Tamaños

Esta tabla muestra qué ancho máximo tendrá tu caja según la pantalla donde se mire:

| Clase de Contenedor | Celular Pequeño (<576px) | Celular Grande (≥576px) | Tablet (≥768px) | Laptop (≥992px) | Monitor (≥1200px) | TV / Pantalla Grande (≥1400px) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| `.container` | `100%` | `540px` | `720px` | `960px` | `1140px` | `1320px` |
| `.container-sm` | `100%` | `540px` | `720px` | `960px` | `1140px` | `1320px` |
| `.container-md` | `100%` | `100%` | `720px` | `960px` | `1140px` | `1320px` |
| `.container-lg` | `100%` | `100%` | `100%` | `960px` | `1140px` | `1320px` |
| `.container-xl` | `100%` | `100%` | `100%` | `100%` | `1140px` | `1320px` |
| `.container-xxl` | `100%` | `100%` | `100%` | `100%` | `100%` | `1320px` |
| `.container-fluid` | `100%` | `100%` | `100%` | `100%` | `100%` | `100%` |

---

## 💻 Ejemplos de Código HTML (Cómo se escribe)

Para usar un contenedor en tu HTML, simplemente creas un `<div>` y le pones la clase correspondiente:
### Ejemplo 1: Usando el contenedor normal
```html
<div class="container">
  <h1>¡Hola mundo!</h1>
  <p>Este contenido estará centrado y con margenes a los lados.</p>
</div> 
```
### Ejemplo 2: Usando contenedores adaptables por pantalla
<!-- Será 100% ancho en celulares, pero se centrará a partir de tablets (md) -->
<div class="container-md">
  <p>Contenido para mi página.</p>
</div>

<!-- Será 100% ancho hasta pantallas de laptop (lg) -->
<div class="container-lg">
  <p>Otro contenido aquí.</p>
</div>


### Ejemplo 3: Usando el contenedor fluido (100% ancho siempre)


<div class="container-fluid">
  <p>Este texto ocupará todo el ancho de la pantalla de borde a borde.</p>
</div>

## ⚙️ Para Programadores Avanzados (Uso con Sass/CSS)

_(Nota: Si apenas estás empezando, no necesitas preocuparte por esto todavía. Es solo por si en el futuro decides personalizar los estilos de Bootstrap)._

Bootstrap permite cambiar las medidas por defecto o crear tus propios contenedores usando **Sass**:

### Cambiar las medidas por defecto (`_variables.scss`):


$container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 960px,
  xl: 1140px,
  xxl: 1320px
); 



### Crear tu propio contenedor con Mixins:


// Creamos una regla propia reutilizando la lógica de Bootstrap
.mi-contenedor-especial {
  @include make-container();
}


![[Pasted image 20260924222232.png]]




