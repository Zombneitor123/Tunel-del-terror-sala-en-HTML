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

### Reto 5: Los retratos y las imágenes accesibles (Miembro 4)
- **Pregunta de investigación:** ¿Para qué sirven `alt`, `width`, `<figure>` y `<figcaption>` al incluir imágenes en HTML?
- **Fuentes consultadas:** [MDN · Elemento `<img>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/img) y [MDN · Elemento `<figure>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/figure).
- **Prueba realizada:** Se añadieron las imágenes locales `img/retrato.jpg` y `img/espejo.jpg` con sus descripciones alternativas y anchos indicados; se agrupó el espejo y su pie de foto en `<figure>`.
- **Decisión razonada:** El texto alternativo describe la información visual a quienes no pueden verla o cuando el archivo no carga. `width` fija el ancho en píxeles sin unidad, y `<figure>` con `<figcaption>` asocia semánticamente el espejo con su pie. Se eligieron imágenes de Wikimedia Commons con licencias abiertas y se registraron sus fuentes y licencias arriba.
