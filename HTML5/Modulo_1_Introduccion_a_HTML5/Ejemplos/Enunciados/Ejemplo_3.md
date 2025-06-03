# 🧪 Ejemplo 3: Enlaces internos y externos

## 🎯 Objetivo
Aprender a crear enlaces que redirigen tanto a otras páginas del mismo sitio (internos) como a sitios web externos, usando la etiqueta `<a>`.

## 📁 Ruta: ./enlaces.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Ejemplo de Enlaces</title>
</head>
<body>
  <h1>Enlaces HTML</h1>

  <p>Visita nuestro <a href="nosotros.html">acerca de nosotros</a> para más información.</p>

  <p>También puedes ir a <a href="https://www.wikipedia.org" target="_blank">Wikipedia</a> para aprender más.</p>

  <p>Enlace con título emergente: <a href="contacto.html" title="Ir a la página de contacto">Contáctanos</a></p>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?

Este documento muestra cómo utilizar la etiqueta `<a>` para crear enlaces que apuntan a:
- Otras páginas del mismo sitio (`nosotros.html`, `contacto.html`)
- Páginas externas (`https://www.wikipedia.org`)

También se demuestra cómo abrir un enlace en una nueva pestaña (`target="_blank"`) y usar el atributo `title` para mostrar una ayuda emergente al pasar el mouse.

---

## 🧠 Conceptos aplicados

- Etiqueta `<a>` con atributo `href` para definir la dirección
- Enlaces internos vs externos
- Uso de `target="_blank"` para abrir en nueva pestaña
- Atributo `title` para accesibilidad y experiencia de usuario

---

## 💡 Variaciones sugeridas

### ✅ 1. Enlace que abre una dirección de correo electrónico
```html
<a href="mailto:contacto@ejemplo.com">Envíanos un correo</a>
```
📌 **¿Por qué?**: Facilita el contacto directo desde la web.

### ✅ 2. Enlace que apunta a una sección dentro de la misma página
```html
<a href="#seccion">Ir a la sección</a>
...
<h2 id="seccion">Sección de destino</h2>
```
📌 **¿Por qué?**: Útil para páginas largas con navegación interna.

### ✅ 3. Descargar un archivo directamente
```html
<a href="archivo.pdf" download>Descargar PDF</a>
```
📌 **¿Por qué?**: Ofrece contenido descargable como recursos o manuales.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Crea el archivo `enlaces.html` con el código anterior.
2. Crea archivos vacíos llamados `nosotros.html` y `contacto.html` en la misma carpeta.
3. Abre `enlaces.html` en el navegador.
4. Verifica que los enlaces internos funcionen y que Wikipedia se abra en otra pestaña.
5. Pasa el mouse sobre los enlaces para ver los títulos emergentes.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 1](../../Modulo_1.md)

### 🏠 - [Inicio](../../../README.md)

