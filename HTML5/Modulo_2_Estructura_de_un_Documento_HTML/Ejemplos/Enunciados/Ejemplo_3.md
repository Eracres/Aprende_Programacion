# 🧪 Ejemplo 3: Incluir CSS y JavaScript en el head

## 🎯 Objetivo
Aprender cómo enlazar correctamente archivos de hojas de estilo (CSS) y scripts de JavaScript dentro del documento HTML, específicamente en la sección `<head>`.

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Documento con CSS y JS</title>
  <link rel="stylesheet" href="styles.css">
  <script src="script.js"></script>
</head>
<body>
  <h1>Hola mundo con estilos y lógica</h1>
  <button onclick="mostrarAlerta()">Haz clic</button>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
Demuestra cómo conectar correctamente una hoja de estilos CSS y un archivo JavaScript desde el `<head>` de un documento HTML, asegurando que el diseño y las funcionalidades estén disponibles al cargar la página.

---

## 🧠 Conceptos aplicados
- Uso de `<link>` para incluir archivos `.css`
- Uso de `<script>` para cargar scripts JavaScript
- Posición del `<script>` en el `<head>` (opcionalmente se recomienda colocarlo al final del `<body>` si bloquea la carga)

---

## 💡 Variaciones sugeridas

### ✅ 1. Mover el `<script>` al final del `<body>`
```html
<body>
  <!-- contenido -->
  <script src="script.js"></script>
</body>
```
📌 **¿Por qué?**: Mejora el rendimiento y evita que el script bloquee el renderizado inicial de la página.

### ✅ 2. Usar `defer` para no bloquear la carga
```html
<script src="script.js" defer></script>
```
📌 **¿Por qué?**: Permite que el navegador continúe procesando el HTML mientras descarga y ejecuta el script después.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Módulo 3 [➡️](../../../Modulo_3/Modulo_3.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 2](../../Modulo_2.md)

### 🏠 - [Inicio](../../../README.md)

