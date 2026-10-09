````
---
fecha: 2026-09-24
tipo: apunte-de-estudio
tecnologia: Bootstrap 5
tema: Columnas (Columns y Flexbox)
nivel: Principiante
etiquetas:
  - diseño-web
  - bootstrap
  - css
  - html
  - flexbox
---

# 🏛️ Guía Fácil: Manejo de Columnas en Bootstrap

En Bootstrap, la estructura de una página web funciona como un árbol:
1. **Contenedor (`.container`)**: La caja principal.
2. **Fila (`.row`)**: Una línea horizontal dentro de la caja.
3. **Columna (`.col`)**: Los bloques verticales dentro de la fila donde pones tu texto, fotos o botones.

> ⚠️ **Regla importante:** La rejilla de Bootstrap siempre se divide en **12 espacios imaginarios** por fila. Puedes hacer que una columna ocupe 3, 4, 6 o los 12 espacios.

---

## 📐 1. Alineación de Columnas (Alinear Arriba, Centro o Abajo)

Como Bootstrap usa tecnología *Flexbox*, podemos mover las columnas vertical y horizontalmente muy fácil.

### A. Alineación Vertical (De arriba a abajo)

Sirve cuando las columnas tienen diferentes alturas y quieres alinearlas respecto a la fila:

* **Arriba (`align-items-start`)**: Alinea todas las columnas al techo de la fila.
* **Al Centro (`align-items-center`)**: Alinea todas las columnas justo en la mitad vertical.
* **Abajo (`align-items-end`)**: Alinea todas las columnas al piso de la fila.

```html
<!-- Ejemplo: Alineadas al centro verticalmente -->
<div class="container text-center">
  <div class="row align-items-center">
    <div class="col">Columna 1</div>
    <div class="col">Columna 2</div>
    <div class="col">Columna 3</div>
  </div>
</div>
````

#### Alinear una sola columna por separado (`.align-self-*`):

Si no quieres alinear toda la fila, puedes mover una columna individual:

- `align-self-start`: Solo esta columna va arriba.
    
- `align-self-center`: Solo esta columna va al centro.
    
- `align-self-end`: Solo esta columna va abajo.
    

HTML

```
<div class="row">
  <div class="col align-self-start">Arriba</div>
  <div class="col align-self-center">Centro</div>
  <div class="col align-self-end">Abajo</div>
</div>
```

### B. Alineación Horizontal (De izquierda a derecha)

Sirve para distribuir las columnas a lo largo de la fila usando `justify-content-*`:

- **`justify-content-start`**: Pega las columnas a la izquierda.
    
- **`justify-content-center`**: Pone las columnas en el centro horizontal.
    
- **`justify-content-end`**: Pega las columnas a la derecha.
    
- **`justify-content-around`**: Deja un espacio uniforme alrededor de cada columna.
    
- **`justify-content-between`**: Pega la primera columna a la izquierda, la última a la derecha y distribuye el resto.
    
- **`justify-content-evenly`**: Deja el mismo espacio exacto entre todas las columnas.
    

HTML

```
<div class="row justify-content-center">
  <div class="col-4">Columna Centrada de 4 espacios</div>
  <div class="col-4">Columna Centrada de 4 espacios</div>
</div>
```

## 🔄 2. Salto de Línea en Columnas (Wrapping y Breaks)

### ¿Qué pasa si sumas más de 12 espacios?

Si pones columnas que superan los 12 espacios en una sola fila, la columna extra **se bajará automáticamente a una nueva línea**.

- _Ejemplo:_ Si pones una columna de 9 espacios (`.col-9`) y otra de 4 (`.col-4`), como `9 + 4 = 13` (mayor que 12), la segunda columna se baja sola.
    

HTML

```
<div class="row">
  <div class="col-9">Ocupa 9 espacios</div>
  <div class="col-4">Se pasa de 12, así que cae a la siguiente línea</div>
</div>
```

### Forzar un salto de línea (`<div class="w-100"></div>`)

Si quieres obligar a que las siguientes columnas se bajen de renglón sin cambiar la suma de 12, insertas una etiqueta vacía con la clase `w-100` (ancho 100%):

HTML

```
<div class="row">
  <div class="col-6">Fila 1 - Columna A</div>
  <div class="col-6">Fila 1 - Columna B</div>

  <!-- Esto fuerza el salto de línea -->
  <div class="w-100"></div>

  <div class="col-6">Fila 2 - Columna A</div>
  <div class="col-6">Fila 2 - Columna B</div>
</div>
```

## 🔀 3. Reordenar Columnas (Cambiar el Orden Visual)

Puedes hacer que una columna aparezca primero en la pantalla aunque en tu código HTML esté escrita al final.

- **`.order-1` hasta `.order-5`**: Define el número de posición.
    
- **`.order-first`**: Pasa la columna al primer lugar.
    
- **`.order-last`**: Mueve la columna al último lugar.
    

HTML

```
<div class="row">
  <div class="col order-last">Escrito primero, pero se verá al FINAL</div>
  <div class="col">Escrito segundo, se verá en el MEDIO</div>
  <div class="col order-first">Escrito al final, pero se verá de PRIMERO</div>
</div>
```

## ➡️ 4. Empujar o Desplazar Columnas (Offsets y Margenes)

Si no quieres pegarle una columna al lado a otra, puedes dejar espacios vacíos (huecos) a la izquierda de dos formas:

### A. Con Clases Offset (`.offset-*`)

La clase `.offset-md-4` le añade un margen a la izquierda equivalente a **4 columnas vacías**.

HTML

```
<div class="row">
  <div class="col-md-4">Columna 1</div>
  <!-- Deja 4 espacios en blanco a la izquierda y luego coloca la columna de 4 -->
  <div class="col-md-4 offset-md-4">Columna 2 (Empujada)</div>
</div>
```

### B. Con Márgenes de Flexbox (`.ms-auto` / `.me-auto`)

- **`ms-auto` (Margin Start Auto)**: Empuja la columna lo más a la derecha posible.
    
- **`me-auto` (Margin End Auto)**: Empuja a las columnas vecinas hacia la derecha.
    

HTML

```
<div class="row">
  <div class="col-md-4">Izquierda</div>
  <div class="col-md-4 ms-auto">Pega esta columna totalmente a la DERECHA</div>
</div>
```

## 🖼️ 5. Usar Columnas Sueltas (Fuera de una Fila)

Puedes ponerle clases de columna como `col-3` o `col-sm-9` a elementos sueltos (sin meterlos dentro de un `<div class="row">`) para darle un ancho fijo respecto a la pantalla:

HTML

```
<!-- Ocupará el 25% de la pantalla (3 de 12 espacios) -->
<div class="col-3 p-3">
  Caja del 25% de ancho
</div>
```

### Texto flotante alrededor de una imagen (`clearfix`)

Si quieres que una imagen ocupe media pantalla y el texto la envuelva bonito por un lado, usas `clearfix` y clases como `float-md-end`:

HTML

```
<div class="clearfix">
  <!-- Imagen que ocupa 6 espacios y flota a la derecha en pantallas medianas -->
  <img src="foto.jpg" class="col-md-6 float-md-end mb-3 ms-md-3" alt="Foto">

  <p>Este es el texto que va a rodear suavemente a la imagen por la izquierda...</p>
</div>
```

![[Pasted image 20260924222158.png]]

se puede jugar con los tamaños pero siempre tiene k dar 12 la suma total

si hay 13 va a haber un salto de linea


[[BOOTSTRAP_BREAKPOINTS]]