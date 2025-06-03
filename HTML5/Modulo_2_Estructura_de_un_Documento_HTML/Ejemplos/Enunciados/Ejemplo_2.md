# 🧪 Ejemplo 2: Uso de etiquetas estructurales: header, main, footer

## 🎯 Objetivo
Aprender a utilizar las etiquetas semánticas principales para organizar el contenido de una página HTML de forma clara y accesible.

## 📁 Ruta: /Modulo_2_Estructura_de_un_Documento_HTML/Ejemplos/Enunciados/Ejemplo_2.md

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ejemplo con etiquetas semánticas</title>
</head>
<body>
  <header>
    <h1>Mi Blog Personal</h1>
    <nav>
      <a href="#inicio">Inicio</a> |
      <a href="#articulos">Artículos</a> |
      <a href="#contacto">Contacto</a>
    </nav>
  </header>

  <main>
    <section id="articulos">
      <article>
        <h2>Artículo 1</h2>
        <p>Este es el contenido del primer artículo.</p>
      </article>
      <article>
        <h2>Artículo 2</h2>
        <p>Este es el contenido del segundo artículo.</p>
      </article>
    </section>
  </main>

  <footer>
    <p>© 2025 Mi Blog Personal</p>
  </footer>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
Este ejemplo muestra cómo se usan las etiquetas semánticas `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` y `<footer>` para organizar una página web de forma lógica, estructurada y accesible para usuarios y buscadores.

---

## 🧠 Conceptos aplicados
- Uso de etiquetas semánticas principales de HTML5
- Organización de contenido en secciones y artículos
- Inclusión de navegación dentro del encabezado
- Mejora de la accesibilidad y SEO

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar un `<aside>` para contenido adicional
```html
<aside>
  <h3>Sobre mí</h3>
  <p>Soy estudiante de desarrollo web.</p>
</aside>
```
📌 **¿Por qué?**: El `<aside>` permite colocar información secundaria relacionada con el contenido principal.

### ✅ 2. Cambiar los artículos por una lista de publicaciones
```html
<ul>
  <li><a href="#">Publicación 1</a></li>
  <li><a href="#">Publicación 2</a></li>
</ul>
```
📌 **¿Por qué?**: Puedes simplificar la estructura si solo estás listando enlaces a artículos.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 2](../../Modulo_2.md)

### 🏠 - [Inicio](../../../README.md)

