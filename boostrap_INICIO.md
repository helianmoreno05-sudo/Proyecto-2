## 1. ¿Cómo se instala? (El enlace CDN)

La forma más fácil de usar Bootstrap (sin descargar nada) es copiar y pegar su enlace de Internet (CDN) en la cabeza ( `<head>`) de su archivo HTML.

Con solo agregar las clases `text-primary`(texto azul) y `text-center`(centrado), el texto ya está estilizado sin que hayas tocado una sola hoja de estilos.

2. El sistema de cuadrícula (El Grid)

El concepto más importante de Bootstrap es cómo organizar el contenido. Imagina que tu pantalla está dividida verticalmente en **12 columnas invisibles** . Tú decides cuántas columnas ocupan cada elemento.

Para usar este sistema, siempre debes anidar tres elementos en este orden estricto:

1. Un contenedor ( `.container`o `.container-fluid`)
    
2. Una fila ( `.row`)
    
3. Las columnas ( `.col-`)




## 3. Componentes listos para usar

Bootstrap trae piezas de interfaz completamente diseñadas. No tienes que programar los bordes redondeados, las sombras o los cambios de color al pasar el ratón.

Por ejemplo, para crear un botón moderno, solo necesitas dos clases:

- `btn`: Le dice a Bootstrap "esto es un botón y necesita forma de botón".
    
- `btn-primary`: Le da el color principal (azul por defecto).



button class="btn btn-success">Guardar</button>
button class="btn btn-danger">Eliminar</button>


**Consejo clave:** Los colores en Bootstrap tienen nombres semánticos. `primary`(principal/azul), `success`(éxito/verde), `danger`(peligro/rojo), `warning`(advertencia/amarillo). Estos nombres se usan para botones, textos, fondos y alertas.


## 4. Clases de utilidad (Espaciado)

Bootstrap tiene clases rápidas para agregar márgenes (espacio hacia afuera) y padding (espacio hacia adentro) sin usar CSS.

- **m** = margen (margen)
    
- **p** = padding (relleno interno)
    
- **t** = arriba (arriba), **b** = abajo (abajo), **s** = inicio (izquierda), **e** = final (derecha)
    

Los tamaños van del 0 al 5.

- `mt-3`: Margen arriba de tamaño 3.
    
- `p-5`: Relleno interno en todos los lados de tamaño máximo.
div class="bg-dark text-white p-4 mt-3"> Caja oscura con texto blanco, mucho relleno interno y separada del elemento de arriba. </div>
[[BOOTSTRAP_CONTENEDORES]]

[[BOOTSTRAP_COLUMNAS]]


[[BOOTSTRAP_BREAKPOINTS]]   LOS BREAKPOINTS FUNCIONAN PARA TODO EN BOOTSTRAP

[[BOOTSTRAP_ESPACIADO_MARGIN_PADDING_GAP]]
