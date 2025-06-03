# 📘 Módulo 2: Estructura de un Documento HTML

## ❓ ¿Qué es la estructura de un documento HTML?

Un documento HTML está organizado en una estructura jerárquica que sigue un orden lógico y semántico. Esta estructura permite que los navegadores y otras herramientas comprendan e interpreten correctamente el contenido de la página.

La estructura está compuesta por tres grandes bloques:

1. **Doctype**: Indica al navegador qué versión de HTML se está utilizando.
2. **`<html>`**: Raíz del documento, contiene todo el contenido visible y no visible.
3. **`<head>` y `<body>`**: Partes principales del documento.

---

## ✅ Partes principales de un documento HTML

| Sección             | Descripción                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `<!DOCTYPE html>`   | Declara que se usará HTML5                                                  |
| `<html lang="es">` | Elemento raíz, contiene todo el contenido del documento                     |
| `<head>`            | Información no visible: metadatos, título, enlaces a estilos y scripts      |
| `<body>`            | Contenido visible que el navegador mostrará al usuario                      |

---

## 🧠 Ejemplo de estructura completa

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo estructurado</title>
  <link rel="stylesheet" href="estilos.css">
</head>
<body>
  <header>
    <h1>Mi sitio web</h1>
  </header>

  <main>
    <section>
      <h2>Sobre mí</h2>
      <p>Este es un párrafo sobre mí.</p>
    </section>
  </main>

  <footer>
    <p>© 2025 Mi Nombre</p>
  </footer>
</body>
</html>
```

---

## 🧰 Buenas prácticas

- Siempre incluir el `<!DOCTYPE html>` al inicio
- Usar `lang="es"` u otro idioma adecuado para accesibilidad
- Organizar el contenido en `header`, `main`, `footer`, `section`, `article`
- Mantener ordenado el código con indentación y comentarios cuando sea útil

---

## 📦 Elementos comunes en `<head>`

- `<meta charset="UTF-8">`: codificación de caracteres
- `<meta name="viewport">`: diseño responsive
- `<title>`: título de la pestaña del navegador
- `<link rel="stylesheet">`: vinculación de estilos CSS
- `<script src="...">`: inclusión de scripts

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### 📘 - [⬅️](../Modulo_1_Introduccion_a_HTML5/Modulo_1.md) Módulo 1 - Módulo 3 [➡️](../Modulo_3_Etiquetas_de_Texto_y_Formato/Modulo_3.md)

### 🏠 - [Volver al Inicio](../README.md)

