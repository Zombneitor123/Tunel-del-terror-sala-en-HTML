# 👻 Túnel del Terror · Sala 4: El espejo
> **Proyecto:** Túnel del terror «El aula maldita»  
> **Módulo:** Lenguaje de Marcas y Sistemas de Gestión de Información (LMSGI) · 1.º Curso  
> **Temas:** Tema 3 (Estructura semántica) y Tema 4 (Etiquetas de texto, enlaces, listas y contenido incrustado)

---

## 📌 Datos de la Sala

| Parámetro | Detalle |
| :--- | :--- |
| **Número de Sala** | Sala 4 |
| **Ambientación** | «Museo del retrato maldito» |
| **Objeto / Enigma** | «La dama del espejo» (cuadro que sigue con la mirada al visitante) |
| **Pantalla de 1.º (HTML)** | Ficha técnica del cuadro con número en romanos que revela la pista |
| **Pantalla de 2.º (JavaFX)** | Pantalla negra interactiva («mírate…»); susto controlado al introducir el número |
| **Pista acordada para 2.º** | **`13`** |
| **Letra que entrega la sala** | **`D`** (aporta para formar la palabra final `MIEDO`) |
| **Autor (GitHub)** | `Zombneitor123` |
| **Repositorio** | [https://github.com/Zombneitor123/Tunel-del-terror-sala-en-HTML.git](https://github.com/Zombneitor123/Tunel-del-terror-sala-en-HTML.git) |

---

## 📖 Historia de la Sala

En la sala más fría y lúgubre del museo cuelga el cuadro de *«La dama del espejo»*. Nadie conoce su procedencia exacta ni al autor que plasmó unos ojos tan inquietantes y abiertos. Cuentan los vigilantes nocturnos que la figura cambia sutilmente de postura con el paso de las horas y que su mueca amaneció alterada. 

Para poder avanzar en el recorrido y obtener la letra maldita en el terminal de 2.º, los visitantes deben inspeccionar el documento reservado de la galería: una ficha técnica donde el número de inventario oculta la clave para aplacar al reflejo del espejo.

---

## 📂 Estructura del Proyecto

```text
tunel-del-terror-sala-en-html/
├── css/
│   └── terror.css              # Hoja de estilos con la ambientación visual
├── docs/
│   └── validacion.png          # Captura de validación sin errores W3C (Paso 9)
├── img/
│   ├── retrato.jpg             # Retrato antiguo de la dama (Paso 4)
│   └── espejo.jpg              # Espejo ovalado empañado (Paso 4)
├── index.html                  # Página principal de la Sala 4
├── pergamino.html              # Documento secreto incrustado con la pista
├── pruebas.html                # Banco de pruebas para investigación de etiquetas
└── README.md                   # Documentación, créditos y Diario de Investigación
```

---

## 🖼️ Capturas y Créditos

- **Retrato antiguo**: *Portrait of a Young Woman*, de Johannes Vermeer, dominio público. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Vermeer-Portrait_of_a_Young_Woman.jpg).
- **Espejo ovalado**: fotografía de rulenumberone2, licencia [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/). [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Arnaud%27s_restaurant,_New_Orleans,_interior_November_2013_-_Mirror.jpg).
- **Validación de código**: W3C Markup Validation Service ([validator.w3.org](https://validator.w3.org/)).

---

## 📓 Diario de Investigación

### Reto 1: Esqueleto semántico y estructura del documento (Miembro 1 · El Arquitecto)
- **Pregunta de investigación:** ¿Por qué es fundamental estructurar un documento web usando etiquetas semánticas de HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`) en lugar de usar contenedores genéricos como `<div>`? ¿Qué beneficios aporta a la accesibilidad y a los navegadores?
- **Fuente oficial consultada:** [MDN Web Docs · HTML5 Semantics](https://developer.mozilla.org/es/docs/Glossary/Semantics) y [MDN Web Docs · Document and website structure](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure).
- **Prueba realizada en `pruebas.html`:** Se diseñó una estructura alternativa con `<div id="cabecera">` y `<div id="cuerpo">` y se comparó con el uso de `<header>`, `<main>` y `<footer>`. Comprobamos cómo las herramientas de accesibilidad y lectores de pantalla identifican hitos (landmarks) de navegación directa con las etiquetas semánticas, mientras que con `<div>` carecen de contexto sobre la función del contenido.
- **Decisión razonada:** Descartar totalmente el uso de `<div>` para la maquetación. Se establece el esqueleto semántico con `<!DOCTYPE html>`, `<html lang="es">`, `<meta charset="UTF-8">`, `<header>`, `<main data-propietario="Zombneitor123">` y `<footer>`, asegurando una página accesible, limpia y alineada con los estándares de HTML5.

### Reto 2: La voz del narrador y etiquetas de texto semánticas (Miembro 2 · El Guionista)
- **Pregunta de investigación:** ¿Qué diferencia semántica hay entre destacar importancia (`<strong>`) y poner negrita visual (`<b>`)? ¿Y entre dar énfasis al leerlo (`<em>`) y poner cursiva tipográfica (`<i>`)? ¿Con qué etiquetas representamos contenido tachado o invalidado, aclaraciones en letra pequeña y subíndices? ¿Para qué sirve un comentario HTML si no lo ve el visitante?
- **Fuente oficial consultada:** [MDN Web Docs · Elemento strong](https://developer.mozilla.org/es/docs/Web/HTML/Element/strong), [MDN Web Docs · Elemento em](https://developer.mozilla.org/es/docs/Web/HTML/Element/em), [MDN Web Docs · Elemento mark](https://developer.mozilla.org/es/docs/Web/HTML/Element/mark), y [MDN Web Docs · Elementos de texto en línea](https://developer.mozilla.org/es/docs/Web/HTML/Element#contenido_de_texto_en_l%C3%ADnea).
- **Prueba realizada en `pruebas.html`:** Se compararon las parejas visuales/semánticas (`<b>` vs `<strong>`, `<i>` vs `<em>`). Se verificó que los lectores de pantalla varían la entonación y volumen con `<strong>` y `<em>`, mientras que con `<b>` e `<i>` ignoran cualquier intención de énfasis. Asimismo, se comprobó el renderizado nativo de `<del>`, `<sub>`, `<mark>` y `<small>`, así como la completa invisibilidad visual de los comentarios `<!-- -->`.
- **Decisión razonada:** En la sección `#historia` de `index.html`, se aplican exclusivamente etiquetas semánticas:
  - `<strong>` para destacar el nombre de la obra: *«La dama del espejo»* (máxima importancia).
  - `<br>` para separar oraciones manteniendo el párrafo temático.
  - `<em>` para acentuar el comportamiento anómalo: *«cambia de postura»*.
  - `<del>` para indicar la corrección del testimonio sobre la boca de la dama: *«cerrada»*.
  - `<sub>` para la fórmula química *H<sub>2</sub>O*.
  - `<mark>` para la advertencia prioritaria: *«No le sostengáis la mirada.»*.
  - `<small>` para la cláusula de descargo de responsabilidad del museo.
  - Comentario `<!-- El número está en la ficha técnica (pergamino.html) -->` para dejar una pista interna para el equipo técnico sin alterar la inmersión del visitante.

### Reto 4: Las normas para sobrevivir y la lista anidada (Miembro 3)
- **Pregunta de investigación:** ¿Cuándo conviene usar una lista ordenada y cuándo una no ordenada? ¿Dónde debe colocarse una lista anidada para que el HTML sea válido?
- **Fuentes consultadas:** [MDN · Elemento `<ol>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/ol) y [MDN · Elemento `<ul>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/ul).
- **Prueba realizada en `pruebas.html`:** Se creó una lista de pasos con `<ol>` y, dentro del segundo `<li>`, una lista de normas con `<ul>`. También se probó la estructura incorrecta colocando `<ul>` directamente dentro de `<ol>`. El validador W3C indicó: `Element “ul” not allowed as child of element “ol” in this context. (Suppressing further errors from this subtree.)`.
- **Decisión razonada:** En `index.html`, las normas que forman una secuencia usan `<ol>`. Las prohibiciones del segundo paso usan `<ul>` porque no tienen un orden obligatorio. La lista anidada se escribe dentro del `<li>` «Delante del cuadro:», no como hija directa de `<ol>`, para respetar el modelo de contenido HTML.

*(Las entradas de los demás retos serán incorporadas por los miembros correspondientes en sus respectivos pasos).*

### Reto 5: Los retratos y las imágenes accesibles
- **Pregunta de investigación:** ¿Para qué sirve el texto alternativo (`alt`) si la imagen ya se ve y quién lo utiliza? ¿Qué ocurre si la ruta de la imagen (`src`) es errónea? ¿Qué aporta agrupar una imagen y su pie de foto con `<figure>` y `<figcaption>` frente a poner un `<p>` suelto debajo? ¿Por qué el atributo `width` se escribe sin unidades?
- **Fuente oficial consultada:** [MDN Web Docs · Elemento `<img>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/img) y [MDN Web Docs · Elemento `<figure>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/figure).
- **Prueba realizada en `pruebas.html`:** Se insertaron las imágenes `img/retrato.jpg` y `img/espejo.jpg` y se provocó deliberadamente un fallo cambiando la ruta a `img/archivo-inexistente.jpg`. Al fallar la ruta, el navegador muestra un icono de imagen rota acompañado del texto escrito en `alt`. Además, se comparó una imagen seguida de un párrafo normal frente a una envuelta en `<figure>` con `<figcaption>`.
- **Decisión razonada:** 
  - Se incluye un atributo `alt` descriptivo en ambas imágenes para garantizar la accesibilidad a personas que usan lectores de pantalla y como respaldo textual si falla la carga del archivo.
  - Se escribe `width="400"` y `width="450"` como números enteros sin unidades (`px` ni `%`) porque la especificación del estándar HTML5 define que este atributo expresa siempre píxeles CSS de forma nativa (añadir `px` invalida el código en el validador W3C).
  - Para la primera imagen (`retrato.jpg`) se usa `<img>` directamente, mientras que para la segunda (`espejo.jpg`) se emplea `<figure>` y `<figcaption>` para vincular semánticamente el espejo con su pie de foto («El espejo que cuelga frente al cuadro.»).

### Reto 6: El documento secreto (`pergamino.html`) y su incrustación con `<iframe>`
- **Pregunta de investigación:** ¿Qué partes del esqueleto HTML se mantienen en una segunda página y cuáles cambian? ¿Cómo se enlaza la misma hoja de estilos y para qué sirve el atributo global `class`? ¿Qué etiqueta permite mostrar una página web dentro de otra, qué atributos controlan su tamaño y por qué es obligatorio darle un nombre accesible con `title`?
- **Fuente oficial consultada:** [MDN Web Docs · Atributos globales (`class`)](https://developer.mozilla.org/es/docs/Web/HTML/Global_attributes/class), [MDN Web Docs · Elemento `<abbr>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/abbr) y [MDN Web Docs · Elemento `<iframe>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/iframe).
- **Prueba realizada en `pruebas.html`:** Se creó el documento `pergamino.html` reutilizando la estructura base (`<!DOCTYPE html>`, `<html lang="es">`, `<head>` con `<meta>` y `<link rel="stylesheet" href="css/terror.css">`), cambiando únicamente el `<title>` y aplicando `<body class="pergamino">`. Posteriormente, se probó su incrustación mediante `<iframe src="pergamino.html">` verificando el comportamiento de los atributos `title`, `width` y `height`.
- **Decisión razonada:** 
  - En `pergamino.html` se usa el atributo global `class="pergamino"` en el `<body>` para que la hoja `css/terror.css` aplique los estilos de papel antiguo y tipografía marrón sin necesidad de crear otro archivo CSS.
  - La pista (`13`) se esconde de forma semántica usando `<abbr title="13">XIII</abbr>`, permitiendo que aparezca en un *tooltip* al pasar el ratón por encima de los números romanos.
  - En `index.html`, dentro de `<section id="pergamino">`, se incrusta el documento con `<iframe src="pergamino.html" title="Ficha técnica del cuadro" width="600" height="320"></iframe>`. El atributo `title` es obligatorio por accesibilidad: sin él, un usuario con lector de pantalla solo escucharía «marco» o el nombre del archivo sin saber qué contiene ni si debe entrar a inspeccionarlo.

### Reto 7: La pista escondida
- **Pregunta:** ¿Cómo escondo el número 13 para que no se vea a simple vista pero se pueda encontrar?
- **Fuente:** [MDN · abbr](https://developer.mozilla.org/es/docs/Web/HTML/Element/abbr) y [MDN · details](https://developer.mozilla.org/es/docs/Web/HTML/Element/details).
- **Prueba:** En `pruebas.html` probé varias formas:
  - `<abbr title="13">XIII</abbr>`: no se ve el 13 hasta que pasas el ratón por encima.
  - `<details>` y `<summary>`: el 13 sale al pulsar el desplegable, pero es demasiado fácil.
  - `<mark>`: resalta las cifras, pero se nota mucho.
  - Comentario `<!-- -->`: no se ve en la página, así que el visitante nunca lo encontraría.
- **Decisión:** Elijo `<abbr>` porque esconde el número pero se encuentra fácil pasando el ratón, y encaja con la historia de los números romanos. Es el número que espera el programa de 2.º.

### Reto 8: Validación W3C
- **Pregunta:** ¿Mi HTML está bien escrito? ¿Qué significan los errores del validador y por qué salen?
- **Fuente:** [Validador W3C](https://validator.w3.org/) y [MDN · Depurar HTML](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML).
- **Prueba:** Subí `index.html`, `pergamino.html` y `pruebas.html` y los tres salieron sin errores. Para ver cómo funciona, pegué en el validador (text input) un código con fallos a propósito y me dio dos errores:
  - `Element ul not allowed as child of element ol`: dentro de un `<ol>` solo pueden ir `<li>`, así que la lista de dentro tiene que ir dentro de un `<li>`.
  - `An img element must have an alt attribute`: la imagen no tenía `alt`, y es obligatorio.
- **Decisión:** Las páginas de la sala pasan sin errores (captura en `docs/validacion.png`). El navegador enseñaba bien el código con fallos, así que valido siempre antes de entregar para asegurarme de que está bien escrito.
  