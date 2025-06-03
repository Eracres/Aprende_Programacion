# 🧪 Ejemplo 6: Combinación de *ngIf y *ngFor

## 🎯 Objetivo

Demostrar cómo combinar directivas estructurales `*ngIf` y `*ngFor` para mostrar listas de forma condicional.

---

## 📁 Ruta: src/app/combinado/combinado.component.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-combinado',
  templateUrl: './combinado.component.html'
})
export class CombinadoComponent {
  elementos = ['HTML', 'CSS', 'Angular'];
  mostrar: boolean = true;
}
```

---

## 📁 Ruta: src/app/combinado/combinado.component.html

```html
<ul *ngIf="mostrar">
  <li *ngFor="let e of elementos">{{ e }}</li>
</ul>
```

---

## ✅ ¿Qué hace este componente?

Este componente utiliza `*ngIf` para mostrar una lista solo cuando la propiedad `mostrar` es verdadera, y a su vez recorre un array con `*ngFor`.  
Es un ejemplo claro de cómo Angular permite **componer directivas** para lograr comportamientos más complejos de forma declarativa.

---

## 🧠 Conceptos aplicados

- Directiva estructural `*ngIf` para control condicional
- Directiva estructural `*ngFor` para iterar arrays
- Renderizado dinámico en Angular
- Separación entre lógica de control (`.ts`) y presentación (`.html`)

---

## 💡 Variaciones sugeridas

### ✅ 1. Cambiar la condición de visibilidad

```ts
mostrar = false;
```

📌 **¿Por qué?**: Para probar que el contenido desaparece si la condición de `*ngIf` no se cumple.

---

### ✅ 2. Controlar visibilidad con un botón

```html
<button (click)="mostrar = !mostrar">Mostrar/Ocultar lista</button>
```

📌 **¿Por qué?**: Permite al usuario controlar si se muestra o no la lista, haciendo el ejemplo interactivo.

---

### ✅ 3. Usar un array de objetos en lugar de strings

```ts
elementos = [
  { nombre: 'HTML' },
  { nombre: 'CSS' },
  { nombre: 'Angular' }
];
```

```html
<li *ngFor="let e of elementos">{{ e.nombre }}</li>
```

📌 **¿Por qué?**: Enseña cómo trabajar con estructuras de datos más reales y complejas.

---

## ✅ ¿Cómo verificar que funciona correctamente?

1. Asegúrate de que `mostrar` esté en `true` y revisa que se renderice la lista.
2. Cambia `mostrar` a `false` y verifica que la lista desaparece.
3. Modifica los elementos del array y observa cómo se actualiza la vista.
4. Agrega un botón para alternar el estado de `mostrar` y verifica su comportamiento.

---

## 🔁 Navegación

### 🧪 - [⬅️](./Ejemplo_5.md) Ejemplo 5 - Módulo 4 [➡️](../../../Modulo_4_Routing/Modulo_4.md)

### 🧪 - [Volver a Ejemplos](../README.md)

### 📋 - [Ir a Ejercicios](../../Ejercicios/README.md)

### 📘 - [Volver a Módulo 3](../../Modulo_3.md)

### 🏠 - [Inicio](../../../README.md)

