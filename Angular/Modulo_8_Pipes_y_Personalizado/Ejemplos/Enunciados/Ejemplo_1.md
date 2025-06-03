# 🧪 Ejemplo 1: Uso básico de pipe uppercase

## 🎯 Objetivo
Aplicar el pipe `uppercase` para transformar texto en mayúsculas directamente desde el HTML.

## 📁 Ruta: src/app/uppercase/uppercase.component.ts
```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-uppercase',
  templateUrl: './uppercase.component.html'
})
export class UppercaseComponent {
  nombre = 'angular';
}
```

## 📁 Ruta: src/app/uppercase/uppercase.component.html
```html
<p>{{ nombre | uppercase }}</p>
```

---

## ✅ ¿Qué hace este ejemplo?

Este ejemplo transforma el contenido de la variable `nombre` a mayúsculas utilizando el pipe `uppercase` de Angular.  
Permite mostrar información en un formato estandarizado desde el template sin modificar la lógica del componente.

---

## 🧠 Conceptos aplicados

- Uso de pipes en Angular
- Transformaciones simples de datos
- Separación de lógica y vista

---

## 💡 Variaciones sugeridas

### ✅ Aplicar uppercase sobre interpolaciones más complejas
```html
<p>{{ 'curso de angular' | uppercase }}</p>
```
📌 **¿Por qué?**: Muestra que se pueden aplicar pipes directamente sobre cadenas literales o expresiones.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener el componente declarado en el módulo.
2. Carga el selector `<app-uppercase>` en `app.component.html`.
3. Verifica que el navegador muestra `ANGULAR` (en mayúsculas).

---

## 🔁 Navegación

### 🧪 - Ejemplo 2 [➡️](./Ejemplo_2.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 8](../../Modulo_8.md)

### 🏠 - [Inicio](../../../README.md)
