# 🧪 Ejemplo 6: Mostrar código fuente y bloques preformateados

## 🎯 Objetivo
Aprender a utilizar las etiquetas `<pre>` y `<code>` combinadas para mostrar bloques de código con formato preservado, útil para ejemplos técnicos o documentación.

## 📁 Ruta: ejemplos/Modulo_3/Ejemplo_6.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Bloques de código</title>
</head>
<body>
  <h1>Ejemplo de bloque de código</h1>

  <pre><code>
function saludar(nombre) {
  console.log("Hola, " + nombre);
}

saludar("Carlos");
  </code></pre>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo muestra cómo usar la combinación de `<pre>` + `<code>` para presentar bloques de código que mantengan la indentación, saltos de línea y estilo monoespaciado, útil en tutoriales o manuales técnicos.

---

## 🧠 Conceptos aplicados

- Uso de `<pre>` para conservar el formato original del texto (espacios, saltos de línea)
- Uso de `<code>` para representar fragmentos de código con estilo tipográfico adecuado
- Combinación ideal para bloques de código en documentación web

---

## 💡 Variaciones sugeridas

### ✅ Agregar sintaxis de colores con librerías como highlight.js o Prism.js (a nivel más avanzado)

```html
<pre><code class="language-javascript">
const saludo = (nombre) => {
  console.log(`Hola, ${nombre}`);
};
</code></pre>
```
📌 **¿Por qué?**: Ayuda a mejorar la legibilidad del código y destacar su estructura.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Abre el archivo en un navegador.
2. Asegúrate de que el bloque conserve el formato original del código.
3. Verifica que se use fuente monoespaciada y que el contenido no se colapse.
4. Edita el código para ver cómo se comporta al agregar líneas o espacios.

---

## 🔁 Navegación

### 🧪 - Ejemplo 5 [⬅️](./Ejemplo_5.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)
