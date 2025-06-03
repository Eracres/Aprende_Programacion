# 🧪 Ejemplo 4: Desplegar app en Netlify

## 🎯 Objetivo
Subir una aplicación Angular a Netlify para acceso público.

## 📁 Ruta: carpeta `dist/`
1. Accede a [https://app.netlify.com/](https://app.netlify.com/)
2. Crea una cuenta y selecciona **"Deploy manually"**
3. Arrastra la carpeta `dist/` a la zona de subida

---

## ✅ ¿Qué hace este proceso?

Netlify toma los archivos estáticos generados por Angular y los sirve como sitio web en su CDN global.

---

## 🧠 Conceptos aplicados

- Despliegue manual de sitios estáticos
- Interfaz de Netlify
- Publicación instantánea

---

## 💡 Variaciones sugeridas

### ✅ Usar CLI de Netlify
```bash
npm install -g netlify-cli
netlify deploy
```

📌 **¿Por qué?**: Automatiza despliegues y permite previsualizaciones.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Compila la app (`ng build`)
2. Sube `dist/` a Netlify
3. Accede al subdominio generado

---

## 🔁 Navegación
### 🧪 - [⬅️](./Ejemplo_3.md) Ejemplo 3 - Ejemplo 5 [➡️](./Ejemplo_5.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 10](../../Modulo_10.md)
### 🏠 - [Inicio](../../../README.md)

