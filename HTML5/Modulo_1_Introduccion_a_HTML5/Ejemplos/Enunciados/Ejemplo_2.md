# 🧪 Ejemplo 2: Insertar imágenes y descripciones

## 🎯 Objetivo
Aprender a insertar imágenes en una página web utilizando la etiqueta `<img>` y complementar la accesibilidad mediante el atributo `alt`.

## 📁 Ruta: ./imagen.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Ejemplo con imagen</title>
</head>
<body>
  <h1>Imagen con descripción</h1>

  <img src="paisaje.jpg" alt="Paisaje natural con montañas y un lago" width="600">

  <p>Esta imagen representa un hermoso paisaje natural al atardecer.</p>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?

Este documento HTML inserta una imagen (`paisaje.jpg`) dentro del cuerpo de la página. Se utiliza el atributo `alt` para proporcionar una descripción alternativa en caso de que la imagen no se cargue, o para lectores de pantalla. También se usa el atributo `width` para controlar el tamaño de la imagen en pantalla.

---

## 🧠 Conceptos aplicados

- Uso de la etiqueta `<img>` para insertar imágenes
- Atributo `src` para indicar la ruta del archivo
- Atributo `alt` para mejorar accesibilidad y SEO
- Control de tamaño mediante `width` (o `height`)

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar el tamaño de la imagen con `height`
```html
<img src="paisaje.jpg" alt="Paisaje" height="300">
```
📌 **¿Por qué?**: Es útil cuando deseas establecer una altura fija.

### ✅ 2. Usar imágenes desde una URL externa
```html
<img src="https://via.placeholder.com/300" alt="Imagen de prueba">
```
📌 **¿Por qué?**: Permite mostrar imágenes sin necesidad de tener el archivo localmente.

### ✅ 3. Agregar un título emergente con `title`
```html
<img src="paisaje.jpg" alt="Paisaje" title="Vista del lago al atardecer">
```
📌 **¿Por qué?**: El atributo `title` muestra una ayuda emergente al pasar el mouse por encima.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener el archivo `paisaje.jpg` en la misma carpeta que `imagen.html`.
2. Abre `imagen.html` en tu navegador.
3. Verifica que la imagen se muestre correctamente.
4. Prueba borrar el archivo de imagen o cambiar el nombre para comprobar cómo se muestra el texto alternativo.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 1](../../Modulo_1.md)

### 🏠 - [Inicio](../../../README.md)

