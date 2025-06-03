# 🧪 Ejemplo 4: Formulario simple con validaciones HTML5

## 🎯 Objetivo
Explorar cómo crear un formulario básico en HTML5 con campos comunes y validaciones nativas del navegador.

## 📁 Ruta: ./formulario.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Formulario de contacto</title>
</head>
<body>
  <h1>Contáctanos</h1>

  <form action="/enviar" method="post">
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required>

    <br><br>

    <label for="email">Correo electrónico:</label>
    <input type="email" id="email" name="email" required>

    <br><br>

    <label for="edad">Edad:</label>
    <input type="number" id="edad" name="edad" min="1" max="120">

    <br><br>

    <label for="mensaje">Mensaje:</label><br>
    <textarea id="mensaje" name="mensaje" rows="4" cols="40" required></textarea>

    <br><br>

    <button type="submit">Enviar</button>
  </form>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?

Este documento crea un formulario con distintos campos: texto, correo, número y un área de texto. Todos ellos utilizan validaciones propias de HTML5 como `required`, `type`, `min` y `max`, que ayudan a garantizar que el usuario ingrese datos válidos antes de enviar el formulario.

---

## 🧠 Conceptos aplicados

- Uso de `<form>` con atributos `action` y `method`
- Campos de entrada: `<input type="text">`, `<input type="email">`, `<input type="number">`
- Área de texto con `<textarea>`
- Validaciones nativas: `required`, `min`, `max`, `type`
- Etiquetas `<label>` asociadas a inputs mediante `for` e `id`

---

## 💡 Variaciones sugeridas

### ✅ 1. Agregar campo de contraseña con validación
```html
<input type="password" name="clave" required minlength="6">
```
📌 **¿Por qué?**: Permite recoger claves con longitud mínima.

### ✅ 2. Usar `placeholder` en campos
```html
<input type="text" name="nombre" placeholder="Tu nombre aquí">
```
📌 **¿Por qué?**: Mejora la usabilidad mostrando un texto indicativo.

### ✅ 3. Agrupar campos con `<fieldset>` y `<legend>`
```html
<fieldset>
  <legend>Datos personales</legend>
  <!-- campos aquí -->
</fieldset>
```
📌 **¿Por qué?**: Mejora la organización visual y semántica del formulario.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Abre `formulario.html` en el navegador.
2. Intenta enviar el formulario sin completar los campos requeridos.
3. Observa cómo el navegador impide el envío y muestra mensajes de error.
4. Rellena los campos con datos válidos para ver que se permite el envío.

---

## 🔁 Navegación

### 🧪 -  [⬅️](./Ejemplo_3.md) Ejemplo 3 - Módulo 2 [➡️](../../../Modulo_2/Modulo_2.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 1](../../Modulo_1.md)

### 🏠 - [Inicio](../../../README.md)
