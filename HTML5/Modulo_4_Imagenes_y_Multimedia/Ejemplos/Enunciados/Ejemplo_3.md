# 🧪 Ejemplo 3: Incluir audio con controles

## 🎯 Objetivo
Aprender a usar la etiqueta `<audio>` para incluir archivos de sonido con controles de reproducción.

## 📁 Ruta: /src/Ejemplos/Enunciados/Ejemplo_3.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Audio de bienvenida</title>
</head>
<body>
  <h2>Escucha nuestro saludo</h2>
  <audio controls>
    <source src="../assets/audio/saludo.mp3" type="audio/mpeg">
    Tu navegador no soporta el elemento de audio.
  </audio>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
Este código inserta un archivo de audio `.mp3` con controles básicos (play, pausa, volumen). También se incluye un mensaje alternativo si el navegador no lo soporta.

---

## 🧠 Conceptos aplicados
- Etiqueta `<audio>` con atributo `controls`
- Uso de `<source>` y tipo MIME
- Mensaje alternativo

---

## 💡 Variaciones sugeridas

### 📁 Ruta: /src/Ejemplos/Variaciones/audio-autoplay.html
```html
<audio controls autoplay>
  <source src="../assets/audio/saludo.mp3" type="audio/mpeg">
</audio>
```
✅ El audio comienza a reproducirse automáticamente.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_2.md) Ejemplo 2 - Ejemplo 4 [➡️](./Ejemplo_4.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)
### 🏠 - [Inicio](../../../README.md)

