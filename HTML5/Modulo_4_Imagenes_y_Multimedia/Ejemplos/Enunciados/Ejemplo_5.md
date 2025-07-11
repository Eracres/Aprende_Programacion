# 🧪 Ejemplo 5: Iframe con video de YouTube

## 🎯 Objetivo
Incrustar un video desde YouTube usando `<iframe>`.

## 📁 Ruta: /src/Ejemplos/Enunciados/Ejemplo_5.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Video desde YouTube</title>
</head>
<body>
  <h2>Tutorial embebido</h2>
  <iframe width="560" height="315"
          src="https://www.youtube.com/embed/dQw4w9WgXcQ"
          title="Video de YouTube"
          frameborder="0"
          allowfullscreen>
  </iframe>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
Muestra un video externo incrustado desde YouTube. Ideal para compartir contenido sin alojarlo directamente.

---

## 🧠 Conceptos aplicados
- Etiqueta `<iframe>`
- Atributo `allowfullscreen`
- Uso de vídeos remotos (CDN)

---

## 💡 Variaciones sugeridas

### 📁 Ruta: /src/Ejemplos/Variaciones/youtube-autoplay.html
```html
<iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1" allowfullscreen></iframe>
```
✅ Reproduce automáticamente el video al cargar.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)
### 🏠 - [Inicio](../../../README.md)

