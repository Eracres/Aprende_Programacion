# 🧪 Ejemplo 1: Componente básico con interpolación

## 🎯 Objetivo
Crear un componente Angular que muestre contenido dinámico utilizando interpolación (`{{ }}`) para insertar el valor de una variable en la vista HTML.

## 📁 Ruta: src/app/saludo/saludo.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-saludo',
  templateUrl: './saludo.component.html',
  styleUrls: ['./saludo.component.css']
})
export class SaludoComponent {
  nombre: string = 'Estudiante';
}
```

---

## 📁 Ruta: src/app/saludo/saludo.component.html

```html
<h2>Hola, {{ nombre }} 👋</h2>
```

---

## ✅ ¿Qué hace este componente?

Este componente muestra un mensaje personalizado utilizando interpolación de datos en Angular.  
La variable `nombre` definida en el componente se inserta directamente en la vista HTML usando `{{ nombre }}`.

---

## 🧠 Conceptos aplicados

- Creación de componentes con Angular CLI
- One-way data binding (enlace unidireccional)
- Interpolación con `{{ variable }}`
- Separación entre lógica (`.ts`) y vista (`.html`)

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar el valor por defecto de `nombre`

📁 Ruta: `src/app/saludo/saludo.component.ts`
```ts
nombre: string = 'Lucía';
```
📌 **¿Por qué?**: Muestra un saludo diferente al inicial.

---

### ✅ 2. Convertir `nombre` en una entrada desde el componente padre

📁 Ruta: `src/app/saludo/saludo.component.ts`
```ts
@Input() nombre: string = '';
```

📁 Ruta: `src/app/app.component.html`
```html
<app-saludo [nombre]="'Carlos'"></app-saludo>
```
📌 **¿Por qué?**: Permite reutilizar el componente y pasarle datos dinámicamente desde su contenedor.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de tener importado y declarado el componente `SaludoComponent` en `app.module.ts`.
2. Inserta el selector `<app-saludo></app-saludo>` en `app.component.html`.
3. Ejecuta `ng serve` y comprueba que aparece el saludo en pantalla.
4. Si editas `nombre`, el contenido del `<h2>` debe actualizarse automáticamente.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_0.md) Ejemplo 0 - Módulo 2 [➡️](../../../Modulo_2_Componentes_y_Data_Binding/Modulo_2.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 1](../../Modulo_1.md)

### 🏠 - [Inicio](../../../README.md)
