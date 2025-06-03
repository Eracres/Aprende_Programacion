# 🧪 Ejemplo 1: Compilar aplicación para producción

## 🎯 Objetivo
Generar una versión optimizada de la aplicación Angular lista para ser desplegada.

## 📁 Ruta: raíz del proyecto
```bash
ng build --configuration production
```

---

## ✅ ¿Qué hace este comando?

Este comando compila la app con las configuraciones de producción, aplicando optimizaciones como:
- Minificación de código
- Eliminación de zonas muertas
- Compresión de archivos

Los resultados se guardan en la carpeta `dist/`.

---

## 🧠 Conceptos aplicados

- CLI de Angular
- Build para entornos productivos
- Optimización automática

---

## 💡 Variaciones sugeridas

### ✅ 1. Especificar carpeta de salida
```bash
ng build --outputPath=dist/proyecto-angular
```

📌 **¿Por qué?**: Controlas exactamente dónde se generan los archivos.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Ejecuta `ng build --configuration production`
2. Verifica que la carpeta `dist/` contiene los archivos `index.html`, `main.*.js`, etc.
3. Sirve localmente con `npx serve dist/` para comprobar el resultado.

---

## 🔁 Navegación
### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 10](../../Modulo_10.md)
### 🏠 - [Inicio](../../../README.md)
