# 🧪 Ejemplo 8: Reproducción de múltiples formatos de audio

## 🎯 Objetivo
Garantizar compatibilidad de audio en distintos navegadores usando múltiples fuentes.

## 📁 Ruta: /src/Ejemplos/Enunciados/Ejemplo_8.html

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Audio compatible</title>
</head>
<body>
  <h2>Audio en varios formatos</h2>
  <audio controls>
    <source src="../assets/audio/musica.mp3" type="audio/mpeg">
    <source src="../assets/audio/musica.ogg" type="audio/ogg">
    Tu navegador no soporta el audio.
  </audio>
</body>
</html>
```

---

## ✅ ¿Qué hace este ejemplo?
Permite reproducir audio en navegadores modernos y antiguos utilizando archivos `.mp3` y `.ogg`.

---

## 🧠 Conceptos aplicados
- Etiqueta `<audio>` con varias fuentes
- Compatibilidad cruzada
- Accesibilidad

---

## 💡 Variaciones sugeridas

### 📁 Ruta: /src/Ejemplos/Variaciones/audio-solo-mp3.html
✅ Incluye solo un tipo de formato.

---

## 🔁 Navegación

### 🧪 - Ejemplo 7 [⬅️](./Ejemplo_7.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 4](../../Modulo_4.md)
### 🏠 - [Inicio](../../../README.md)

