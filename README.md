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

- **Fotografías y recursos gráficos**: Imágenes con licencia libre procedentes de [Pixabay](https://pixabay.com).
- **Validación de código**: W3C Markup Validation Service ([validator.w3.org](https://validator.w3.org/)).

---

## 📓 Diario de Investigación

### Reto 1: Esqueleto semántico y estructura del documento (Miembro 1 · El Arquitecto)
- **Pregunta de investigación:** ¿Por qué es fundamental estructurar un documento web usando etiquetas semánticas de HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`) en lugar de usar contenedores genéricos como `<div>`? ¿Qué beneficios aporta a la accesibilidad y a los navegadores?
- **Fuente oficial consultada:** [MDN Web Docs · HTML5 Semantics](https://developer.mozilla.org/es/docs/Glossary/Semantics) y [MDN Web Docs · Document and website structure](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure).
- **Prueba realizada en `pruebas.html`:** Se diseñó una estructura alternativa con `<div id="cabecera">` y `<div id="cuerpo">` y se comparó con el uso de `<header>`, `<main>` y `<footer>`. Comprobamos cómo las herramientas de accesibilidad y lectores de pantalla identifican hitos (landmarks) de navegación directa con las etiquetas semánticas, mientras que con `<div>` carecen de contexto sobre la función del contenido.
- **Decisión razonada:** Descartar totalmente el uso de `<div>` para la maquetación. Se establece el esqueleto semántico con `<!DOCTYPE html>`, `<html lang="es">`, `<meta charset="UTF-8">`, `<header>`, `<main data-propietario="Zombneitor123">` y `<footer>`, asegurando una página accesible, limpia y alineada con los estándares de HTML5.

---

*(Las siguientes entradas del diario serán incorporadas por los miembros correspondientes en sus respectivos pasos).*
