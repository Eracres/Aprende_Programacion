# 🧪 Ejemplo 1: Interpolación básica

## 🎯 Objetivo
Mostrar cómo enlazar una variable desde el componente TypeScript a la vista HTML usando interpolación.

## 📁 Ruta: src/app/app.component.ts
```ts
export class AppComponent {
  titulo: string = 'Curso Angular';
}
```

## 📁 Ruta: src/app/app.component.html
```html
<h1>{{ titulo }}</h1>
```

---

## ✅ ¿Qué hace este ejemplo?
Este ejemplo muestra cómo usar la **interpolación (`{{ }}`)** para insertar el valor de una variable directamente en el HTML desde la lógica del componente.

---

## 🧠 Conceptos aplicados

- Interpolación en Angular
- Enlace unidireccional de datos
- Separación de lógica (`.ts`) y vista (`.html`)

---

## 💡 Variaciones sugeridas

### ✅ Usar una expresión directamente en el HTML

```html
<h2>{{ 'Bienvenido al curso'.toUpperCase() }}</h2>
```

📌 ¿Por qué?: Puedes usar métodos inline para modificar la visualización.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener definido `titulo` en el componente.
2. Verifica que `{{ titulo }}` muestra su valor correctamente.
3. Modifica el valor de `titulo` y verifica que se actualiza en pantalla.

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)
### 🧪 - [Volver a Ejemplos](../README.md)
### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)
### 📘 - [Volver a Módulo 2](../../Modulo_2.md)
### 🏠 - [Inicio](../../../README.md)
