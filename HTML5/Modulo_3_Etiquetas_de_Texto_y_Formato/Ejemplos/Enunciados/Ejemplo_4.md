# 🧪 Ejemplo 4: Citas, abreviaciones y definiciones en HTML

## 🎯 Objetivo
Explorar el uso de etiquetas como `<blockquote>`, `<q>`, `<abbr>`, `<cite>` y `<dfn>` para incorporar contenido semántico relacionado con citas, referencias y definiciones.

## 📁 Ruta: ejemplos/Modulo_3/Ejemplo_4.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Citas y Definiciones</title>
</head>
<body>
  <p><abbr title="Organización Mundial de la Salud">OMS</abbr> es una agencia de las Naciones Unidas especializada en gestionar políticas de prevención, promoción e intervención en salud a nivel mundial.</p>

  <p><dfn>HTML</dfn> es el lenguaje de marcado que se utiliza para estructurar páginas web.</p>

  <blockquote cite="https://es.wikipedia.org/wiki/HTML">
    HTML es el lenguaje con el que se definen los contenidos de una página web.
  </blockquote>

  <p>Como dijo Tim Berners-Lee: <q>La Web es para todos</q>.</p>

  <p>Referencia: <cite>HTML5 Specification</cite></p>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo muestra cómo enriquecer un documento con significado usando etiquetas semánticas específicas para citas largas, citas en línea, definiciones, abreviaciones y fuentes de referencia.

---

## 🧠 Conceptos aplicados

- Uso de `<abbr>` para mostrar el significado completo de una abreviación al pasar el cursor
- Inclusión de citas largas con `<blockquote>` y atributo `cite`
- Citas en línea con `<q>`
- Inclusión de definiciones con `<dfn>`
- Referencias y fuentes con `<cite>`

---

## 💡 Variaciones sugeridas

### ✅ Citar varios autores y combinar etiquetas

```html
<p>Según <cite>W3C</cite>, <abbr title="HyperText Markup Language">HTML</abbr> es fundamental para la Web.</p>
<blockquote>
  <p>HTML describe la estructura de las páginas usando elementos como títulos, párrafos y listas.</p>
</blockquote>
```
📌 **¿Por qué?**: Mejora la accesibilidad, usabilidad y comprensión del contenido.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Abre el archivo en el navegador.
2. Coloca el cursor sobre la abreviación para ver el título emergente.
3. Verifica que las citas estén correctamente formateadas.
4. Usa herramientas de inspección para confirmar la semántica del documento.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)

