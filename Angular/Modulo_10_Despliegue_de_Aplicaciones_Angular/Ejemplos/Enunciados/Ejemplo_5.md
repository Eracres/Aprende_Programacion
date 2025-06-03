# 🧪 Ejemplo 5: Configurar deploy en Vercel

## 🎯 Objetivo
Publicar una aplicación Angular en Vercel desde la terminal o mediante la web.

## 📁 Ruta: raíz del proyecto

1. Instala la CLI de Vercel:
```bash
npm i -g vercel
```

2. Ejecuta el asistente:
```bash
vercel
```

---

## ✅ ¿Qué hace este proceso?

Configura automáticamente el deploy y genera una URL pública.  
Ideal para pruebas rápidas y despliegues desde GitHub.

---

## 🧠 Conceptos aplicados

- CLI de Vercel
- Hosting global en CDN
- Vínculo con repositorio

---

## 💡 Variaciones sugeridas

### ✅ Añadir archivo `vercel.json`
```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```

📌 **¿Por qué?**: Garantiza que las rutas de Angular funcionen correctamente en Vercel.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Ejecuta `ng build`
2. Luego `vercel`
3. Visita la URL generada

---

## 🔁 Navegación
### 🧪 - [⬅️](./Ejemplo_4.md) Ejemplo 4 - Ejemplo 6 [➡️](./Ejemplo_6.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 10](../../Modulo_10.md)
### 🏠 - [Inicio](../../../README.md)

