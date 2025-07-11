# 🧪 Ejemplo 4: Reproducir video MP4 con subtítulos

## 🎯 Objetivo
Aprender a usar la etiqueta `<video>` y agregar subtítulos con `<track>`.

## 📁 Ruta: /src/Ejemplos/Enunciados/Ejemplo_4.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Video introductorio</title>
</head>
<body>
  <h2>Video de presentación</h2>
  <video width="640" height="360" controls>
    <source src="../assets/video/presentacion.mp4" type="video/mp4">
    <track src="../assets/video/subtitulos.vtt" kind="subtitles" srclang="es" label="Español">
    Tu navegador no soporta el video.
  </video>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
Reproduce un video `.mp4` y carga subtítulos desde un archivo `.vtt`. Mejora la accesibilidad para usuarios con problemas auditivos.

---

## 🧠 Conceptos aplicados
- Etiqueta `<video>` con controles
- Uso de `<source>` para video
- Inclusión de subtítulos mediante `<track>`

---

## 💡 Variaciones sugeridas

### 📁 Ruta: /src/Ejemplos/Variaciones/video-sin-subtitulos.html
```html
<video controls>
  <source src="../assets/video/presentacion.mp4" type="video/mp4">
</video>
```
✅ Versión sin subtítulos.

---

## 🔁 Navegación

### 🧪 - Ejemplo 3 [⬅️](./Ejemplo_3.md) | Ejemplo 5 [➡️](./Ejemplo_5.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)
### 🏠 - [Inicio](../../../README.md)

