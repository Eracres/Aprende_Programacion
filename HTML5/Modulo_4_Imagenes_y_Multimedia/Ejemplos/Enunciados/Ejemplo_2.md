# 🧪 Ejemplo 2: Imagen con ruta relativa y alternativa

## 🎯 Objetivo
Mostrar cómo usar rutas relativas en imágenes y definir textos alternativos apropiados para accesibilidad.

## 📁 Ruta: /src/Ejemplos/Enunciados/Ejemplo_2.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Galería de productos</title>
</head>
<body>
  <h1>Producto destacado</h1>
  <img src="../assets/img/producto1.jpg" alt="Imagen del producto estrella en promoción" width="400">
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
El ejemplo utiliza una ruta relativa para cargar una imagen ubicada en un subdirectorio diferente (`../assets/img/`). El atributo `alt` describe la imagen, cumpliendo con normas de accesibilidad.

---

## 🧠 Conceptos aplicados
- Uso de rutas relativas en `src`
- Buenas prácticas en descripciones `alt`
- Organización de carpetas para imágenes (`assets/img/`)

---

## 💡 Variaciones sugeridas

### 📁 Ruta: /src/Ejemplos/Variaciones/img-con-alt-descriptivo.html
```html
<img src="../assets/img/mouse.jpg" alt="Mouse inalámbrico negro con diseño ergonómico">
```
✅ Alternativa más descriptiva para accesibilidad visual.

### 📁 Ruta: /src/Ejemplos/Variaciones/img-ruta-incorrecta.html
```html
<img src="img/mouse.jpg" alt="Imagen del mouse">
```
❌ No se mostrará si la ruta es incorrecta. Asegúrate de verificar la ubicación del archivo.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_1.md) Ejemplo 1 - Ejemplo 3 [➡️](./Ejemplo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 4](../../Modulo_4.md)

### 🏠 - [Inicio](../../../README.md)

