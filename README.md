# Axwi

Esta es una biblioteca minimalista de CSS/Sass para crear RWD.

## Comenzando 🚀

_Estas instrucciones te permitirán obtener el proyecto en funcionamiento en tu máquina local para propósitos de desarrollo y pruebas._

### Instalación 🔧

- Instale los archivos fuente Sass a través de npm
  ```
  npm install --save-dev axwi
  ```
  - Luego de haberlo instalado importe en su archivo de sass `@import "~axwi/axwi"`
- Cuando solo necesite incluir CSS compilado en su última versión, puede usar el CDN
  ```
  <link href="https://unpkg.com/axwi/src/css/axwi.min.css" rel="stylesheet">
  ```

### Uso 🔥

_Puedes usar las siguientes variables, clases, funciones y mixins._

1. Clases
   - `axContainer` Debe tener al menos un **axItem** como hijo directo
     - `is-full` Use esta clase si desea un **axContainer** que mida siempre el 100% de la pantalla
   - `axItem` Siempre debe ser hijo de un **axContainer**
     - `[breakpoint]-[numero]` Usar cualquier número multiplo de 5 entre 0 y 100
     - `[breakpoint]-[numerador]-[denominador]` Usa esta clase cuando quieras dividir el ancho entre 3 o 6
     - `[breakpoint]-order[numero]` Define el orden del item donde número va de 1 hasta la variable **\$max-grid-columns**
     - `axContainer` Usa esta clase para anidar contenedores e items
   - `axGrid`
     - `[breakpoint]-grid[numero]` Define las columnas que tendrá el contenedor donde número va de 1 hasta la variable **\$max-grid-columns**
     - `[breakpoint]-gridMax1fr` Define dos columnas, una con max-content y otra con 1fr
     - `[breakpoint]-gap[numero]` El número va de 0 a 4 con separaciones de .5rem, también puede usar el numero 05 para separaciones de .25rem
     - `rowsGap` Agrega una separación entre filas
     - `[breakpoint]-alignContent[Start|End|Center|Stretch|Around|Between|Evenly]` Alinea el contenido de un grid
     - `[breakpoint]-justifyContent[Start|End|Center|Stretch|Around|Between|Evenly]` Justifica el contenido de un grid
     - `[breakpoint]-alignItems[Start|End|Center|Stretch]` Alinea los hijos de un grid
     - `[breakpoint]-justifyItems[Start|End|Center|Stretch]` Justifica los hijos de un grid
   - Estas clases pueden ser aplicadas a los hijos de **axGrid**
     - `[breakpoint]-cols[numero]` Define la cantidad de columnas que ocupa un item
     - `[breakpoint]-x[numero]` Define en que columna inicia un item
     - `[breakpoint]-rows[numero]` Define la cantidad de filas que ocupa un item
     - `[breakpoint]-y[numero]` Define en que fila inicia un item
     - `[breakpoint]-order[numero]` Define el orden del item donde número va de 1 hasta la variable **\$max-grid-columns**
     - `[breakpoint]-alignSelf[Start|End|Center|Stretch]` Alinea el hijo de un grid
     - `[breakpoint]-justifySelf[Start|End|Center|Stretch]` Justifica el hijo de un grid
   - `dev` Activa el modo dev al poner esta clase en el _**body**_
   - `devHover` Activa el modo dev con hover al poner esta clase en el _**body**_
   - `flex` Convertirá en caja flexible al elemento
   - `[breakpoint]-nowrap` Aplicará nowrap a la caja flexible
   - `[breakpoint]-[numero]` Usar cualquier número multiplo de 5 entre 0 y 100
   - `[breakpoint]-m[r|b|l|t][numero]` Aplica márgenes, el número va de 0 a 10 con separaciones de .5rem, también puede usar el numero 05 para separaciones de .25rem
   - `[breakpoint]-p[t|r|b|l|x|y|xy][numero]` Aplica paddings, el número va de 0 a 10 con separaciones de .5rem, también puede usar el numero 05 para separaciones de .25rem
   - `[breakpoint]-main[Start|Center|End|Between|Around|Evenly]` Alinea horizontalmente a los elementos hijos
   - `[breakpoint]-cross[Start|Center|End|Baseline|Stretch]` Alinea verticalmente a los elementos hijos
   - `[breakpoint]-row` Define la orientación de izquierda a derecha (predeterminado)
   - `[breakpoint]-column` Define la orientación de arriba hacia abajo
   - `[breakpoint]-rowReverse` Define la orientación de derecha a izquierda
   - `[breakpoint]-columnReverse` Define la orientación de abajo hacia arriba
   - `[breakpoint]-[left|center|right]` Alineación de contenido
   - `[breakpoint]-to[Left|Center|Right]` Alineación de bloques
   - `[breakpoint]-block[Left|Center|Right]` Alinear elementos inline
   - `[breakpoint]-[static|absolute|relative|fixed|sticky]` Define la propiedad position
   - `block` Bloques pequeños como widgets, cards y separadores
   - `section` Sección grande de contenido
   - `bigSection` Igual que el anterior pero cuando se quiere dar una separación mayor
   - `cancelBlock` Cancela margin-bottom de hermano anterior **block**
   - `cancelSection` Cancela margin-bottom de hermano anterior **section**
   - `cancelBigSection` Cancela margin-bottom de hermano anterior **bigSection**
   - `from-[breakpoint]` Hará al elemento visible a partir del breakpoint
   - `to-[breakpoint]` Hará al elemento visible por debajo del breakpoint
   - `[breakpoint]-textRows[numero]` Limitará la cantidad de lineas del texto, el número va de 1 a 10
