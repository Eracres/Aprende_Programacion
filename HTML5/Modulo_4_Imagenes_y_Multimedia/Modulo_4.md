# 📘 Módulo 4: Imágenes y Multimedia

## 🎯 Objetivo del módulo
Aprender a integrar contenido multimedia en una página web utilizando HTML5: imágenes, audio, video e iframes. Este módulo también cubre buenas prácticas de accesibilidad y optimización.

---

## 🖼️ Insertar imágenes con `<img>`
La etiqueta `<img>` permite insertar imágenes en la web. Es importante siempre incluir el atributo `alt` por accesibilidad.

```html
<img src="logo.png" alt="Logo de la empresa" width="200" height="100">
```

### Atributos clave:
- `src`: ruta de la imagen.
- `alt`: texto alternativo si no se carga.
- `width` y `height`: dimensiones en píxeles o porcentaje.

---

## 🎵 Incluir archivos de audio con `<audio>`
La etiqueta `<audio>` permite reproducir sonidos.

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  Tu navegador no soporta el elemento de audio.
</audio>
```

### Atributos útiles:
- `controls`: muestra controles para reproducir/pausar.
- `autoplay`: comienza automáticamente (no recomendado por accesibilidad).
- `loop`: reproduce en bucle.

---

## 🎬 Reproducir video con `<video>`

```html
<video width="320" height="240" controls>
  <source src="video.mp4" type="video/mp4">
  Tu navegador no soporta el elemento de video.
</video>
```

### Buenas prácticas:
- Incluir subtítulos con `<track>`.
- Evitar autoplay.
- Comprimir los archivos para mejorar el rendimiento.

---

## 🌐 Incrustar contenido externo con `<iframe>`

```html
<iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" width="560" height="315" frameborder="0" allowfullscreen></iframe>
```

- Utiliza iframes para integrar contenido externo (videos, mapas, formularios).
- Ajusta tamaño, bordes y controles según el contexto.

---

## ✅ Buenas prácticas generales
- Optimiza imágenes para carga rápida (`.webp`, compresión).
- Usa texto alternativo descriptivo en imágenes.
- No sobrecargues con videos pesados o autoplay masivo.
- Asegura compatibilidad entre navegadores usando varios formatos (`.mp3`, `.ogg`, `.mp4`, `.webm`).

---

## 🧪 Ejemplos de este módulo

#### [🔗 Listado de Ejemplos](./Ejemplos/README.md)

---

## 📋 Ejercicios propuestos

#### [🔗 Listado de Ejercicios](./Ejercicios/README.md)

---

## 🔁 Navegación

### 📘 - [⬅️](../Modulo_3_Etiquetas_de_Texto_y_Formato/Modulo_3.md) Módulo 3 - Módulo 5 [➡️](../Modulo_5_Enlaces_y_Navegacion/Modulo_5.md)

### 🏠 - [Volver al Inicio](../README.md)
