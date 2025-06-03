# 🧪 Ejemplo 0: Crear y ejecutar tu primer proyecto Angular

## 🎯 Objetivo
Mostrar cómo instalar Angular CLI, crear un nuevo proyecto y ejecutarlo en el navegador.

## 📁 Ruta: comandos de terminal / estructura del proyecto inicial

```bash
npm install -g @angular/cli
ng new mi-proyecto
cd mi-proyecto
ng serve
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo guía al usuario en la creación de su primer proyecto Angular usando Angular CLI.  
Se muestran los comandos necesarios para instalar la herramienta, generar el proyecto y levantar el servidor local.

---

## 🧠 Conceptos aplicados

- Instalación de Angular CLI globalmente
- Creación de proyectos con `ng new`
- Levantar el servidor con `ng serve`
- Estructura inicial del proyecto Angular (`src/`, `app/`, `main.ts`, etc.)

---

## 💡 Variaciones sugeridas

### ✅ 1. Crear proyecto sin routing y con estilos SCSS

```bash
ng new mi-proyecto --routing=false --style=scss
```
📌 **¿Por qué?**: Puedes personalizar tu proyecto desde el inicio desactivando el router o cambiando el preprocesador CSS.

---

### ✅ 2. Servir en un puerto diferente

```bash
ng serve --port 4300
```
📌 **¿Por qué?**: Útil si tienes otro proyecto ocupando el puerto 4200.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Abre tu navegador en `http://localhost:4200`.
2. Asegúrate de ver la pantalla de bienvenida de Angular.
3. En consola no deben aparecer errores.
4. Puedes editar el archivo `src/app/app.component.html` y ver los cambios en tiempo real.

---

## 🔁 Navegación

### 🧪 - Ejemplo 1 [➡️](./Ejemplo_1.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 1](../../Modulo_1.md)

### 🏠 - [Inicio](../../../README.md)