2. Variables
   1. Sass
      - `$breakpoints` Breakpoints, _valor por default:_ `(s: 0, m: 640px, lg: 1024px, xl: 1440px)`
      - `$dev` Estilos para el debug, _valor por default:_ `false`
      - `$dev-hover` Estilos para el debug al hacer hover, _valor por default:_ `false`
      - `$max-width` Ancho máximo de los contenedores, _valor por default:_ `1200px`
      - `$l-unit` Unidad básica para el layout, _valor por default:_ `.5rem`
      - `$gap` Separación entre columnas, _valor por default:_ `$l-unit * 4`
      - `$fractions` Fracciones para crear columnas, _valor por default:_ `3 6`
      - `$container` Clase para el contenedor flexbox, _valor por default:_ `axContainer`
      - `$item` Clase para los items flexbox, _valor por default:_ `axItem`
      - `$grid-container` Clase para el contenedor grid, _valor por default:_ `axGrid`
      - `$max-grid-columns` Máximo número de columnas grid, _valor por default:_ `12`
   2. Css
      - `--verticalBlockSpace` _valor por default:_ `#{$l-unit * 2}`
      - `--verticalContentSpace` _valor por default:_ `#{$l-unit * 2}`
      - `--gap` _valor por default:_ `#{$l-unit * 2}`
      - `--maxWidth` _valor por default:_ `#{$max-width}`
3. Mixins
   - `ax-container`
   - `ax-item($s,$m,$lg,$xl)` Los parámetros definen el ancho den cada breakpoint, puede usar fracciones como parámetros
   - `from($bp)` Para tamaños mayores al breakpoint (parámetro)
   - `to($bp)` Para tamaños menores al breakpoint (parámetro)
   - `from-to($bp-from, $bp-to)` Para tamaños comprendidos entre los dos parámetros
   - `bp-prefix($names, $property, $value, $concat)` Se usa para convetir cualquier clase en la nomenclatura de la biblioteca **breakpoint-name**
4. Funciones
   - `em($px)` Esta función convierte un número en px a em
   - `rem($px)` Esta función convierte un número en px a rem
   - `to-px($value)` Esta función convierte un valor en rem o em a px
   - `is-core-bp($bp)` Devuelve true si el breakpoint es parte del core
   - `is-valid-bp($bp)` Devuelve true si el breakpoint es válido (em, rem, px)
   - `get-bp($bp)` Obtiene un breakpoint del core
   - `str-capitalize($string)` Capitaliza un string
   - `str-initials($string)` Extrae las primeras letras de un string escrito en kebab-case ejemplo: hola-mundo => hm

## Despliegue 📦

1. In process...

## Licencia 📄

Este proyecto está bajo la Licencia (GPL-2.0) - mira el archivo [LICENSE](LICENSE) para detalles.
